---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: Learn about the function inLastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
---
# inLastMonths {#inLastMonths}

Returns true if a given date or dateTime is between now and now - delta months.

## Category

Date

## Function syntax

`inLastMonths(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastMonths(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns true.
