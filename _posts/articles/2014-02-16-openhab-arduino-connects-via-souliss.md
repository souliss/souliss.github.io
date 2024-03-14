---
layout: article
title: "openHAB and Arduino, connects via Souliss"
categories: articles
author: plinio_seniore
excerpt: "Demo video, connect to openHAB using the HTTP Binding"
tags: [arduino, openhab, http, xml]
modified: 2014-02-16
image:
  feature: 
  teaser: 
ads: false  
redirect_from: "2014/02/openhab-and-arduino-connects-via-souliss.html"
---

As [announced in a previous post](http://souliss.github.io/2014/01/souliss-alpha-51-is-now-close-to-openhab.html), there is an active job in the integration between openHAB and a network of Arduino (and compatible) nodes using Souliss. The communication goes from [openHAB HTTP binding](https://github.com/openhab/openhab/wiki/Http-Binding) to an Arduino that acts as Souliss gateway, collecting data from all others Arduino running Souliss as peer even if they aren't using Ethernet.

In the video Fulvio shows how is operating a DINo (Arduino with relay and Ethernet) via openHAB web interface. While integrating via openHAB the network of Souliss nodes is still operable via SoulissApp for Android.

<iframe width="420" height="315" src="https://www.youtube.com/embed/mQxXwgrfl_0" frameborder="0" allowfullscreen></iframe>

The official release will be available soon, for now you can get the code in the relevant topic and follow the discussion on the integration via the [Google group](https://groups.google.com/forum/?fromgroups#!forum/souliss).