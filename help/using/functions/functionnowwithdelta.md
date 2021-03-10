---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Learn about the function nowWithDelta
feature: Journeys
role: Data Engineer
level: Experienced
---

# nowWithDelta {#nowWithDelta}

Returns the current datetime including an offset. If a time zone id is specified, the time zone offset will be applied. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Date

## Function syntax

`nowWithDelta(<parameters>)`

## Parameters

|Parameter|Description|
|--- |--- |
|delta|positive or negative integer value|
|date part|years, months, days, hours, minutes or seconds as a string|
|time zone id|string representation of the time zone value. For more, see [Data types](../expression/data-types.md). Time zone id must be a string constant. It cannot be a field reference nor an expression.|

## Signatures and returned type

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returns a dateTime.

## Examples

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returns a dateTime exactly 2 hours ago.
