---
product: adobe campaign
title: inNextDays
description: Learn about the function inNextDays
feature: Journeys
role: Developer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
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
