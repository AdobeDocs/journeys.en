---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: Learn about the function inNextHours
---

# inNextHours {#inNextHours}

Returns true if a given date or dateTime is between now and now + delta hours.

## Category

Date

## Function syntax

`inNextHours(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextHours(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returns true.
