---
layout: article
title: "Smart Home with ESP8266 and openHAB"
categories: articles
author: plinio_seniore
excerpt: "With the ESP8266 supported in Souliss, get it in openHAB is a breeze!"
tags: [souliss, arduino, esp8266, wifi]
modified: 2015-04-28
image:
  feature: 
  teaser: 2015-05/openhab-teaser.jpg
ads: false  
redirect_from: "2015/05/smart-home-with-esp8266-and-openhab.html"
---

Last weeks were full of news, as announced in a [previous post](http://www.souliss.net/2015/05/preview-run-souliss-on-olimex-esp8266.html) we have started and basically completed the porting of Souliss on ESP8266 modules, isn't a simple use of the ESP8266 as a transceiver for an Arduino based on an Atmel AVR microcontroller, but is the Souliss framework itself that runs on the ESP8266. 
All has started from Saverio, it was Easter when he came out with the news, [he compiled successfully most of Souliss code for an ESP8266](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!msg/souliss-it/1uDh8lSuVIo/Os0QjjFw0QUJ) and after a couple of days we got some basic functionality available.This has been possible thanks to the amazing work of the guys that has ported the cores in the [Arduino IDE for ESP8266](https://github.com/esp8266/Arduino).

Just the time to release a first try of Souliss for ESP8266 and a bunch of people in our [mailing list](https://github.com/souliss/souliss/wiki/Community) were ready to test and share feedback, as result [Souliss release v.7.0.5](https://github.com/souliss/souliss/releases/tag/v7.0-friariello.5) is now ready to be installed from the [Library Manager](https://github.com/souliss/souliss/wiki/Getting%20Started%20with%20Souliss).

Just a couple of days ago we also got the official inclusion of the [Tonino's binding in openHAB](https://github.com/openhab/openhab/wiki/Souliss-Arduino-based-SmartHome-Binding), so you can now officially use openHAB with a Souliss, and of course with ESP8266 running Souliss.

To use ESP8266 you need to install the relevant cores by ESP8266 community, this can be done directly from the Board Manager of your IDE using the instruction [here](https://github.com/esp8266/Arduino). Then load the following sketch and follow the instruction to [configure the binding](https://github.com/openhab/openhab/wiki/Souliss-Arduino-based-SmartHome-Binding).

{% highlight c %}
/**************************************************************************
    Souliss - Hello World
    
    This is the basic example, control one LED via a push-button or Android
    using SoulissApp (get it from Play Store).  
    
    Run this code on ESP8266 as WiFi SoC.
        
***************************************************************************/

// Configure the framework
#include "bconf/MCU_ESP8266.h"          
#include "conf/Gateway.h"                  
#include "conf/IPBroadcast.h"

// **** Define the WiFi name and password ****
#define WIFICONF_INSKETCH
#define WiFi_SSID               "mywifi"
#define WiFi_Password           "mypassword"   

// Include framework code and libraries
#include 
#include "Souliss.h"

// This identify the number of the LED logic
#define MYLEDLOGIC          0               

// Define the network configuration according 
// to your router settings
uint8_t ip_address[4]  = {192, 168, 1, 77};
uint8_t subnet_mask[4] = {255, 255, 255, 0};
uint8_t ip_gateway[4]  = {192, 168, 1, 1};
#define Gateway_address 77
#define myvNet_address  ip_address[3]  
#define myvNet_subnet   0xFF00
#define myvNet_supern   Gateway_address

// **** Define here the right pin for your ESP module **** 
#define OUTPUTPIN   5

void setup()
{   
    Initialize();

     // Set network parameters
    Souliss_SetIPAddress(ip_address, subnet_mask, ip_gateway);
    SetAsGateway(myvNet_address);  
    
    // Define a simple LED light logic
    Set_SimpleLight(MYLEDLOGIC);        
    
    pinMode(OUTPUTPIN, OUTPUT);  // Power the LED
}

void loop()
{ 
    // Here we start to play
    EXECUTEFAST() {                     
        UPDATEFAST();   
        
        // We process the logic and relevant input 
        // and output every 50 milliseconds
        FAST_50ms() {   
            // Drive the LED as per command
            Logic_SimpleLight(MYLEDLOGIC);    
            DigOut(OUTPUTPIN, Souliss_T1n_Coil, MYLEDLOGIC);                
        } 
              
        // Here we handle here the communication
        FAST_GatewayComms();                                        
        
    }
} 
{% endhighlight %}

Ensure that the pins available on your module matches the one in the sketches, so that you can control it via openHAB and of course SoulissApp.

Enjoy!