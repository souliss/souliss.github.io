---
layout: article
title: "Hardware development, next step with Olimex"
categories: articles
author: plinio_seniore
excerpt: "Integration completed."
tags: [arduino, android, olimex, uext]
modified: 2013-04-11
image:
  feature: 2013-04/olimex-rgb.jpg
  teaser: 2013-04/olimex-rgb-teaser.jpg
ads: false  
redirect_from: "2013/04/hardware-development-next-step-with.html"
---

As promised we are focusing on hardware, today we received from Olimex a set of boards that will soon be integrated into Souliss. In the first step was a small WiFi relay controller, the core are always Arduino compatible boards but we are focused on what is placed near it.

![](http://souliss.net/images/2013-04/olimex-boards.jpg?raw=true)

As you can see in the main picture, as communication devices there are two Ethernet boards based on Microchip ENC28J60, same as many shield like the one from Open Electronics, but with a really tiny shape and the UEXT connector. These boards are yet supported in Souliss, due to the work done for KMTronic DINo, and runs over uIP software stack.

A new entry is the RGB LED strip controller, is based on a Microchip microcontroller that get via I2C the values for Red, Blue and Green color and drives the three output MOSFET accordingly. This device lets control LED and strips and using the new SoulissApp will let your LEDs follow the music played by your smartphone. The controller itself has also an audio input to process music directly on board.

![](http://souliss.net/images/2013-04/olimex-enc28j60.jpg?raw=true)

On the bottom of the main picture there are two microcontroller boards (AVR-T32U4 and Olimexino-328) and the relay board MOD-IO, is pretty similar to MOD-IO2 yet supported in Souliss bus has four relays instead of two and the four inputs are optoisolated.

We expect to include and test support for this Olimex hardware in few time, probably a couple of weeks, there are still other boards that we are interested too, these will came at a later stage.

Stay tuned!