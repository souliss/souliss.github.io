---
layout: article
title: "Post data to Xively"
categories: articles
author: plinio_seniore
excerpt: "Post data to Xively"
tags: [arduino, xively, ethernet, smarthome]
modified: 2013-12-28
image:
  feature: 
  teaser: 
ads: false  
redirect_from: "2013/12/post-data-to-xively.html"
---

As a complete distributed system, Souliss miss most of the features related to the Internet of Thing world. 
Actually we are working to define the future of the development activities that will be based on the [Zozzariello](http://souliss.github.io/2013/09/souliss-webserver-codename-zozzariello.html) concept.

![](http://souliss.github.io/images/2013-12/Schermata 2013-12-28 alle 10.18.07.png?raw=true)

Basically, your hook to the internet world will be your Android smartphone, because is one of the most used operative system and in the time it will growth the number of "old" and used devices.
We always looked to a less-is-better in terms of hardware, and using an "old" Android device as home server is in our philosophy.

When Zozzariello will get out from the concept, you can have a Souliss home server based on an home tabled or even on your mobile device (based on how much IoT reliability you are looking for).

In these days Tonino has released a [Xively](https://xively.com/dev/docs/api/) push application that fetch data from SoulissApp using the HTTP/JSON embed server included in the Zozzariello branch. Data from your Souliss network can be pushed out easily with a simple UI setup that can be done directly on Android.

This is just one step into the IoT features that we are building around Souliss, because thanks to Yaler servers, we will include the ability to reach out a Souliss network from the internet without any setup on your router, as standard IoT product does.
Our key is that a project that has been designed as distributed can even work locally without any loss of features, that is what most of actual commercial product hasn't.

![](http://souliss.github.io/images/2013-12/Screenshot_2013-12-27-15-42-10.png?raw=true)