---
product: adobe campaign
title: inLastHours
description: Learn about the function inLastHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
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
