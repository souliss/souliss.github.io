---
layout: article
title: "Planning New Hardware / 2"
categories: articles
author: plinio_seniore
excerpt: "Designing new hardware with Ethermania."
tags: [arduino, enc28j60, relay board, 220 volt arduino, android, internet controlled]
modified: 2012-06-12
ads: false  
redirect_from: "2012/05/planning-new-hardware.html"
---

As discussed some weeks ago, there is an interesting design by Marco Signorini from Ethermania, that now is in the prototyping phase.

The board is equipped with three relays and four configurable I/O with an RS485 driver interfaced to the uC serial port. In the actual design can be powered either at 12 or 24 V due to the use of an onboard DC/DC switching regulator.

The switching regulator offer a suitable efficiency above 70% in test conditions, providing 5.4 V at 430 mA with an input voltage of 31.4 V. A linear regulator with the same input-output drop (26 V) can offer an efficiency near to 20%, out of the heat constrains. The board can work either at 12 or 24 V, and is related to the equipped relays that gets the supply directly from the inlet feed.


![](http://souliss.github.io/images/2012-06/Domoduino12b.png?raw=true)

Souliss will support this board in the framework, using dedicated drivers for RS485 management. A peer-to-peer driver with collision management it will be the goal to fully support this board.

Thanks Marco!

Regards,
Dario.