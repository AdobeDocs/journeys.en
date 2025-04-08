---
product: adobe campaign
title: Segment qualification events
description: Learn about segment qualification events
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
---
# Segment qualification events {#segment-qualification}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._



## About segment qualification events{#about-segment-qualification}

This activity allows your journey to listen to the entrances and exits of profiles in Adobe Experience Platform segments in order to make individuals enter or move forward in a journey. For more information on segment creation, refer to this [section](../segment/about-segments.md).

Let's say you have a "silver customer" segment. With this activity, you can make all new silver customers enter a journey and send them a series of personalized messages.

This type of event can be positioned as the first step or later in the journey.

>[!IMPORTANT]
>
>Keep in mind that Adobe Experience Platform segments are calculated either once a day (**batch** segments) or in real-time (**streamed** segments, using the High Frequency Audiences option of Adobe Experience Platform).
>
>If the selected segment is streamed, the individuals belonging to this segment will potentially enter the journey in real-time. If the segment is batch, people newly qualified for this segment will potentially enter the journey when the segment calculation is executed on the Adobe Experience Platform.


1. Unfold the **[!UICONTROL Events]** category and drop a **[!UICONTROL Segment qualification]** activity into your canvas.

   ![](../assets/segment5.png)

1. Add a **[!UICONTROL Label]** to the activity. This step is optional.

1. Click in the **[!UICONTROL Segment]** field and select the segments you want to leverage.

   >[!NOTE]
   >
   >Note that you can customize the columns displayed in the list and sort them.

   ![](../assets/segment6.png)

   Once the segment is added, the **[!UICONTROL Copy]** button allows you to copy its name and ID:

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. In the **[!UICONTROL Behaviour]** field, choose whether you want to listen to segment entrances, exits or both.

   >[!NOTE]
   >
   >Note that **[!UICONTROL Enter]** and **[!UICONTROL Exit]** correspond to the **Realized** and **Exited** segment participation statuses from Adobe Experience Platform. For more on how to evaluate a segment, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results). 

1. Select a namespace. This is only needed if the event is positioned as the first step of the journey.

   ![](../assets/segment7.png)

The payload contains the following context information, which you can use in conditions and actions:

* the behavior (entrance, exit)
* the timestamp of qualification
* the segment id

When using the expression editor in a condition or action that follows a **[!UICONTROL Segment qualification]** activity, you have access to the **[!UICONTROL SegmentQualification]** node. You can choose between the **[!UICONTROL Last qualification time]** and the **[!UICONTROL status]** (enter or exit).

See [Condition activity](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

A new journey that includes a segment qualification event is operational ten minutes after you have published it. This time interval corresponds to the cache refresh interval of the dedicated service. Therefore, you must wait ten minutes before using this journey.

## Best practices {#best-practices-segments}

The **[!UICONTROL Segment Qualification]** activity enables the immediate entrance in journeys of individuals getting qualified or disqualified from an Adobe Experience Platform segment.

The reception speed of this information is high. Measurements made show a speed of 10 000 events received per seconds. As a result, you should make sure you understand how peaks of entrance might happen, how to avoid them and how to make your journey ready for them.

### Batch segments{#batch-speed-segment-qualification}

When using segment qualification for a batch segment, note that a peak of entrance will happen at the time of the daily calculation. The size of the peak will depend on the number of individuals entering (or exiting) the segment daily.

Moreover, if the batch segment is newly created and immediately used in a journey, the first batch of calculation might make a very large number of individuals enter the journey.

### Streamed segments{#streamed-speed-segment-qualification}

When using segment qualification for streamed segments, there is less risk of getting large peaks of entrances/exits due to the continuous evaluation of the segment. Still, if the segment definition leads to making a large volume of customers qualify at the same time, there might be a peak too. 

For more information on streaming segmentation, refer to this [page](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### How to avoid overloads{#overloads-speed-segment-qualification}

Here are a few best practices that will help to avoid overloading systems leveraged in journeys (data sources, custom actions, Adobe Campaign Standard actions).

Do not use, in a **[!UICONTROL Segment Qualification]** activity, a batch segment immediately after its creation. It will avoid the first calculation peak. Note that there will be a yellow warning in the journey canvas if you're about to use a segment that has never been calculated.

![](../assets/segment-error.png)

Put in place a capping rule for data sources and actions used in journeys to avoid overloading them (refer to this [section](../api/capping.md)). Note that the capping rule has no retry. If you need to retry, you must use an alternative path in the journey by checking the box **[!UICONTROL Add an alternative path in case of a timeout or an error]** in conditions or actions.

Before using the segment in a production journey, always evaluate first the volume of individuals qualifying for this segment every day. To do so, you can check the **[!UICONTROL Segments]** section in the Adobe Experience Platform and look at the graph on the right side.

![](../assets/segment-overload.png)
