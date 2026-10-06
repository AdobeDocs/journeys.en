---
product: adobe campaign
title: nowWithDelta
description: Learn about the function nowWithDelta
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
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
