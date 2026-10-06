---
product: adobe campaign
title: inLastHours
description: Learn about the function inLastHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
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
# inLastHours {#inLastHours}

Returns true if the given date time is between now and now - delta hours. 

## Category

Date

## Function syntax

`inLastHours(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastHours(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Returns true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Returns true.
