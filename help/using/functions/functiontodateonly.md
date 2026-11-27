---
product: adobe campaign
title: toDateOnly
description: Learn about the function toDateOnly
badge: label="Legacy" type="Informative"
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
