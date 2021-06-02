---
product: adobe campaign
title: Working with Adobe Campaign
description: Learn about Adobe Campaign actions
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
---
# Working with Adobe Campaign {#using_adobe_campaign_standard}

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
