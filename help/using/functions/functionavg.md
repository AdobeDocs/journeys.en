---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: Learn about the function avg
---

# avg {#avg}

Returns the average value among a set of expressions, given either as a list or two expressions. Null values are ignored.


## Category

Aggregation

## Function syntax

`avg(<parameter>)`

## Parameters

Supported types:

* listInteger
* listDecimal
* decimal
* integer

## Signatures and returned type

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Returns a decimal.

## Examples

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Returns 7.0.

`avg(10.2, 3)`

Returns 6.6.
