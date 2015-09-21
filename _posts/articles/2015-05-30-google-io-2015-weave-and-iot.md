---
layout: article
title: "Google I/O 2015 : Weave and the IoT"
categories: articles
author: plinio_seniore
excerpt: "BigG just announced their plans for IoT and its standardization"
tags: [souliss, arduino, esp8266, wifi]
modified: 2015-04-30
image:
  feature: 
  teaser: 2015-05/io15-teaser.jpg
ads: false  
redirect_from: "2015/05/google-io-2015-weave-and-iot.html"
---

At I/O conference Google has introduced Weave, their protocol to standardize the communication between IoT devices, this isn't a new concept but Google can be strong enough to let Weave spread across devices and became a de-facto standard.

The only information that we actually have is a slide from the I/O talk, but the way Weave has been introduced lets assume that the protocol will allow devices to be discovered and able to describe their-self. A native support for Weave will be included in Android M with API exposed to App developers.

This open a new scenario, where any Android app can access Weave based devices, as example a generic weather app can activate your sprinkler system to water your plants, without need a bind with the technology behind your sprinkler system.

If we look back, this was quite similar to a design that we tried to start a couple of years ago, just after Zozzariello an internal discussion on how to share data between application has been live for months, but nothing comes out. That's simply because after the design you need to be strong enough to get that protocol used, and of course we aren't.

**So, what will be the impact on Souliss?** Is simply a big opportunity, Souliss has yet an approach that let the nodes to be discovered and provide details on what they can do and it use a standardize communication between nodes using Typicals. Those are the features that Weave want to bring out in the cloud.

Souliss has been focused on Arduino AVR nodes, that generally are low performances devices that are not suitable to process complex ASCII protocols, the time will give more Arduino powerful devices, but that's not the way we want to follow. We will run a compatibility layer on SoulissApp and openHAB.

**The Hardware-less approach**, has been introduced with Zozzariello, it means improve without have to change your hardware. To keep a server-less approach SoulissApp will expose Weave through Zozzariello, that's basically the same that happen now with an our own JSON structure.
A server based approach will probably be based on a service that can run on a 24h powered home device, like a Raspi with openHAB.

This assume that Weave will be free for use and that the certification program will not be mandatory.

The release of Weave is expected at the end of the year, so we should still wait some months before know if it will became the IoT protocol.

Stay tuned!