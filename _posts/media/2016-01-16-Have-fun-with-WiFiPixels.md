---
layout: article
title: "Have fun with WiFiPixels"
date: 2016-01-16
modified:
categories: media
excerpt: "The light effects of WS2812 addressable LEDs with the connectivity of the ESP8266 WiFi module."
author: plinio_seniore
ads: false
image:
  feature: 2016-01/wifipixels.jpg
  teaser: 2016-01/wifipixels-teaser.jpg
  credit: Protoneer
  creditlink: http://blog.protoneer.co.nz/
---

Far from the Australia the WiFi Pixel has arrived in my mailbox, this is a combination of a NeoPixel Ring and an ESP8266 WiFi SoC that gives the awesome effects of 16 WS2812 addressable LEDs.

> The WS2812 combine three LED (Red, Green and Blue) and a small circuit that acts as a shift register 24 bit memory. So you can use a proper waveform to have it store a color as input and as any shift register it output the previous value, the result it that a single pin can drive an array of LED with the length as you want.

The below image by [Adafruit](https://learn.adafruit.com/assets/10668) shows the internal view of the addressable LED

![](http://souliss.net/images/2016-01/leds_neo-closeup.jpg?raw=true)

Assuming that you know how to use the [Arduino IDE and the ESP8266](http://souliss.net/media/how-to-load-a-sketch-on-ESP/), you just have to download the [Adafruit NeoPixel library](https://github.com/plinioseniore/Adafruit_NeoPixel) and have the latest Souliss release (v7.1.1 at time of writing) to run the following sketch

{% highlight c %}
/**************************************************************************
    Souliss - WiFi Pixels

    Control a WiFi Pixels board from Android or openHAB, it network the node
    so that you can control the light effect also from other Souliss nodes
    using peer to peer send or listening for broadcasted/multicasted topics.

    Need Adafruit NeoPixel library.

    Run this code on one of the following boards:
      - Protoneer WiFi Pixels
      - An ESP8266 with WS2812 LEDs

***************************************************************************/

// Configure the framework
#include "bconf/MCU_ESP8266.h"              // Load the code directly on the ESP8266
#include "conf/Gateway.h"                   // The main node is the Gateway, we have just one node

// **** Define the WiFi name and password ****
#define WIFICONF_INSKETCH
#define WiFi_SSID               "mywifi"
#define WiFi_Password           "mypassword"    

// Include framework code and libraries
#include <ESP8266WiFi.h>
#include <EEPROM.h>
#include "Souliss.h"

// Dependency
#include <Adafruit_NeoPixel.h>

// WiFi Pixels pin
#define WS2812_PIN        2
#define WS2812_PIXELS     16

// Souliss logic (aka typical) slots
#define LEDCONTROL        0
#define LEDRED            1
#define LEDGREEN          2
#define LEDBLUE           3
#define ALLTHESAME        4
#define COLORWIPE         5
#define THEATERCHASE      6

/*** 
    Color Effect Mode:

        4 - All The Same
        5 - Color Wipe
        6 - Theater Chase
***/
uint8_t coloreffect=ALLTHESAME;

// Index of the addressed pixel
uint8_t i_coloreffect=0;    
unsigned long timedelay=millis();
#define TIME_DELAY           50     // Not stopping delay in milliseconds

// Init the LED object, refer to Adafruit NeoPixel library for more details
Adafruit_NeoPixel strip = Adafruit_NeoPixel(WS2812_PIXELS, WS2812_PIN, NEO_GRB + NEO_KHZ800);

void setup()
{   
    Initialize();

    // Get the IP address from DHCP
    GetIPAddress();                          
    SetAsGateway(myvNet_dhcp);                  // Set this node as gateway for SoulissApp                        

    Set_T16(LEDCONTROL);                        // Set a logic to control a LED strip
    Set_T11(ALLTHESAME);                        // Set a button for the All The Same effect
    Set_T11(COLORWIPE);                         // Set a button for the Color Wipe effect
    Set_T11(THEATERCHASE);                      // Set a button for the Theater Chase effect

    // Init the pixels
    strip.begin();
    strip.show(); 

    // Init the All The Same mode as default
    mOutput(ALLTHESAME) = 1;
}

void loop()
{ 
    // Here we start to play
    EXECUTEFAST() {                     
        UPDATEFAST();   

        // Execute the code every 10 milliseconds   
        FAST_10ms() {

            // Execute the logic that handle the LED
            if(Logic_T16(LEDCONTROL)) timedelay=millis();
            setColor();

            // Just process communication as fast as the logics
            ProcessCommunication();
        } 

        // Execute the code every 110 milliseconds  
        FAST_110ms() {
            
            // Select the effect mode
            if(Logic_T11(ALLTHESAME)) {
                coloreffect = ALLTHESAME;

                // Reset the other color mode
                mOutput(COLORWIPE) = 0;
                mOutput(THEATERCHASE) = 0;
            }

            if(Logic_T11(COLORWIPE)) {
                coloreffect = COLORWIPE;

                // Reset the other color mode
                mOutput(ALLTHESAME) = 0;
                mOutput(THEATERCHASE) = 0;
            }

            if(Logic_T11(THEATERCHASE)) {
                coloreffect = THEATERCHASE;

                // Reset the other color mode
                mOutput(COLORWIPE) = 0;
                mOutput(ALLTHESAME) = 0;
            }

        }

        // Process the other Gateway stuffs
        FAST_GatewayComms();

    }
    EXECUTESLOW()
    {   
        UPDATESLOW();

        SLOW_10s()  {

            // The timer handle timed-on states
            Timer_LED_Strip(LEDCONTROL);                      
        }     
    }       
}

// Set the selected color and effect
void setColor() {
    
    if(coloreffect==COLORWIPE)          colorWipe();
    else if(coloreffect==THEATERCHASE)  theaterChase();
    else                                alltheSame();

    strip.show();
}

// Set the same color for all pixels
void alltheSame() {
    uint32_t c = strip.Color(mOutput(LEDRED), mOutput(LEDGREEN), mOutput(LEDBLUE));

    for(i_coloreffect=0;i_coloreffect<strip.numPixels();i_coloreffect++)
        strip.setPixelColor(i_coloreffect, c);
}

// Set the current color one pixel per time
void colorWipe() {

    // Update periodically
    if((long)(millis()-timedelay)>0) {

        uint32_t c = strip.Color(mOutput(LEDRED), mOutput(LEDGREEN), mOutput(LEDBLUE));

        strip.setPixelColor(i_coloreffect, c);
        i_coloreffect = (i_coloreffect+1) % strip.numPixels();
        
        timedelay = millis() + TIME_DELAY;
    }
}

// Turn the third pixel and shut the previous
void theaterChase() {

    // Update periodically
    if((long)(millis()-timedelay)>0) {

        uint32_t c = strip.Color(mOutput(LEDRED), mOutput(LEDGREEN), mOutput(LEDBLUE));

        strip.setPixelColor(i_coloreffect, c);
        strip.setPixelColor(i_coloreffect+2, 0);
        i_coloreffect = (i_coloreffect+3) % strip.numPixels();

        timedelay = millis() + TIME_DELAY;
    }
}
{% endhighlight %}

In SoulissApp you will have direct control of the main color and you will be able to select a light effect between three choices, more can of course be added, just keep in mind that Souliss is running in the background and effect shall not stop the code execution.

Enjoy this little light module and share were you will use it!