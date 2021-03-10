---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: Learn about the function inNextMonths
feature: Journeys
role: Data Engineer
level: Experienced
---

# inNextMonths {#inNextMonths}

Returns true if a given date or dateTime is between now and now + delta months.

## Category

Date

## Function syntax

`inNextMonths(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextMonths(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Returns true.
