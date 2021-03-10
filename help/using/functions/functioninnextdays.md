---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: Learn about the function inNextDays
feature: Journeys
role: Data Engineer
level: Experienced
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
