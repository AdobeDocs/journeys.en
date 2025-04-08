---
product: adobe campaign
title: About custom action configuration
description: Learn how to configure a custom action
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
---
# About custom action configuration {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


If you're using a third-party system to send messages or if you want [!DNL Journey Orchestration] to send API calls to a third-party system, this is where you configure its connection to [!DNL Journey Orchestration]. The custom action defined by technical users will then be available in the left palette of your journey, in the **[!UICONTROL Action]** category (see [this page](../building-journeys/about-action-activities.md). Here are a few examples of systems that you can connect to with custom actions: Epsilon, Facebook, Adobe.io, Firebase, etc.

Limitations are listed in [this page](../about/limitations.md).

In custom action parameters, you can pass a simple collection, as well as a collection of objects. Regarding the limitations, please refer to [this page](../usecase/collections.md#limitations). Also note that the parameters have an expected format (example: string, decimal, etc.). You must be careful to respect these expected formats. Refer to this [use case](../usecase/collections.md).

Here are the main steps required to configure a custom action:

1. From the **[!UICONTROL Actions]** list, click **[!UICONTROL Add]** to create a new action. The action configuration pane opens on the right side of the screen.

    ![](../assets/custom2.png)

1. Enter a name for your action.

    >[!NOTE]
    >
    >Do not use spaces or special characters. Do not use more than 30 characters.

1. Add a description to your action. This step is optional.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. See [this page](../action/url-configuration.md).
1. Configure the **[!UICONTROL Authentication]** section. This configuration is the same as for data sources.  See [this section](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Define the **[!UICONTROL Action parameters]**. See [this page](../action/defining-the-message-parameters.md).
1. Click **[!UICONTROL Save]**.

    The custom action is now configured and ready to be used in your journeys. See [this page](../building-journeys/about-action-activities.md).

    >[!NOTE]
    >
    >When a custom action is used in a journey, most parameters are read-only. You can only modify the **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** fields and the **[!UICONTROL Authentication]** section.
