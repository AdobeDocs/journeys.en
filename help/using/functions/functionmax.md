---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Learn about the function max
feature: Journeys
role: Data Engineer
level: Experienced
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
