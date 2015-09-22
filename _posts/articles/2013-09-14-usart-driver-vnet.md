---
layout: article
title: "USART Driver for vNet"
categories: articles
author: plinio_seniore
excerpt: "A peer to peer communication over RS485"
tags: [arduino, android, rs485, peer to peer, bus. vNet, souliss]
modified: 2013-09-14
image:
  feature: 
  teaser: 2013-09/vNet over USART.jpg
ads: false  
redirect_from: "2013/09/usart-driver-for-vnet.html"
---

People that follows Souliss blog from long time probably know about a working idea that started with Marco Signorini from Ethermania. It came up as an Arduino based RS-485 board and moved to the design of a power+data bus at 24V, most of it is documented on this [topic](http://forum.arduino.cc/index.php/topic,97347.0.html) of the Arduino forum.

There was a lot of work out of the topic, we get a final design but end up that was too similar to commercial project and quite risky, so after some time we moved back to the old idea of RS-485 with the idea to make the board even simpler.

One of the challenging is using an RS-485 connection with Souliss, because that standard came up at time of master/slave communication and electrically an RS-485 driven doesn't allow a peer-to-peer communication, because doesn't allow a listen back for collision detection.
At time of the first Ethernet (10-BASE2), it was basically a modified RS-485 for collision detection with a dedicated transceiver, this is now no longer supported in common transceiver. So, we get inspired by [uLAN](http://ulan.sourceforge.net/index.php) and we are start to design a collision avoidance driver that will run into vNet, in the top image there is the first run between two boards.

![](http://souliss.net/images/2013-09/Domoduino12_Proto_2.jpg?raw=true)

The plan is to design three boards based on RS-485, all based on ATmega328 with the followings:
A relay board, with three (3) relay and direct contact inputs (just wire the standard wall push-button in);
A LED board, with 8 or 12 channels (based on space) and direct contact inputs;
An input board, just with inputs.
Thanks to vNet, this boards can join the Souliss network throught a bridge that will be based on a classic Ethernet board with a RS-485 shield, where one or more bridging can be used according to the topology of the network and number of nodes.

Is still a big question mark and we are just at the begin, finger crossed!

Stay tuned,
Dario. 