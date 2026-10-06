---
product: adobe campaign
title: inNextDays
description: Learn about the function inNextDays
feature: Journeys
role: Developer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
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
# inNextDays {#inNextDays}

Returns true if a given date or dateTime is between now and now + delta days.

## Category

Date

## Function syntax

`inNextDays(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextDays(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returns true.
