---
product: adobe campaign
title: Using segments in conditions
description: Learn how to use a segment
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Using segments in conditions {#using-a-segment}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


This section explains how to use a segment in a journey condition. To learn how to use a **[!UICONTROL Segment qualification]** event in your journey, refer to this [section](../building-journeys/segment-qualification-events.md).

To use a segment in a journey condition, follow these steps:

1. Open a journey, drop a **[!UICONTROL Condition]** activity and choose the **Data Source Condition**.
   ![](../assets/journey47.png)

1. Click **[!UICONTROL Add a path]** for each extra path needed. For each path, click the **[!UICONTROL Expression]** field.

   ![](../assets/segment3.png)

1. On the left side, unfold **[!UICONTROL Segments]** node. Drag and drop the segment you want to use for your condition. By default, the condition on the segment is true.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Only the individuals with the **Realized** and **Existing** segment participation statuses will be considered as members of the segment. For more on how to evaluate a segment, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results). 

For more information on journey conditions and how to use the simple expression editor, refer to [Condition activity](../building-journeys/condition-activity.md#about_condition).
