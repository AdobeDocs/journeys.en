---
product: adobe campaign
title: About actions
description: Learn how to configure an action
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
---
# About actions {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="About actions"
>abstract="This is where you define the connection to the system that will send messages. The actions defined here will then be available in the left palette of your journey, in the Action category. "

Actions are connections through which you deliver personalized, real-time experiences to customers such as push notifications, email, SMS, or any other means of digital engagement you use in your business.

Custom actions enable you to configure connection of a third-party system to send messages or API calls. An action can be configured with any service from any provider that can be called through a REST API with a JSON-formatted payload.

The actions are available in the left palette of your journey, in the **[!UICONTROL Action]** category. See [this page](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>The configuration of custom actions is always performed by a **technical user**.

In the list of **Actions**, you can press c to create a new journey, action, data source or event. For more information on shortcuts in [!DNL Journey Orchestration], see [this section](../about/user-interface.md#section_ksq_zr1_ffb).

To view the action list or configure a new action, click **[!UICONTROL Actions]** in the top menus. The list of actions is displayed. See [this page](../about/user-interface.md) for more information on the interface.

![](../assets/custom1.png)

If you have Adobe Campaign Standard, you need to configure the out-of-the box action to send emails, push notifications and SMS using the Adobe Campaign Standard's Transactional Messaging capabilities. Refer to [this page](../action/working-with-adobe-campaign.md).

If you have Adobe Campaign v7 or v8, an integration is available upon request. Refer to [this page](../action/acc-action.md).

If you're using a third-party system to send messages such as Epsilon, Facebook, Adobe.io, Firebase, etc, you need to add and configure a custom action. Refer to [this page](../action/about-custom-action-configuration.md).

