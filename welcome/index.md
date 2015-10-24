---
layout: article
title: "Welcome in Souliss"
date: 2015-06-12T09:44:20-04:00
excerpt: "What's Souliss? Here you can found the answer!"
tags: [arduino, android, home automation, smarthome, openhab, internet of things, iot, openHAB]
image:
  feature:
  teaser:
  thumb:
share: false
ads: false
---

**The open-source SmartHome framework to empower your Arduino and Android devices**

*Souliss* is an open-source project that collects code and people with common interest in the field of SmartHome and Internet of Things. It's designed to be light and scalable, runs across multiple nodes and communication media.

You can use Souliss to build smart objects or an entiere home automation system based on Ethernet and RS485, create your own ZigBee-like wireless intelligent devices or simply to open your garage door from your Android smartphone.

## Our Internet of Things Vision

The Internet of Things (IoT) starts from your **Intranet of Things**, that's what Souliss does. It build a local network of connected devices, able to share data in *peer-to-peer* using an **event based** protocol, this lets you focus on your goal rather than on the development.

<p class="post-excerpt" align="center"><img src="{{ site.url }}/images/intranetofthings800.png" alt="{{ site.title }}"></p> 

Your **Souliss** network is an *Intranet* made of **Arduino** and compatibles devices that communicates over Ethernet, WiFi, wireless point-to-point and RS485 in a seamless peer-to-peer environment, one device will bridge your network to the *Internet*. The network layer is behind Souliss and is invisible for the users, each node has an its own identifier, you don't need to know nothing more.

## A Distributed Approach that goes in the Cloud

The underlaying layer works in a *peer-to-peer* environment so that your internal network is not affected by internet, compared to **cloud-only** devices you don't care if your internet is down, your basical functionalities will always be available and neither you have a single point of failure. 

You'll use Internet connectivity only when strictly required, as example to control your *Things* while you are abroad or when you need to interact with external cloud service (like schedule your objects via Google Calendar).

## Interact from your Smartphone and build Scenarios

Controlling your devices from your *smartphone* is straightforward, using **SoulissApp** for Android you can directly access your Things without relying on a central server, but if you need it a server can be used to build scenarios and get a webhook to cloud services. This is done through **openHAB** an open-source automation server that offer cloud and webservices for your smart objects and home.