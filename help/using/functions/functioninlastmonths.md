---
product: adobe campaign
title: inLastMonths
description: Learn about the function inLastMonths
badge: label="Legacy" type="Informative"
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returns true.
