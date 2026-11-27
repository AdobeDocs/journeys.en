---
product: adobe campaign
title: inNextMonths
description: Learn about the function inNextMonths
badge: label="Legacy" type="Informative"
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Returns true.
