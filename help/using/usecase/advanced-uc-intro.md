---
title: About the advanced use case
description: Lean more on the journey advanced use-case
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# About the advanced use case {#concept_vzy_ncy_w2b}

## Purpose {#purpose}

Let's take the example of a hotel brand named Marlton. In their hotels, they have positioned beacon devices near all the strategic areas: lobby, floors, restaurant, gym, pool, etc.

>[!NOTE]
>
>In this use case, we use Adobe Campaign Standard to send messages.

In this use case, we will see how to send personalized messages in real-time to customers when they walk near a specific beacon.

First of all, we want to send a message as soon as a person enters a Marlton hotel. We want to send a message only if the person has not received any communication from us within the last 24 hours.

We then check two conditions:

* If this person is not a loyalty member, we send him an email to join the loyalty membership offer.
* If this person is already a loyalty member, we check if he has a room reservation:
    * If he doesn't, we send him a push notification with room rates.
    * If he does, we send him a welcome push notification. And if he enters the restaurant within the next 6 hours, we send him a push notification with a discount on a meal.

![](../assets/journeyuc2_29.png)

For this use case, we will need to create two events (see [](../usecase/uc2event.md)):

* The lobby beacon event that will be pushed to the system when a customer enters the hotel.
* The restaurant beacon event that will be pushed when a customer enters the restaurant.

We will need to configure a connection to two data sources (see [](../usecase/advanced-uc-data-source.md)):

* The build-in Experience Platform data source, to retrieve the information for our two conditions (loyalty membership and last contact date) as well as the message personalization information.
* The hotel reservation system, to retrieve the reservation status information.

## Pre-requisites {#prerequisites}

For our use case, we have designed three Adobe Campaign Standard transactional messaging templates. We are using event transactional messaging templates. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is configured to send emails and push notifications.

The Experience Cloud ID is used as the key to identify the customer in the hotel reservation system.

Events are sent from the customers' mobile phone when they detected near a beacon. You need to design a mobile application to send events from the customer's mobile phone to the Mobile SDK.

The Loyalty member field is a custom field and was added in XDM for our specific organization ID.
