---
layout: article
title: "Automate with Automate"
date: 2015-11-28
modified:
categories: media
excerpt: "Integrated with SoulissApp, Automate free yourself from repetitive task."
author: plinio_seniore
ads: false
image:
  feature: 2015-11/Automate-splash.png
  teaser: 2015-11/Automate-splash-teaser.jpg
  credit: https://play.google.com/store/apps/details?id=com.llamalab.automate&hl=en
---

After quite a lot of words on the integration of [SoulissApp with Automate and Tasker](http://souliss.net/articles/soulissapp-integrations/) through [intents and plugins](http://souliss.net/articles/happy-laziness-automate-tasker/), is now time to have a detailed look on how to get it working.

We focus on Tasker Plugin that is a set of open API supported from multiple Android software like Tasker (of course) or Automate that will be covered in this tutorial. The Plugin allow an interaction with Souliss via common language like *turn on the living room light* or *is the living room light on?*.

> Using Automate you can have preemptive notification, that asks you if you want to perform common task based on time, position or other condition (open app, accelerometer sensor of the smartphone)

![](http://souliss.net/images/2015-11/dialog-suggestion.jpg?raw=true)

** Execute an Action or take Decision  **

![](http://souliss.net/images/2015-11/AutomatePlugin.png?raw=true)

In the flow editor, included in the APPS menu there are the two Plugin that can be used with SoulissApp, the Action and Decision. The former is used to execute an action, the latter to take a decision based on the state of a device in SoulissApp.

So you can turn on the *Main Light* using the **Action** one or,

![](http://souliss.net/images/2015-11/ActionPlugin.jpg?raw=true)

Check if the *Main Light* is on using the **Decision** one

![](http://souliss.net/images/2015-10/ConditionPlugin.png?raw=true)

These two Plugin can be used in any Automate flow, even if this is not a full Automate tutorial, lets see how we can build simple conditional actions.

** Recursively check for a condition with Forks **

Flows are easy to use but needs recursive check to be effective, the flow in the below picture checks for a time frame and later show a notification if the ambient light cross a threshold value.

![](http://souliss.net/images/2015-11/Automate-not-recursive.jpg?raw=true)

Once started the flow will wait for a time frame, after 9 PM it enters in the next step and check for the ambient light using the embed sensor of the smartphone. If in the time frame the ambient light is too high,it will show a notification and will ask the user if he want to lower the brightness.

That's works nice if after 9 PM you cross the threshold, if not the flow will check the light value and waits there. So, the morning after you will likely get the notification even if this wasn't your goal.

> You need a recursive check of a condition using parallel flow, those are called Fork. In Automate Flows can interact with their Forks but not with other Flows.

![](http://souliss.net/images/2015-11/Automate-recursive.png?raw=true)

Having a recursive check needs a dedicated fork, like in the above picture. It first checks if connected to *Plinio* WiFi network (set it as *Immediately*) is not it holds on the same check with *On Change* parameter. This will not drain your battery while waiting for a change in the connection state.

Once connected, it starts a fork that will be a new flow starting from that point that will do something else, and checks again the WiFi state *On Change*, if the connection is lost it will stop the fork and restart the flow. So in this way you are recursively checking for the WiFi state and your flow will stop at every time if this condition is missed.

This applies to any block as a time frame or else, **after the fork you can apply the same scheme** creating multiple condition in AND, like check for *WiFi and time frame*. 

** Create Custom Interaction **

Even if the Plugin allow few commands like [*turn on, turn off and toggle*](https://github.com/souliss/souliss/wiki/SoulissApp-API) you can create custom and complex interaction with dedicated code on your node.

Lets assume that you have three LYT bulbs and you want to set a *Movie Time* to lower the switch off two of the three bulbs and use a low brightness amber light, this quite complex state can be achieved with a custom action defined in your node.

In the *Gateway* node include a set of pushbutton as [T14](https://github.com/souliss/souliss/wiki/Typical_T1n#typical-14--pulse-digital-output) and configure them to  [broadcast a topic](https://github.com/souliss/souliss/wiki/Peer2Peer#user-defined-publish--subscribe), like in this case *LowMood, FullLight and MediumLight*.
 
In this way any other node in your network can listen for this topic and apply the required changes.

{% highlight c %}

...

#define LowMood                                 0xFF01,0x01
#define FullLight                               0xFF01,0x02
#define MediumLight                             0xFF01,0x03

...

void setup()
{ 
  ...

    Set_T14(PUSH1);
    Set_T14(PUSH2);
    Set_T14(PUSH3); 
}

void loop()
{
  ... 

    FAST_110ms() {

    // LowMood Command
    if(Logic_T14(PUSH1))
        if(mOutput(PUSH1))  publish(LowMood);

    // Full Light Command
    if(Logic_T14(PUSH2))
        if(mOutput(PUSH2))  publish(FullLight);

    // Full Light Command
    if(Logic_T14(PUSH3))
        if(mOutput(PUSH3))  publish(MediumLight);
    }
}
{% endhighlight %}

On the node side, as example

{% highlight c %}

...

#define LowMood                                 0xFF01,0x01
#define FullLight                               0xFF01,0x02
#define MediumLight                             0xFF01,0x03

...

void loop()
{
    ...
    // Listen for topic published by other nodes
    FAST_110ms() {
    
        // Set LowMood
        if(subscribe(LowMood))
        {
            // Do something
            ...
        }

        // Set Full Light
        if(subscribe(FullLight))
        {
            // Do something
            ...
        }

        // Set Medium Light
        if(subscribe(MediumLight))
        {
            // Do something
            ...
        }
}
{% endhighlight %}

At this time you will get on SoulissApp the three T14 that can be renamed as you like and be activated from the Plugin.

> Automate extend SoulissApp features and gives sense to your automation

So, what if you smartphone **will preempt you asking if you want to lower the light?** This give sense to your automation that is no longer a simple remote control.

What if SoulissApp will be **able to recognize when you and your family are at home?** Simply build a flow that periodically trigs a state (one for each people at home) when you enters at home and connect to your WiFi, use a timer on the node side to clear the state. This will show when you are at home and any node can benefit from.

What if you build a **shortcut that open your IPCamera app and at same time turn on the lights** without have you to dig in SoulissApp?

Enjoy!



