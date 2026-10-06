---
product: adobe campaign
title: now
description: Learn about the function now
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
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
# now {#now}

Returns the current date in date time format. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Date

## Function syntax

`now(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string||

## Signatures and returned type

`now()`

`now("<timeZone id>")`

Returns a dateTime.

## Examples

`now()`

 Returns 2019-06-03T06:30Z.

`toString(now())`

Returns "2019-06-03T06:30Z"

`now("Europe/Paris")`

Returns 2019-06-03T08:30+02:00.
