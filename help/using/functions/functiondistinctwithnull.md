---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: Learn about the function distinctWithNull
---

# distinctWithNull {#distinctWithNull}

Returns the distinct values of the list. If the list has at least one null value, a null value will be in the returned list.

## Category

List

## Function syntax

`distinctWithNull(<parameter>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| List      | listString       |
| List      | listBoolean      |
| List      | listInteger      |
| List      | listDecimal      |
| List      | listDuration     |
| List      | listDateTime     |
| List      | listDateTimeOnly |

## Signatures and returned types

`distinctWithNull(<listInteger>)`

Returns a list of integers.

`distinctWithNull(<listDecimal>)`

Returns a list of decimals.

`distinctWithNull(<listString>)`

Returns a list of strings.

`distinctWithNull(<listDateTimeOnly>)`

Returns a list of datetimes without considering time zone.

`distinctWithNull(<listDateTime>)`

Returns a list of datetimes.

`distinctWithNull(<listBoolean>)`

Returns a list of booleans.

`distinctWithNull(<listDuration>)`

Returns a list of durations.

## Examples

`distinctWithNull([10,2,10,null])`

Returns [10, 2, null]
