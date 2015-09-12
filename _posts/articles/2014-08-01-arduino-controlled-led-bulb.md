---
layout: article
title: "An Arduino controlled LED Bulb with Souliss"
categories: articles
author: plinio_seniore
excerpt: "Authometion LYT bulbs preview"
tags: [arduino, authometion, lyt, bulb]
modified: 2014-08-01
image:
  feature: 
  teaser: 
ads: false  
redirect_from: "2014/08/an-arduino-controlled-led-bulb-with.html"
---

A couple of months ago I got one email from a startup that is developing a set of Arduino compatible smart devices, they are not yet on the market and their name Authometion has probably never been in your ears.
They have several ideas for products powered by an Arduino compatible AVR, following an approach that isn't far from ZWave or Zigbee products: light bulbs, smart socket and others; with the key goal that those can be programmable by the user to fit their needs. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/M6zf2jSaJDE" frameborder="0" allowfullscreen></iframe>

Of course those products will be sold with a ready to use software and a common goal would be having Souliss at the hearth of those devices. Actually we are working to understand if Souliss can fit in those devices and the video above shows the first integration with the IoTuino.

In this case, the LED Bulb isn't an Arduino compatible device (so doesn't run Souliss) but is controlled from IoTuino, that board has an ATmega328P with Arduino UNO booatloader with a WiFi transceiver and a point-to-point wireless 2.4 GHz transceiver to control the bulbs. A 521 KByte flash memory is also available on IoTuino via SPI, this lets save customization parameters or logging data from remote (even located on different Arduino or IoTuino) boards.
At this stage, Souliss runs over IoTuino communicating with any other Souliss devices through the WiFi module (that is loaded with a special firmware for the case) and then map the action through a set of API developed by Authometion.

The result is a light bulb that integrate in any Souliss network, so you can control those from any other board running Souliss or from Android and openHAB (using the openHAB interface on an external board).

Is just a small step, the biggest one will be available in the next months, when on the market there will be completely open source products that are at same time ready to use, a real freedom for integration and customization.