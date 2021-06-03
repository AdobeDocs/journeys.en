---
product: adobe campaign
title: inLastDays
description: Learn about the function inLastDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
---
# inLastDays {#inLastDays}

Returns true if a given date or dateTime is between now and now - delta days.

## Category

Date

## Function syntax

`inLastDays(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastDays(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Returns true.
