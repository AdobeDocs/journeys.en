---
title: nowWithDelta
description: Learn about the function nowWithDelta
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# nowWithDelta {#nowWithDelta}

Returns the current datetime including an offset. If a time zone id is specified, the time zone offset will be applied. For more information on data types, refer to [](../expression/data-types.md).

## Category

Date

## Function syntax

`nowWithDelta(<parameters>)`

## Parameters

|Parameter|Description|
|--- |--- |
|delta|positive or negative integer value|
|date part|years, months, days, hours, minutes or seconds as a string|
|time zone id|string representation of the time zone value. For more, see [](../expression/data-types.md). Time zone id must be a string constant. It cannot be a field reference nor an expression.|

## Signatures and returned type

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returns a dateTime.

## Examples

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returns a dateTime exactly 2 hours ago.
