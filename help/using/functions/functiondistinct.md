---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: Learn about the function distinct
feature: Journeys
role: Data Engineer
level: Experienced
---

# distinct {#distinct}

Returns the distinct values of the list without null values.

## Category

List

## Function syntax

`distinct(<parameter>)`

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

`distinct(<listInteger>)`

Returns a list of integers.

`distinct(<listDecimal>)`

Returns a list of decimals.

`distinct(<listString>)`

Returns a list of strings.

`distinct(<listDateTimeOnly>)`

Returns a list of datetimes without considering time zone.

`distinct(<listDateTime>)`

Returns a list of datetimes.

`distinct(<listBoolean>)`

Returns a list of booleans.

`distinct(<listDuration>)`

Returns a list of durations.

## Examples

`distinct([10,2,10,null])`

Returns `[10, 2]`.
