---
product: adobe campaign
title: About data sources
description: Learn how to configure a data source 
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
---
# About data sources {#concept_s1s_dqt_52b}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._



>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="About data sources"
>abstract="The data source configuration allows you to define a connection to a system to retrieve additional information that will be used in your journeys."

The data source configuration allows you to define a connection to a system to retrieve additional information that will be used in your journeys, for:

* [condition definition](../building-journeys/condition-activity.md)
* parameter and personalization data in [actions](../action/action.md)
* [custom wait definition](../building-journeys/wait-activity.md#custom)
* [time zone definition](../building-journeys/timezone-management.md)

This configuration is not required if your journeys only leverage local data coming from an event payload. For example, if your journey is composed of an event followed by an email activity that only uses data from the event, there is no need to configure a data source.

There are two types of data sources:

* The pre-configured Adobe Experience Platform data source that defines the connection to the Real-time Customer Profile Service. This is a built-in data source. See [this page](../datasource/adobe-experience-platform-data-source.md).
* The external data sources that allow you to define a connection to external systems. These are the ones you can create. See [this page](../datasource/external-data-sources.md).

For each data source, you define the information to retrieve using field groups. Field groups are sets of fields that can be retrieved from a data source. See [this page](../datasource/field-groups.md).

Here are the main data source configuration steps:

>[!NOTE]
>
>The data source configuration is always performed by a **technical user**.

1. In the menu pane, select **[!UICONTROL Admin]**. In the **[!UICONTROL Data sources]** section, click **[!UICONTROL Manage]**.

    The list of data sources is displayed. See [this page](../about/user-interface.md) for more information on the interface.

    ![](../assets/journey18.png)

1. Then you can either add field groups to the built-in data source (see [this page](../datasource/adobe-experience-platform-data-source.md)) or create a new external data source (see [this page](../datasource/external-data-sources.md)) and associated field groups (see [this page](../datasource/field-groups.md)).

    ![](../assets/journey23.png)

1. Click **[!UICONTROL Save]**.

    The data source is now configured and ready to be used in your journeys.
