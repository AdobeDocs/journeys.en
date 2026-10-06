---
product: adobe campaign
title: inNextHours
description: Learn about the function inNextHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
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
# inNextHours {#inNextHours}

Returns true if a given date or dateTime is between now and now + delta hours.

## Category

Date

## Function syntax

`inNextHours(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextHours(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returns true.
