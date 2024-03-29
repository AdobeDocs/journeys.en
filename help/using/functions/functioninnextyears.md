---
product: adobe campaign
title: inNextYears
description: Learn about the function inNextYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
---
# inNextYears {#inNextYears}

Returns true if a given date or dateTime is between now and now + delta years.

## Category

Date

## Function syntax

`inNextYears(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextYears(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Returns true.
