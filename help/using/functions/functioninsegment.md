---
product: adobe campaign
title: inSegment
description: Learn about the function inSegment
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# inSegment {#inSegment}

Checks if an individual belongs to a given segment.

>[!NOTE]
>
>You can retrieve up to 100 segments.

The segment name must be a string constant. It cannot be a field reference nor an expression.

Segments are defined in the [Adobe Experience Platform](https://platform.adobe.com/segment/overview). The expression editor provides an autocompleted list of segments.

Segments can have three statuses:

* existing: entity continues to be in the segment.
* realized: entity is entering the segment.
* exited: entity is exiting the segment.

Only the individuals with the **Realized** and **Existing** segment participation statuses will be considered as members of the segment. For more on how to evaluate a segment, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results). 

`IF inSegment('segmentName') == true` means that you have a segmentMembership with the entered/existing status.

`ELSE inSegment('segmentName') == false` means that you have a segmentMembership of the exited status.

## Category

Adobe Experience Platform

## Function syntax

`inSegment(<parameter>)`

## Parameters

|Parameter|Description|Type|
|--- |--- |--- |
|Segment|The segment name |`<string>`|

## Signature and returned type

`inSegment(<string>)`

Returns a boolean.

## Example

`inSegment("men over 50")`

Explanation:

The function will return **[!UICONTROL true]** if the individual within the journey instance is part of the Adobe Experience Platform segment named “men over 50”, **[!UICONTROL false]** otherwise.
