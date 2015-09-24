---
layout: article
title: "Controlling cheap RC Power Socket"
categories: articles
author: plinio_seniore
excerpt: "A cheap Androidification for 433 MHz RC Power Socket"
tags: [arduino, android, 433 mhz, cheap, rc socket]
modified: 2013-09-16
image:
  feature: 
  teaser: 2013-09/rcswitch-teaser.jpg
ads: false  
redirect_from: "2013/09/controlling-cheap-rc-power-socket.html"
---

It was just three days ago when Christian [makes a knock](https://groups.google.com/forum/?fromgroups#!topic/souliss/F_VheIs5Te8) in the forum, he triggered a set of common RF Power Socket at 433 MHz using [RCSwitch](https://github.com/sui77/rc-switch) and was then working for an integration with Souliss, adding Android control was the goal.

![](http://souliss.net/images/2013-09/rcswitch.jpg?raw=true)

After few steps the sketch was complete and this is the result:

Lets have a look in detail:

<iframe width="560" height="315" src="https://www.youtube.com/embed/S5AaDj3JlFk" frameborder="0" allowfullscreen></iframe>

These socket use a simple ASK modulation to transmit data over the air, there are cheap transmitter and receiver available over internet, [Seeedstudio offer them at 4.90 $](http://www.seeedstudio.com/depot/433mhz-rf-link-kit-p-127.html). There are not "intelligent" devices and hasn't the features of more complex radio like the Atmel AT86RF230 transceiver actually supported in Souliss, just send (modulation is care of the MCU) and receive data, all the other stuff shall be carried out into the microcontroller.

In this case, these sockets just goes ON and OFF and doesn't provide any feedback, a transmitter will do the job. Of course you need a receiver to get the code from the original remote, in order to replicate them over the air and control the sockets.

Most of this devices are based on standard encoder/decoder (SC5262 / SC5272, HX2262 / HX2272, PT2262 / PT2272, EV1527, RT1527, FP1527 or HS1527) this are used in almost all of these sockets, so the same code base will work for (almost) all of them.
In order to make things easier, Christian used RCSwitch that gives a simple set of APIs to interact with your sockets, mixing those with Souliss and the sockets became Android controlled.

That's all, we will prepare as soon a tutorial with Christian to track the small steps needed to get your sockets in Souliss.

Stay tuned,
The Souliss Team.