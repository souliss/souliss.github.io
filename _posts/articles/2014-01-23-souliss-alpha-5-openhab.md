---
layout: article
title: "Souliss Alpha 5.1 is now close to openHAB"
categories: articles
author: plinio_seniore
excerpt: "Connect to openHAB using the HTTP Binding"
tags: [arduino, openhab, http, xml]
modified: 2014-01-23
image:
  feature: 
  teaser: 
ads: false  
redirect_from: "2014/01/souliss-alpha-51-is-now-close-to-openhab.html"
---

Yes, looks strange see an [XML](http://en.wikipedia.org/wiki/XML) picture in the Souliss blog. Is long time that we run away from ASCII protocols in order to save RAM and get impressive fast performance, and starting from Alpha 5 release branch all of those were deprecated, so now we are back with a new design. 

Starting from the next release a new operating mode called Data Persistance is available, it runs directly in MaCaco and store pass-through data in order to serve polling protocols. Those data are now stored into a separated area of the RAM that doesn't need any user care and doesn't affect any other operation.

Under the skin this design is quite far from release Alpha 4 and works seamlessly even if the Data Persistence mode isn't active (of course, only local data will be available) either on Gateway and Peers. 

From the user point of view, a new Interface based on HTTP/XML has been developed in order to have a smooth integration with [openHAB](http://www.openhab.org/) HTTP binding, this design is by Fulvio and has simpler approach compared to the previous HTTP/JSON.
As most, there is no longer a complex data structure that contains the complete network, but a flat XML with information regarding a unique type and a unique node; this makes the parsing easier and can be handled easily using the REGX available in openHAB.

More details are available on the [forum](https://groups.google.com/forum/?fromgroups#!topic/souliss/0RP_1eIg4ls).