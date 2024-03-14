---
layout: article
title: "Planning New Hardware"
categories: articles
author: plinio_seniore
excerpt: "Designing new hardware with Ethermania."
tags: [arduino, enc28j60, relay board, 220 volt arduino, android, internet controlled]
modified: 2012-05-09
ads: false  
redirect_from: "2012/05/planning-new-hardware.html"
---

Provide hardware solution for home automation is one of the main goals of Souliss project, and after the first releases of the Souliss framework we are getting the interest of some hardware developers to include their hardware in Souliss.

![](http://souliss.github.io/images/2012-05/ArdDomo.jpg?raw=true)


The first one (that is still in progress) is the [DINo](http://souliss.github.io/2012/04/getting-kmtronic-dino.html) by KMTronic, to support this board we are working on the ENC28J60 including the uIP stack in vNet, this will integrate ENC28J60 based boards (like DINo) in Souliss vNet networks.

A new board is adding in the Souliss world, it will be designed and produced by Marco Signorini from Ethermania and there is a [open discussion](http://arduino.cc/forum/index.php?topic=97347.new;topicseen#new) where we contribute in the design. The board from Marco is RS-485 and is designed with the goal of a small footprint in the mind.
The design is ongoing and the discussion is focused on using power supply (moving from 5V to 12/24V) and overall efficiency of the board.

Regards,
Dario.