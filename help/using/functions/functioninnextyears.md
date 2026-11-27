---
product: adobe campaign
title: inNextYears
description: Learn about the function inNextYears
badge: label="Legacy" type="Informative"
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
