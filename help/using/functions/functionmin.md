---
product: adobe campaign
title: min
description: Learn about the function min
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
---
# min {#min}

Returns the minimum value among a set of expressions, given either as a list or two expressions. Null values are ignored.

## Category

Aggregation

## Function syntax

`min(<parameters>)`

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

`min(<listDuration>)`

Returns a duration.

`min(<listInteger>)`

Returns a duration.

`min(<listDateTimeOnly>)`

Returns a datetime without considering time zone.

`min(<listDateTime>)`

Returns a datetime.

`min(<listDecimal>)`

Returns a decimal.

`min(<decimal>,<decimal>)`

Returns a decimal.

`min(<duration>,<duration>)`

Returns a duration.

`min(<dateTime>,<dateTime>)`

Returns a datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Returns a datetime without considering time zone.

`min(<integer>,<integer>)`

Returns an integer.

## Examples

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Returns 3.

`min([10,null,8])`

Returns 8.
