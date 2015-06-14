---
layout: article
title: "Getting Started with Souliss"
date: 2015-06-14T13:57:25-04:00
modified:
excerpt:
tags: [arduino, android, smart home, home automation, avr, esp8266, ethernet, wifi, rs485, wireless]
image:
  feature:
  teaser:
  thumb:
share: false
---

Lets see what Souliss does and how can fit for you.

## Introduction

Souliss is build in three main parts, listed below:

* [The Arduino Networking Framework](https://github.com/souliss/souliss) : This is the code that runs on your Arduino and compatible boards, it network your boards and is the base structure of your automation system.

* [The Android Application](https://github.com/souliss/soulissapp) : This is an application that can communicate directly with your automation system, it learns from the nodes their features (light, door, windows or whatever they control).

* [The openHAB Binding](https://github.com/souliss/bindingopenhab) : This bind your Souliss nodes with the openHAB automation supervision system, this provide you a server to control your automationa and make advanced schedules. More with openHAB it lets you control multiple vendor system through an unique interface, so that you can use Souliss based devices togheter with other commercial ones.

Is at your option to decide to use the Android Application or the openHAB Binding, you can even use both at same time.

{% include toc.html %}

## Get Started

The first step in is a tour in the [wiki](https://github.com/souliss/souliss/wiki), this gives you a detail understanding of the features and capabilities. The most important pages to read are:

* [Supported Hardware Platforms](https://github.com/souliss/souliss/wiki/Supported%20Hardware%20Platform) : Identify how you nodes will be build and the communication medias (Ethernet, Wireless point-to-point, RS485).
* [Suppoerted Network Architectures](https://github.com/souliss/souliss/wiki/Supported%20Network%20Architecture) : Understand how you can combine multiple communication interface
* [Getting Started](https://github.com/souliss/souliss/wiki/Getting%20Started%20with%20Souliss) : Now you are ready to goo deeper, start from the first upload guide.

Some others useful wiki pages: <a href="https://github.com/souliss/souliss/wiki/Your%20First%20Upload" class="btn-info">Step by step upload</a> <a href="https://github.com/souliss/souliss/wiki/Framework%20Configuration" class="btn-info">Configure a sketch</a> <a href="https://github.com/souliss/souliss/wiki/SoulissApp" class="btn-info">Use SoulissApp</a> 
 
### Required skills

Souliss is quite simple to use, but the following skills are required to get a network up and running. Consider that as average you can get a first node working in less than an hour,

* A general understanding of the Arduino world and its IDE to program the nodes,
* A basic knownledge of electronics and eletricity,
* A little knowledge of networking (basically the IP protocol).

## Build products based on Souliss

You can build nodes with Souliss pre-compiled and loaded, so that people can just install and use it. Souliss code is distributed under license GNU GPLv3, and there is no fee to use it, but you should contribute back if you are modifing the code as per license constrains.
At your option you can require us to re-license the code.

## Community

As open-source project, Souliss based on a community of people that share their work. You are suggested to join the [community](https://github.com/souliss/souliss/wiki/Community) to get support and share your result.

The following languages are available:
<a href="https://groups.google.com/forum/#!forum/souliss" class="btn-info">English</a> <a href="https://groups.google.com/forum/#!forum/souliss-it" class="btn-info">Italiano</a> <a href="https://groups.google.com/forum/#!forum/souliss-es" class="btn-info">Espanol</a>

**Be Aware:** The [**Community**](https://github.com/souliss/souliss/wiki/Community) is a mailing list of `volunteers` that help each others in improve their object and home empowered with Souliss. If you are using Souliss on a product, consider to get a `premium` support, contact us for details. 
{: .notice-warning}

## Contribute and Promote

You can contribute and promote Souliss in several ways and isn't required to be a programmer or an electronic designer:

* Share on social media ([twitter](https://twitter.com/soulissteam), [G+](https://plus.google.com/113934123042484468682/posts)) and with friends, show them your Souliss installation and help them to get started
* Partecipate in the [community](https://github.com/souliss/souliss/wiki/Community), help other people and share your results
* Fork the code and [contribute](https://github.com/souliss/souliss/wiki/Contribute) in the development
* [Donate](https://pledgie.com/campaigns/27771) to support the expenses and development

If you want to share your code, refer to [contribute](https://github.com/souliss/souliss/wiki/Contribute) page in the wiki.

**Support and Donations:** As all `community driven` project, also here all contribution to support the projects are welcome. [**Donations**](https://pledgie.com/campaigns/27771) are used to cover expenses.
{: .notice-success}

**Enjoy!**