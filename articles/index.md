---
layout: archive
title: "Blog Post"
date: 2014-05-30T11:39:03-04:00
modified:
excerpt: "We share here our mind, goal and achievements."
tags: [arduino, android, iot, internet of thing, smart home, home automation, souliss, esp8266]
image:
  feature:
  teaser:
---

<div class="tiles">
{% for post in site.categories.articles %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->