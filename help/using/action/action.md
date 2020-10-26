---
title: About actions
description: Learn how to configure an action
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# About actions {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="About actions"
>abstract="This is where you define the connection to the system that will send messages. The actions defined here will then be available in the left palette of your journey, in the Action category. "

Actions are connections through which you deliver personalized, real-time experiences to customers such as push notifications, email, SMS, or any other means of digital engagement you use in your business.

Custom actions enable you to configure connection of a third-party system to send messages or API calls. An action can be configured with any service from any provider that can be called through a REST API with a JSON-formatted payload.

The actions are available in the left palette of your journey, in the **[!UICONTROL Action]** category (see [](../building-journeys/about-action-activities.md) ).

>[!NOTE]
>
>The configuration of custom actions is always performed by a **technical user**.

In the list of **Actions**, you can press c to create a new journey, action, data source or event. For more information on shortcuts in [!DNL Journey Orchestration], see [](../about/user-interface.md#section_ksq_zr1_ffb).

To view the action list or configure a new action, click **[!UICONTROL Actions]** in the top menus. The list of actions is displayed. See [](../about/user-interface.md) for more information on the interface.

![](../assets/custom1.png)

If you have Adobe Campaign Standard, you need to configure the out-of-the box action to send emails, push notifications and SMS using the Adobe Campaign Standard's Transactional Messaging capabilities. Refer to [](../action/working-with-adobe-campaign.md).

If you're using a third-party system to send messages such as Epsilon, Facebook, Adobe.io, Firebase, etc, you need to add and configure a custom action. Refer to [](../action/about-custom-action-configuration.md).

For more information on how to configure an Action for [!DNL Journey Orchestration] and how to use it in a journey, watch this [video tutorial](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html).
