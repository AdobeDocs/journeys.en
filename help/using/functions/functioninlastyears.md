---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: Learn about the function inLastYears
---

# inLastYears {#inLastYears}

Returns true if a given date or dateTime is between now and now - delta years.

## Category

Date

## Function syntax

`inLastYears(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastYears(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns true.
