---
layout: article
title: "Ciseco XinoRF, update over the air!"
categories: articles
author: plinio_seniore
excerpt: "Arduino UNO style with RF and OTA."
tags: [arduino, ciseco, usart, rf transmission]
modified: 2013-12-01
image:
  feature: 
  teaser: 2013-12/XinoRF-teaser.JPG
ads: false  
redirect_from: "2013/12/ciseco-xinorf-update-over-air.html"
---

Today we got new Twitter follower, [Ciseco](http://shop.ciseco.co.uk/), an UK electronic designer and producer in the area of Arduino and compatibles. I've dived a bit into their website and found some interesting product. Basically they use a Texas Instrument SoC (the C1110) to span USART messages to the air, like most simple OOK transmitter and receiver, but whit a complete MAC layer offered by the radio embedded in the SoC.

Is something similar to [AirQ](http://www.souliss.net/2013/04/do-it-wirelessly-with-airq-boards.html) products, but with a more important feature, they just move USART as in over the air, without adding a middle layer in between, so you can even update wirelessly your boards (I'm expecting that just the board to be updated must be powered).

So, is a mere broadcasting and you need a software layer over, that's the most interesting feature. Using [XinoRF](http://shop.ciseco.co.uk/xinorf-100-arduino-uno-r3-based-dev-board-with-radio-transciever/) (or generally the stand-alone [XRF radio](http://shop.ciseco.co.uk/xrf-wireless-rf-radio-uart-rs232-serial-data-module-xbee-shape-arduino-pic-etc/)) need an application and transportation layer, a piece of code that cares for message delivery and parsing, that's what Souliss has with MaCaco and vNet.

I haven't those boards in my hand, but reading their docs, looks that [vNet USART drivers](http://www.souliss.net/2013/09/usart-driver-for-vnet.html) will work out of the box (just need to enable the radio in the setup) and the collision avoidance that we handle in software will not strictly be required, because the C1110 has an its own MAC layer that cares about.

I really hope that a common path can be found with Ciseco, because their hardware looks cool and can be easily mixed with Souliss. Maybe they are interested too.

Stay tuned!
Dario.