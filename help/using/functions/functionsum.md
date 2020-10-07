---
title: sum
description: Learn about the function sum
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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
