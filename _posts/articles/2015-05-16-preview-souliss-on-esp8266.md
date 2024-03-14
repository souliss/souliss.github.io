---
layout: article
title: "Preview : Run Souliss on Olimex ESP8266-EVB"
categories: articles
author: plinio_seniore
excerpt: "Few hours and Souliss is running on ESP8266, that's amazing!"
tags: [souliss, arduino, esp8266, wifi, olimex]
modified: 2015-05-16
image:
  feature: 
  teaser: 2015-05/Esp8266pinout1-teaser.png
ads: false  
redirect_from: "2015/05/preview-run-souliss-on-olimex-esp8266.html"
---

A couple of weeks ago we got some [Olimex ESP8266-EVB](http://souliss.github.io/2015/04/first-experiment-run-souliss-on-esp8266.html) a small board to quickly prototype on the cheapest WiFi module for DIYers actually on the market, yesterday the porting of Souliss has been completed and now we can run directly on this module without have an Arduino ATmega inbetween.

The Arduino core for the ESP8266 is constantly updated and for this reason we are distributing an Arduino IDE for Windows that includes the tested cores (*update, the IDE has been removed as the cores are now stable* **follow [this tutorial instead](http://souliss.github.io/media/how-to-load-a-sketch-on-ESP/)**), just ensure that in your Documents/Arduino/libraries there isn't a Souliss library, this because the IDE that we provide contains also the latest Souliss code.

Run this sketch, considering the GPIO available on your module, this use GPIO5 that is used in Olimex ESP8266-EVB with a relay.

{% highlight c %}
/**************************************************************************  
   Souliss - Hello World for Expressif ESP8266  
   This is the basic example, create a software push-button on Android  
   using SoulissApp (get it from Play Store).   
   Load this code on ESP8266 board using the porting of the Arduino core  
   for this platform.  
 ***************************************************************************/  
 // Configure the framework  
 #include "bconf/MCU_ESP8266.h"       // Load the code directly on the ESP8266  
 #include "conf/Gateway.h"          // The main node is the Gateway, we have just one node  
 #include "conf/DynamicAddressing.h"     // Use dynamic addressing  
 #include "conf/DisableEEPROM.h"  
 // Define the WiFi name and password  
 #define WIFICONF_INSKETCH  
 #define WiFi_SSID        "mywifi"  
 #define WiFi_Password      "mypassword"    
 // Include framework code and libraries  
 #include <ESP8266WiFi.h>  
 #include "Souliss.h"  
 // This identify the number of the LED logic  
 #define MYLEDLOGIC     0          
 void setup()  
 {    
   Initialize();  
   // Connect to the WiFi network and get an address from DHCP  
   Setup_ESP8266();                
   SetAsGateway(myvNet_esp8266);    // Set this node as gateway for SoulissApp   
   // This node will serve all the others in the network providing an address  
   SetAddressingServer();  
   Set_SimpleLight(MYLEDLOGIC);    // Define a simple LED light logic  
   pinMode(5, OUTPUT);         // Use pin 5 as output   
 }  
 void loop()  
 {   
   // Here we start to play  
   EXECUTEFAST() {             
     UPDATEFAST();    
     FAST_50ms() {  // We process the logic and relevant input and output every 50 milliseconds  
       Logic_SimpleLight(MYLEDLOGIC);  
       DigOut(5, Souliss_T1n_Coil,MYLEDLOGIC);  
     }   
     // Here we handle here the communication with Android  
     FAST_GatewayComms();                      
   }  
 }  
{% endhighlight %}

If you have the Olimex module, is enough to press the button and then power the module, this set the module in firmware mode and let you load the code from the IDE using an FTDI at 3.3v as shown in [Olimex post](https://olimex.wordpress.com/2015/03/31/programming-esp8266-evb-with-arduino-ide/).

Using the ESP-01 and other modules from other vendors require an external connection as per following scheme

![](http://souliss.github.io/images/2015-05/esp8266-push-button-web.png?raw=true)

In the sketch insert your WiFi SSID and Password, once loaded the module connects to your router and you can control it directly from SoulissApp (download the [app here](https://play.google.com/store/apps/details?id=it.angelic.soulissclient)) and the app will automatically discover your node.

The result is [SoulissApp](https://github.com/souliss/souliss/wiki/SoulissApp) showing the node and the relay for control,

![](http://souliss.github.io/images/2015-05/SoulissApp.png?raw=true)

This is just a simple example, because the ESP8266 runs a full Souliss framework and you can communicate with other ESP and AVR based boards (where also wireless-RF and RS485 are supported) to have a full network between your nodes.

The support for ESP8266 has just started, use the [community](https://github.com/souliss/souliss/wiki/Community) to get help and follow the wiki for details.

Enjoy!