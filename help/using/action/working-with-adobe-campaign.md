---
product: adobe campaign
title: Working with Adobe Campaign
description: Learn about Adobe Campaign actions
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
---
# Working with Adobe Campaign {#using_adobe_campaign}

## Using Adobe Campaign Standard {#using_adobe_campaign_standard}

You can send emails, push notifications and SMS using the Adobe Campaign Standard's Transactional Messaging capabilities.

[!DNL Journey Orchestration] comes with an out-of-the-box action which allows the connection to Adobe Campaign Standard. 

The Campaign Standard transactional message and its associated event must be published in order to be used in Journey Orchestration. If the event is published but the message is not, it will not be visible in the Journey Orchestration interface. If the message is published but its associated event is not, it will be visible in the Journey Orchestration interface but it will not be usable.

>[!NOTE]
>
>A capping rule of 13 calls per second is automatically defined for Adobe Campaign Standard actions as soon as Adobe Campaign Standard integration is set up. This corresponds to the official scale of Adobe Campaign Standard Transactional Messaging.
>
>Read more about transactional messaging SLAs in [Adobe Campaign Standard Product Description](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Here are the steps to configure it:

1. From the **[!UICONTROL Actions]** list, click the built-in **[!UICONTROL AdobeCampaignStandard]** action. The action configuration pane opens on the right side of the screen.

    ![](../assets/actioncampaign.png)

1. Copy your Adobe Campaign Standard instance URL and paste it in the **[!UICONTROL URL]** field.

1. Click the **[!UICONTROL Test the instance URL]** to test the validity of the instance.

    >[!NOTE]
    >
    >This test verifies that:
    >
    >The host is ".campaign.adobe.com", ".campaign-sandbox.adobe.com", ".campaign-demo.adobe.com", ".ats.adobe.com" or ".adls.adobe.com".
    >
    >The URL starts with https,
    >
    >The ORG associated to this Adobe Campaign Standard's instance is the same as the Journey Orchestration's ORG.

When designing your journey, three actions will be available in the **[!UICONTROL Action]** category: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (see [Using Adobe Campaign actions](../building-journeys/using-adobe-campaign-actions.md)). **Reactions event** will also allow you to react on message clicks, opens, etc. (see [Reactions events](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

If you're using a third-party system to send messages, you need to add and configure a custom action. See [About custom action configuration](../action/about-custom-action-configuration.md).

## Using Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

This integration is available for Adobe Campaign Classic v7 starting 21.1 release, and Adobe Campaign v8. It allows you to send emails, push notifications and SMS using Adobe Campaign Transactional Messaging capabilities.

The connection between the Journey Orchestration and Campaign instances is setup by Adobe at provisioning time.

An end-to-end use case is presented in this [section](../usecase/campaign-v7-v8-use-case.md).

For each action configured, an action activity is available in the journey designer palette. Refer to this [section](../building-journeys/using-adobe-campaign-actions.md).

### Important notes

* There is no throttling of messages. We cap the number of messages that can be sent over to 50,000/hour based on our current Campaign SLA. For this reason, Journey orchestration should only be used in unitary use cases (individual events, not segments).

* You need to configure one action on the canvas per template you wish to use. You need to configure one action in Journey Orchestration for each template you wish to use from Adobe Campaign.

* We recommend that you use a dedicated Message Center instance that is hosted for this integration to avoid impacting any other Campaign operations that you may have going on. The marketing server can be hosted or on-premise. The build required is 21.1 Release Candidate or greater. 

* There is no validation that the payload or Campaign message is correct.

* You cannot use a Campaign action with a segment qualification event.

### Prerequisites

In Campaign, you need to create and publish a transactional message and its associated event. Refer to the [Adobe Campaign documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

You can build your JSON payload corresponding to each message following the pattern below. You will then paste this payload when configuring the action in Journey Orchestration (see below)

Here is an example:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **channel**: the channel defined for your Campaign transactional template
* **eventType**: the internal name of your Campaign event
* **ctx**: variable based on the personalization you have in your message. 

### Configuring the action

In Journey Orchestration, you need to configure one action per transactional message. Follow these steps:

1. Create a new action. Refer to this [section](../action/action.md).
1. Enter a name and description.
1. In the **Action type** field, select **Adobe Campaign Classic**.
1. Click in the **Payload** field and paste an example of the JSON payload corresponding to the Campaign message. Contact Adobe to get this payload.
1. Adjust the different fields to be static or variable depending on if you want to map them on the Journey canvas. Certain fields, such as channel parameters for email address and personalization fields (ctx), you likely want defined as variables for mapping in context of the journey.
1. Click **Save**.

![](../assets/accintegration1.png)


