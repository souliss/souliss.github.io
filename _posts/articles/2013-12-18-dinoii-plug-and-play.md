---
layout: article
title: "Lets start, DINo v2 full plug&play"
categories: articles
author: plinio_seniore
excerpt: "First attempts for auto-configuration nodes."
tags: [arduino, kmp electronics, rs485, ethernet]
modified: 2013-12-18
image:
  feature: 2013-12/DinoII-InputsB_EN.jpg
  teaser: 2013-12/DinoII-InputsB_EN-teaser.jpg
ads: false  
redirect_from: "2013/12/lets-start-dino-v2-full-plug.html"
---

After some time spent on tuning Souliss drivers for Wiznet W5200 Ethernet controller equipped on KMP Electronics DINo v2, we got a full support of new features included in new Alpha 5 with focus on plug&play.

Diving into the examples prepared for DINo you will found no longer need to set Quick Configuration paramters and IP configuration, that's the new inSketch mode included in the last Souliss release. Just load the example on your DINo and connect the boards to the network, they will join and be discovered by your Android smartphone automatically, doesn't matter your IP configuration.

Isn't magic, just using broadcast the boards will discover them-self and auto assign an address using a MAC-RAW (no IP) data exchange, then only the main (Gateway) board that has to be connected to Android get the IP configuration from the app itself. These features are of course available on all Souliss nodes regardless the communication media that is used.

All is included in new release A5.0.3 available in the [download](https://github.com/souliss/souliss/wiki/Downloads) area.