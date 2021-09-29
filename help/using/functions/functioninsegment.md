---
product: adobe campaign
title: inSegment
description: Learn about the function inSegment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
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
