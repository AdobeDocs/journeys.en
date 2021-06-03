---
product: adobe campaign
title: sum
description: Learn about the function sum
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
---
# sum {#sum}

Returns the sum of the values of a set of expressions. Null values are ignored.

## Category

Aggregation

## Function syntax

`sum(<parameters>)`

## Parameters

* listInteger
* listDecimal
* duration
* integer
* decimal

## Signatures and returned types

`sum(<listDecimal>)`

Returns a decimal.

`sum(<listInteger>)`

Returns an integer.

`sum(<integer>,<integer>)`

Returns an integer.

`sum(<decimal>,<decimal>)`

Returns a decimal.

## Examples

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Returns 21.

`sum([10.5,null,8.1])`

Returns 18.6.
