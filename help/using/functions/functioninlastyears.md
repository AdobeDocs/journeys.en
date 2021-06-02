---
product: adobe campaign
title: inLastYears
description: Learn about the function inLastYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
---
# inLastYears {#inLastYears}

Returns true if a given date or dateTime is between now and now - delta years.

## Category

Date

## Function syntax

`inLastYears(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastYears(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns true.
