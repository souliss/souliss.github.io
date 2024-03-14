---
layout: article
title: "The new DINo is now available"
categories: articles
author: plinio_seniore
excerpt: "The new DINo is now available"
tags: [arduino, kmp electronics, dino 2, new dino, arduino relay board]
modified: 2013-11-03
image:
  feature: 2013-11/DinoII.png
  teaser: 2013-11/DinoII-teaser.png
ads: false  
redirect_from: "2013/11/the-new-dino-is-now-available.html"
---

It was more than one year ago when we announced the first supported hardware board, [the KMTronic DINo](http://souliss.github.io/2012/04/getting-kmtronic-dino.html), an Arduino Duemilanove compatible with four relays, opto-isolated digital inputs and an Ethernet interface based on Microchip ENC28J60. That board was also the first step into the uIP stack that actually powers Souliss over Ethernet interfaces that requires an IP stack in software.

That's why we are really in love with the DINo, also if most of our users gets hard time to find those board on the market and the design has some minor bugs. Recently the design moved from KMTronic to [KMP Electronics](http://kmpelectronics.eu/) and a new DINo has born.

Lets start from the new electronics design, that share some technical solution with our [RS-485 ones](http://souliss.github.io/2013/09/3d-rendering-for-new-rs-485-boards.html), the most important is the new power supply section that is now based on a DC/DC switching regulator (that's why you can see that big coil near the 12V screws terminal), this solves the over-heating of the previous DINo and will make easy to move into a 24V version  (DINo II has power range in 10 - 30V due to 5V coil relays).
More, the microcontroller is now the Atmel ATmega32U4, same as [Arduino Leonardo](http://arduino.cc/en/Main/arduinoBoardLeonardo) that result in a direct USB interface without the need for an FTDI USART to USB interface.
Last but not the least, there is no longer the Microchip ENC28J60 but Ethernet is now handled using the Wiznet W5200. This chip doesn't require (same as W5100) the IP stack in software and has a lower footprint in terms of RAM used on the microcontroller side.

The DINo II isn't yet supported in Souliss, but it will just need a small modification in the Wiznet libraries in order to move from W5100 to newer W5200, that will give full Souliss power (including of course Android support) to the new DINo.
More, the new Souliss Alpha 5 (available in preview on our support forum) is including configuration-less features, using that release a DINo (as all the others supporter by us) will became plug-and-play, no longer IP configuration needed.

We really hope to see Souliss Alpha 5 on DINo II as preloaded framework to have plug-and-play and Android support in minutes, we will update you soon.

Regards,
The Souliss Team.