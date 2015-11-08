---
layout: article
title: "Are you lazy enough? Automate and Tasker integration"
date: 2015-11-08
categories: articles
excerpt: "Happy laziness, less tap on your smartphone screen with the Automate and Tasker integration in SoulissApp"
author: plinio_seniore
ads: false
image:
  feature: 2015-11/happy-laziness.jpg
  teaser: 2015-11/happy-laziness-teaser.png
---

Laziness is a life style and tap your finger on the smartphone screen looking for the button to dimmer out lights or do any other routine action is boring as step-up to the wall button. Wouldn't be nice if your smartphone can propose you what you need?

![](http://souliss.net/images/2015-11/dialog-suggestion.jpg?raw=true)

Is not yet time for an Artificial Intelligence that learns your habit, it will likely be in the next future but our laziness cannot wait, so starting from SoulissApp 1.6.1 any other Android application can interact through [Intents](http://developer.android.com/guide/components/intents-filters.html).

A special Intent is the [Tasker Plugin](http://tasker.dinglisch.net/plugins.html), that is supported by [Automate](https://play.google.com/store/apps/details?id=com.llamalab.automate&hl=en), [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en) and other Android application that lets build If-Then-Else rules based on sensors and internet data.

There are two types of plugins, the Action Plugin can be used to send command through SoulissApp as you were using Voice Commands, the [wiki has more details](https://github.com/souliss/souliss/wiki/SoulissApp-API) but basically you just have to write something like **turn on bedroom lights** where you have a set of keyword like *turn on, turn off, open, close* and others that shall be followed with the name that the target device has in SoulissApp

![](http://souliss.net/images/2015-11/ActionPlugin.jpg?raw=true)

As well a state can be retrieved in a similar way using the Conditional Plugin, having a True/False statement as result.

![](http://souliss.net/images/2015-10/ConditionPlugin.png?raw=true)

We will soon start to release examples for Automate and Tasker, but the SoulissApp Plugins will generally be the last step in your flow, there are several example that can be build and fully customized based on your needs:

* Using the light sensor of your phone, in the evening and if connected to your home WiFi, a notification can ask you if you want to lower the brightness of your lights in the living room,
* Using the GPS or Cell Tower position to open automatically the Garage Door or ask with a notification if you want to open it,
* Catch the sunset using an online service and turn gradually on an [LYT Bulb](http://souliss.net/articles/multicolor-wifi-bulb-arduino-based/) with a warm yellow.

The release 1.6.1 of SoulissApp is in preview on the [mailing list](https://github.com/souliss/souliss/wiki/Community) and will be available in the [Play Store](https://play.google.com/store/apps/details?id=it.angelic.soulissclient) in few days.

Have fun!