---
product: adobe campaign
title: toDateOnly
description: Learn about the function toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
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
# toDateOnly{#toDateOnly}

Converts an argument value into a date only value.

## Category

Conversion

## Function syntax

`toDateOnly(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date in ISO-8601 or "YYYY-MM-DD" format (XDM Date format) | string |
| date | date |

## Signatures and returned types

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Return a datetime without considering time zone.

## Examples

`toDateOnly("2016-08-18")`

returns a dateOnly object representing 2016-08-18.
