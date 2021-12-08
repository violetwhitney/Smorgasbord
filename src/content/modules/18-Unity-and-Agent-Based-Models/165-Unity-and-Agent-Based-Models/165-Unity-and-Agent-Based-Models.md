---
moduleid: 161
title: Webhooks - Connecting IFTTT and Processing
published: True
slug: webhooks-connecting-ifttt-and-processing
---

Ambient Computing:
===========================================

# Webhooks: Connecting IFTTT and Processing
## Module Summary

[Webhooks](https://ifttt.com/maker_webhooks) allows you to make or receive a **web request** with IFTTT. A **web request** aka an **http request** allows software developers to request information from a website, such as data from an IFTTT sensor, or a street view image from Google. This means that we can get applications not yet supported by IFTTT, such as Processing, to talk to IFTTT. We will use Processing to create an HTTP request that will alert our webhook triggering an action in IFTTT. There will be three basic parts to linking IFTTT and Processing:

![processing-diagram](images/Webhooks-Connecting-IFTTT-and-Processing-diagram1.png#img-full)

- **Processing (HTTP request)** — here we can program our own unique triggers such as: a button, light level, sound, number of faces in a camera; to trigger our webhook. The important part is that we have all the necessary information in Processing (the **API key** for webhooks, and the right **“event name”** from webhooks. We'll talk about these terms in the tutorial.
- **Webhook (Trigger)**— when Processing triggers an HTTP request with our event name, webhooks will relay this trigger to the appropriate action based on the recipe we've created
- **IFTTT (Action)** — This can be any action from IFTTT as it normally works in IFTTT recipes.


## Conceptual Introduction
**On a technical level**, what is particularly important about learning how to work with webhooks is that it teaches us how to talk to all kinds of websites. By learning the basic structure of a webhook, we will learn what is typically required when talking with a website.

![processing-diagram](images/webhooks-11.gif#img-full)

**On a design level**, we're learning how to connect various "worlds" that don't usually talk to each other: Processing, IOT sensors, microservices. Designers that have a knack for connecting different "worlds" such as this will have much greater fluidity when prototyping ideas and a greater ability to innovate because they won't be bound by one "world's" capabilities. For example to prototype a Grasshopper plugin can only get you so far, but if you now learn how to connect Grasshopper with you phone, the two worlds have much greater cabalities together. 

**On a societal level**, this has cascading consequences for what designers can build, and thus will impact the spaces and technology they create. A designer who can connect the world of the web, with sensor technologies, with physical spaces, will have the ability to connect worlds that have never been united. Thus, these designers, will change the type of real world that we live in. One where interactions on the web don't require you spending your day in front of a computer screen, or clicking buttons on a tiny phone. One where web based interactions can be more contextually aware of where and when information is most relevant: i.e. getting pinged by a work email may not be relevant if you are at home with your family for Thanksgiving dinner.

**Ultimately** webhooks allow us to expand a spatial UX toolkit. We can think about user experiences in physical spaces and connect the world of the web with the physical world.

![processing-diagram](images/webhook1-12.gif#img-full)


## Tutorial
### Creating A IFTTT Recipe with Webhooks
1. sign in to [IFTTT](https://ifttt.com/home)
2. Go to `Create` → to create a new application
3. click on the **“this”** to choose our trigger. Search for **“webhooks”**. Select `webhooks`.

![processing-diagram](images/webhooks-1.gif#img-full)

4. Now click on the **“Receive a web request”** .
5. Create an **“Event Name”** for the trigger. I will just call mine **“turn_on”**. If you are creating a new event trigger, you should name this something unique. Then click `Create trigger`.

![blahblah](images/webhooks-2.gif#img-full)

6. Now we need to create our **“that”** event, click on the `that` button. Select any notification as you normally would. In our instance I will turn on an outlet from `Kasa TP-Link`.
7.Now select the Kasa TP-Link device that you plan to turn on.

![blahblah](images/webhooks-3.7.gif#img-full)
