---
product: adobe campaign
title: About the simple use case
description: Lean more on the journey simple use-case
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
---
# About the simple use case{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


## Purpose {#purpose}

Let's take the example of a hotel brand named Marlton. In their hotels, they have positioned beacon devices near all the strategic areas: lobby, floors, restaurant, gym, pool, etc.

In this use case, we will see how to send a personalized message in real-time to a person walking next to a beacon positioned near the spa.

We want to send a message only if the person is a woman. The message must be received within seconds.

![](../assets/journeyuc1_16.png)

## Pre-requisites {#prerequisites}

For our use case, we have designed one email transactional messaging template in Adobe Campaign Standard. We are using an event transactional messaging template. Refer to this [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html).

Adobe Campaign Standard is configured to send emails.

Events are sent from the customers' mobile phone when they are detected near a beacon. You need to design a mobile application to send events from the customer's mobile phone to the Mobile SDK.
