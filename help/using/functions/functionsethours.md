---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Learn about the function setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
---
# setHours {#setHours}

Sets the hours of a date time or date time only. For example, if you want to wait until a certain hour tomorrow, you can force the hour.

## Category

Date

## Function syntax

`setHours(<parameter>)`

## Parameters

|Parameter|Type|
|--- |--- |
|date time|dateTime|
|date time without considering time zone|dateTimeOnly|
|hours|integer|

## Signatures and returned type

`setHours(<dateTime>,<hours>)`

Returns a datetime.

`setHours(<dateTimeOnly>,<hours>)`

Returns a datetime without considering time zone.

## Examples

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returns tomorrow at 8 PM.
