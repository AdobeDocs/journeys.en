---
product: adobe campaign
solution: Journey Orchestration
title: Using Adobe Campaign v7/v8 actions
description: Learn about Adobe Campaign v7/v8 actions
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
---
# Using Adobe Campaign v7/v8 {#using_campaign_classic} 

An integration is available if you have Adobe Campaign v7 or v8. It will allow you to send emails, push notifications and SMS using Adobe Campaign Transactional Messaging capabilities.

The connection between the Journey Orchestration and Campaign instances is setup by Adobe at provisioning time. Contact Adobe.

For this to work, you need to configure a dedicated action. Refer to this [section](../action/acc-action.md).

An end-to-end use case is presented in this [section](../usecase/campaign-classic-use-case.md).

1. Design your journey, starting with an event. See this [section](../building-journeys/journey.md).
1. In the **Action** section of the palette, select a Campaign action and add it to your journey.
1. In the **Action parameters**, all the fields expected in the message payload are displayed. You need to map each of these fields with the field you want to use, either from the event or from the data source. This is similar to custom actions. Refer to this [section](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
