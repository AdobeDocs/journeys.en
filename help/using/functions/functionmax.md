---
title: max
description: Learn about the function max
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---
# max{#max}

Returns the maximum value among a set of expressions, given either as a list or two expressions. Null values are ignored.

## Category

Aggregation

## Function syntax

`max(<parameter>)`

## Parameters

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duration
* integer
* decimal
* dateTime
* dateTimeOnly

## Signatures and returned types

`max(<listDuration>)`

Returns a duration.

`max(<listInteger>)`

Returns a duration.

`max(<listDateTimeOnly>)`

Returns a datetime without considering time zone.

`max(<listDateTime>)`

Returns a datetime.

`max(<listDecimal>)`

Returns a decimal.

`max(<decimal>,<decimal>)`

Returns a decimal.

`max(<duration>,<duration>)`

Returns a duration.

`max(<dateTime>,<dateTime>)`

Returns a datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Returns a datetime without considering time zone.

`max(<integer>,<integer>)`

Returns an integer.

## Examples

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Returns 10.

`max([10,null,8])`

Returns 10.
