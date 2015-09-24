---
layout: article
title: "Multicolor WiFi Bulb, the first Arduino based one"
categories: articles
author: plinio_seniore
excerpt: "We are working with Authometion for the release of LYT8266, a Lifx-like ESP8266 based bulb"
tags: [authometion, lyt, esp8266, wifi]
modified: 2015-09-24
ads: false  
image:
  feature: 2015-09/lyt8266-white.jpg
  teaser: 2015-09/lyt8266-white-teaser.jpg
  credit: Authometion
  creditlink: http://authometion.com/
---

In these days we are working closed with Authometion and their new bulb, the LYT8266 that will be unveiled at [European Maker Faire in Rome](http://www.makerfairerome.eu/en/) (from 16th to 18th October 2015). These new bulbs share with the LYT88 the AC/DC and RGBW LED but instead of an ATmega88 use an ESP8266 that gives WiFi and control over the LEDs.

![](http://souliss.net/images/2015-09/lyt8266-color.jpg?raw=true)

> The LYT8266 compares directly with the most famous WiFi bulb, the [Lifx](http://www.lifx.com/), with a more competitive price and most important with full access to the ESP8266 microcontroller and its [Arduino support](https://github.com/esp8266/Arduino). 

As any other ESP8266 based device, also the LYT8266 can be programmed using the Arduino IDE and can run [Souliss natively](https://github.com/souliss/souliss/wiki/Supported%20Hardware), just before the start of the Maker Faire we will release Souliss v7.1 with example sketches for the new LYT bulb. In the while here a quick preview, the LYT8266 will be the first product that benefit the new WebConfig interface that allow full IP and Souliss network configuration on runtime.

At the startup the ESP8266 starts as access point and stars a simple webserver as in the below picture, from where you can configure all the needs, included the [Gateway or Peer](https://github.com/souliss/souliss/wiki/RuntimeConfiguration) behavoir of the node.

![](http://souliss.net/images/2015-09/WebConfig.png?raw=true)

At the Maker Faire you can preview the LYT8266 running Souliss or any other Arduino sketch, this include SoulissApp and openHAB as well as all networking feature.

![](http://souliss.net/images/2015-09/SoulissApp.jpg?raw=true)