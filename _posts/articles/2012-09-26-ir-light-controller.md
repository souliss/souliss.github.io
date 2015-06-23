---
layout: article
title: "IR Lights Controller"
categories: articles
author: plinio_seniore
excerpt: "Control an IR Lamp."
tags: [arduino, infrared, IR, lamp, led bulb]
modified: 2012-09-26
image:
  teaser: 2012-09/IR_controlled_lamp.jpg
ads: false  
redirect_from: "2012/09/ir-lights-controller.html"
---

Souliss Client is going to support common IR remote controller, to manage LED spotlights and strips. LED spotlight are becoming common, at least to replace old power-consuming halogen ones, and coloured ones are getting very common and cheap. The remote controller seems to be [quite easy to reproduce](https://docs.google.com/spreadsheet/ccc?key=0Aupzmp8AqC8JdFBObkk1b21tSVROYl95NS0xUHlJT2c), since it uses NEC IR protocol already supported by [Ken Shirriff's legendary](http://www.arcfn.com/2009/08/multi-protocol-infrared-remote-library.html) arduino library.

![](https://github.com/souliss/souliss.github.io/blob/master/images/2012-09/IR_controlled_lamp.jpg?raw=true)

In order to support InfraRed operations, a Souliss typical was developed to control such lights: the typical supports all infrared commands, allowing a full control from your smartphone even when you're far from home. You can also define scenes and/or programs to automate lights' behaviour, and use other IR controlled devices from the same Souliss node. 

Stay tuned to get more info!