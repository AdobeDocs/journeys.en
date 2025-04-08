---
product: adobe campaign
title: About Adobe Experience Platform segments
description: Learn how to configure an Adobe Experience Platform segment
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
---
# About Adobe Experience Platform segments {#about-segments}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


If you're using the [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) to create your segments, you can leverage them in [!DNL Journey Orchestration]. Thanks to a dedicated event activity, you can make individuals enter or move forward in a journey based on Adobe Experience Platform segment entrances and exits. This also allows you to build complex conditions in your journeys using the simple or advanced expression editor.

Let's say you have a "silver customer" segment. With this activity, you can make all new silver customers enter a journey and send them a series of personalized messages. You can also easily build conditions based on this segment.

Here are the possibilities [!DNL Journey Orchestration] offer you with segments:

* Access the list of Adobe Experience Platform segments. See [Creating a segment](../segment/creating-a-segment.md).
* Create segments directly in [!DNL Journey Orchestration] the same way you create them using the Segmentation Service. See [Creating a segment](../segment/creating-a-segment.md).
* Leverage segments in your journey's conditions using the simple or advanced expression editor. See [Using segments in conditions](../segment/using-a-segment.md).
* Add a **[!UICONTROL Segment qualification]** event to your journey in order to listen to the entrances and exits of profiles in Adobe Experience Platform segments. See [Events activities](../building-journeys/segment-qualification-events.md).

## Evaluation method in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration, audiences are generated from segment definitions using one of these evaluation methods:

* Streaming segmentation – the audience list for the segment is kept up-to-date in real time while new data flows into the system.
* Batch segmentation – the audience list for the segment is updated on an hourly basis, based on data that has arrived in the past hour.

The determination between batch segmentation and streaming segmentation is made by the system for each segment definition, based on the complexity and the cost of evaluating the segment rule.

You can view the evaluation method for each segment in the **[!UICONTROL Evaluation method]** column of the segment list.

After you have first defined a segment, profiles are added to the audience when they qualify.

Backfilling the audience from prior data can take up to 24&nbsp;hours. After the audience has been backfilled, the audience is continuously kept up-to-date and is always ready for targeting.