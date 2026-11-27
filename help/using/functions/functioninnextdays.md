---
product: adobe campaign
title: inNextDays
description: Learn about the function inNextDays
badge: label="Legacy" type="Informative"
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
