---
product: adobe campaign
title: toDateOnly
description: Learn about the function toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
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

`toDateTimeOnly ("2016-08-18")`

returns a dateTime representing 2016-08-18T00:00:00.000

`toDateOnly("2016-08-18")`

returns a dateOnly object