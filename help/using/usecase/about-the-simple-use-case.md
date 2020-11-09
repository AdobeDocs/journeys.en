---
title: About the simple use case
description: Lean more on the journey simple use-case
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# About the simple use case{#concept_grh_vby_w2b}

## Purpose {#purpose}

Let's take the example of a hotel brand named Marlton. In their hotels, they have positioned beacon devices near all the strategic areas: lobby, floors, restaurant, gym, pool, etc.

In this use case, we will see how to send a personalized message in real-time to a person walking next to a beacon positioned near the spa.

We want to send a message only if the person is a woman. The message must be received within seconds.

![](../assets/journeyuc1_16.png)

## Pre-requisites {#prerequisites}

For our use case, we have designed one email transactional messaging template in Adobe Campaign Standard. We are using an event transactional messaging template. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is configured to send emails.

Events are sent from the customers' mobile phone when they are detected near a beacon. You need to design a mobile application to send events from the customer's mobile phone to the Mobile SDK.