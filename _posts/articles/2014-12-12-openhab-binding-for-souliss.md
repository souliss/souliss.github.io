---
layout: article
title: "openHAB Binding for Souliss"
categories: articles
author: tonino_fazio
excerpt: "Get your Souliss network in openHAB with the new binding"
tags: [arduino, openhab, binding, souliss]
modified: 2014-12-12
image:
  feature: 2014-12/openHAB.png
  teaser: 2014-12/openHAB-teaser.jpg
ads: false  
redirect_from: "2014/12/openhab-binding-for-souliss.html"
---

Antonino and Fulvio has released for beta testing a native binding for openHAB that let use all functionality of Souliss.
Starting from the SoulissApp code written by Alessandro, Antonino has build a binding that connects directly to the Gateway using MaCaco/vNet event-based communication. 

Using this binding there is no longer need of an HTTP/XML interface on the Souliss Gateway, that means no additional resources (mainly RAM) are required.

![](http://souliss.net/images/2014-12/openhab1.png?raw=true)

Of course you can use SoulissApp and openHAB at same time, handling as default five connection (the value can be increased).

Using openHAB gives the freedom to build automation mixing Souliss with commercial products and offers a rule engine. In the screenshot of this post, the average temperature is used to control the heating system.

![](http://souliss.net/images/2014-12/openhab2.png?raw=true)

Actually this binding is not available in the list of openHAB official ones, because it still need some work in terms of coding, but soon will be released.

In the while, if you want to have a try, join the [mailing list topic](https://groups.google.com/forum/?fromgroups=#!topic/souliss/eU6XF8Ebwc4) and get the binaries in beta.