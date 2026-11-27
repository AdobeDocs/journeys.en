---
product: adobe campaign
title: avg
description: Learn about the function avg
badge: label="Legacy" type="Informative"
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
