---
layout: article
title: "Souliss, what's next"
categories: articles
author: plinio_seniore
excerpt: "Thinking out loud."
tags: [arduino, fks, bfks, oscilloscope]
modified: 2012-08-12
ads: false  
redirect_from: "2012/08/souliss-whats-next.html"
---

It is now time to plan the next features that Souliss requires to grow and become more usable. Basically, now there are some old ideas that weren't implemented at the begin, just to save time and release the code quickly.

Embedding the TCP/IP stack into the network layer (vNet) for the ENC28J60 support let us go back to the old idea of an user interface directly integrated into the Souliss framework, that means an event-driven binary protocol to share data with boards.
Actually the interaction is done via an ASCII polling protocol (JSON) commonly used for web application and generally quite simple to use, that's also one more interesting feature, JSON share not only the data but the whole database structure in a quickly way. This give us the opportunity to build an auto-configured user interface based on Android.

![](http://souliss.net/images/2012-08/mblogic.png?raw=true)

So, JSON is nice, but what's the problem? Sharing data using an ASCII protocol needs more bytes rather than a binary one. Handling this complexity with low performance microcontrollers result in a waste of RAM and CPU for more important features. With Alessandro we are working to include in the future Souliss Android App the binary protocol used for the boards, with some minor modification to handle the user interface.

Furthermore, as now the integration of an external user interface require dedicated code for the JSON parsing, this result in lack of user interfaces. So we would move to more standard protocol, Modbus. The JSON gateway will still remain a supported solution, but only for W5100 based boards, because the JSON  impact on RAM and CPU with an hardware TCP/IP stack is acceptable; for the ENC28J60 the support for JSON (actually available) will be removed, giving priority to binary protocols.

So, the integration with Android will be a sort of native, rather for others user interface Modbus and JSON will be the available options. Both protocols will be available over TCP/IP and virtual RS-232, so Modbus will be either TCP and RTU.

With Modbus potentially all the open source SCADA solution will became a supported user interface panel, like MBLogic, a nice and tiny Python open source HMI Server with Modbus support. Unfortunately this project looks no longer updated, we are trying to contact the authors.

User interfaces will not be the only working field, because still there is the FSK-bus board designed with Ethermania, for this board a draft of working drivers is yet available, and a lot of work is still required.

There are lots of things, hopefully all will be implemented. Idea and collaborations are always appreciated.

Stay tuned.

Regards,
Dario.