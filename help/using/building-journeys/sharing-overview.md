---
product: adobe campaign
title: Journey step sharing overview
description: Journey step sharing overview
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
---
# Journey step sharing overview{#sharing-overview}

[!DNL Journey Orchestration] automatically sends journey performance data to the Adobe Experience Platform so it can be combined with other data for analysis purposes. 

>[!NOTE]
>
>This feature is activated by default on all instances for journey steps events. For journey profile step events, the activation is upon request. You cannot modify or update the schemas and datasets that have been created during provisioning for step events. By default, these schemas and datasets are in read-only mode.

For example, you have set up a journey that sends multiple emails. This capability allows you to combine [!DNL Journey Orchestration] data with downstream event data like how many conversions occurred, how much engagement happened on the website, or how many transactions happened in the store. The journey information can be combined with data on the Adobe Experience Platform, either from other digital properties or from offline properties to give a more comprehensive view of performance.

[!DNL Journey Orchestration] automatically creates the necessary schemas and streams into datasets to the Adobe Experience Platform for each step an individual takes in a journey. A step event corresponds to an individual moving from one node to another in a journey. For example, in a journey that has an event, a condition and an action, three step events are sent to the Adobe Experience Platform. 

The list of XDM fields that are passed is comprehensive. Some contain system generated codes and others have human readable friendly names. Examples include the label of the journey activity or the step status: how many times an action timed out or ended in error.

>[!CAUTION]
>
>Datasets cannot not be turned on for real time profile service. Please make sure that the **[!UICONTROL Profile]** toggle is turned off.

Journeys sends data as it occurs, in a streaming way. You can query this data using the Query Service. You can connect to Customer Journey Analytics or other BI tools to view data related to these steps.

The following schemas are created:

* Journey Step Profile Event schema for [!DNL Journey Orchestration] – Experience Events for steps taken in a Journey along with an Identity Map to be used for mapping to an individual Journey Participant.
* Journey Step Event schema for [!DNL Journey Orchestration] – Journey step event that is tied to a Journey Metadata.
* Journey schema with Journey Fields for [!DNL Journey Orchestration] – Journey Metadata to describe Journeys.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

The following datasets are passed:

* Journey Step Profile Event schema for [!DNL Journey Orchestration]
* Journey Step Events
* Journeys

![](../assets/sharing3.png)

The lists of XDM fields passed to the Adobe Experience Platform are detailed here:

* [Step event field list](../building-journeys/sharing-field-list.md)
* [Legacy step event fields](../building-journeys/sharing-legacy-fields.md)

For more information on step events reporting to Adobe Experience Platform, watch this [tutorial video](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
