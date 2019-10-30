---
layout: article
title: "SoulissApp Android 10 update"
categories: articles
author: shine_angelic
excerpt: "SoulissApp updated to Android Q"
tags: [soulissapp, android]
modified: 2019-10-30
ads: false  
image:
  feature: 2019-10/Screenshot_home.png
  teaser: 2019-10/env.png
  creditlink: https://github.com/souliss/soulissapp/releases/tag/2.3.2
---

Updating soulissApp is both a pleasure and a pain. Proud of mantaining a 7 years old app, born under Android 2 _Gingerbread_ environment, it still takes some old legacy dependancy with it and several spiderwebs. Hard to update and/or mantain, especially because of the earthquaking environment. But it still works, I "just" had to redo backgroud services and remove much legacy code. This new version is compiled **targeting sdk 29**, aka Q, Android 10, but the biggest changes came adapting to previous Android's major release.

![New permissions request modal](http://souliss.net/images/2019-10/Screenshot_permission.png)
![new settings screen](http://souliss.net/images/2019-10/Screenshot_settings.png)

Demo mode has been temporanely removed, as the public IP isn't available any longer. Write us if you can host one and are willing to.

Please be patient, as this software is entirely free. As always, I'd be glad to receive some pull request and/or translations

**CHANGELOG:**
Quite a long list, even though it doesn't look so. 

 * Preferences screen entirely re-made according to new [Settings](https://developer.android.com/guide/topics/ui/settings/) API.
 * Watchdog died. He was a good boy, but Android now [forbids receiving system Intents](https://developer.android.com/about/versions/pie/android-9.0-migration)
 * Because of Android 8.0 [Behavior Changes](https://developer.android.com/about/versions/oreo/android-8.0-changes), SoulissDataService has been deeply slimmed
 * New Font style, merged old (API < 19) ones
 * Several useless lint suggestions/forced changes
 * Migrated some dependency to [Jetpacks](https://developer.android.com/jetpack/). I don't even know what does it mean, frankly.
 * Several once-fine deprecated methods updated

