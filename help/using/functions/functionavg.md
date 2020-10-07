---
title: avg
description: Learn about the function avg
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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
