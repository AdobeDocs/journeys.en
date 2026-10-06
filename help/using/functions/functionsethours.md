---
product: adobe campaign
title: setHours
description: Learn about the function setHours
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
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

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returns 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returns tomorrow at 8:XY PM, XY being the minutes at the moment of the current time evaluation. If the evaluation happens at 2:45 AM, the returned time will be 8:45 PM.
