---
title: Get started
description: Discover the main steps to set up Journey Orchestration and build your first journey.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Get started{#concept_y4b_4qt_52b}

In [!DNL Journey Orchestration], there are two types of users, each of them performing specific tasks: the **technical user** and the **business user**. User access is managed via product profiles and rights. Refer to [](../about/access-management.md) to learn how to configure user access.

Here are the main steps to configure and use [!DNL Journey Orchestration]:

1. **Configure an event**

    You need to define the expected information and how to process it. This configuration is mandatory. This step is performed by a **technical user**.

    For more on this, refer to [](../event/about-events.md).

    ![](../assets/journey7.png)  

1. **Configure the data source**

    You need to define a connection to a system to retrieve additional information that will be used in your journeys, for example in your conditions. A built-in Adobe Experience Platform data source is also configured at provisioning time. This step is not required if you only leverage data from the events in your journey. This step is performed by a **technical user**. 

    For more on this, refer to [](../datasource/about-data-sources.md).
    
    ![](../assets/journey22.png)  

1. **Configure an action**

    If you're using a third-party system to send your messages, you need to configure its connection with [!DNL Journey Orchestration]. See [](../action/about-custom-action-configuration.md). 

    If you are using Adobe Campaign Standard to send messages, you need to configure the built-in action. See [](../action/working-with-adobe-campaign.md). 

    These steps are performed by a **technical user**. 

    ![](../assets/custom2.png)  

1. **Design your journey**

     Combine the different event, orchestration and action activities to build your multi-step cross-channel scenarios. This step is performed by a **business user**. 

     For more on this, see [](../building-journeys/journey.md).

     ![](../assets/journeyuc2_24.png)

1. **Test and publish the journey**

    You need to validate and activate the journey. This step is performed by a **business user**. 

    For more on this, see [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

    ![](../assets/journeyuc2_32bis.png)

1. **Monitor your journey**

    Use the dedicated reporting tools to measure your journey's effectiveness. This step is performed by a **business user**. 

    For more on this, see [](../reporting/about-journey-reports.md).

    ![](../assets/dynamic_report_journey_12.png)

