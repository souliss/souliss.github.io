---
layout: article
title: "Souliss, what's next?"
categories: articles
author: plinio_seniore
excerpt: "Lets see what will be available in the next releases."
tags: [arduino, android, smart home, internet of things, home automation, souliss]
modified: 2013-04-01
ads: false  
redirect_from: "2013/04/souliss-whats-next.html"
---

It's again time to point out where we are and where we would go next. It was just last summer when we released Souliss Alpha 3, it was the first step into the expansion of the supported boards, because included in Souliss a software TCP/IP stack required by most (but not all) of Ethernet controller.

The release Alpha 3 wasn't enough, the stack were working but the performances was too low, due to the few kilobytes of RAM available we was obliged to split the IP packet sent to the user interface, that gives a slowly response. At that time, the only protocol available for user interfaces was HTTP/JSON and it's ASCII nature makes the exchanged frames too big for a low performance device.

This was the spark for the new Souliss, the release Alpha 4 came out near six month later with a new concept behind, the MaCaco binary protocol that up to A3 were used only between boards was extended to the user interfaces (so the SoulissApp Android application) and a new data structure and Modbus support was added. That's the new Souliss.

Is now time to complete and hopefully came out from the Alpha stage, Souliss will include in few time a nice number of boards, most of them were previewed and are from different manufactured like Olimex, AirQ and some will be from Open Electronics. The next step will be the configuration.

Starting from release Alpha 4.1, that include different (but still not all) Olimex boards, there is a QuickConfiguration tool, that has a single entry point for the configuration needed before the compilation and loading on the board, but this is still not enough.
The main goal is make Souliss pre-loadable, to let load the code and then configure the network parameters later, in the future the standard functionality will not require to compile and load the board if is pre-loaded. One more important point will be a new concept of gateway node, that will allow pass-throught, saving RAM and increasing the number of nodes that can join a network.

So, we are starting now the design for the new Alpha 5, we hope to be fast enough to have it in few months, in the while there will be probably some sub-release for Alpha 4 including bugfix and additional hardware support.

Stay tuned and have a good Easter!