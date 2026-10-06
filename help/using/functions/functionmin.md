---
product: adobe campaign
title: min
description: Learn about the function min
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
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
* listDateOnly
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

`min(<listDateOnly>)`

Returns a date.

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
