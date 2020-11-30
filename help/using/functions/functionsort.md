---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: Learn about the function sort
---

# sort {#sort}

Sorts a list of values in the natural order. The first argument is the list of values, the second is a boolean value indicating if the sort is ascending (true) or descending (false).

## Category

List

## Function syntax

`sort(<parameters>)`

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
| Boolean   | Boolean |

## Signature and returned type

`sort(<listInteger>,<boolean>)`

Returns a list of integers.

`sort(<listDecimal>,<boolean>)`

Returns a list of decimals.

`sort(<listString>,<boolean>)`

Returns a list of strings.

`sort(<listDateTimeOnly>,<boolean>)`

Returns a list of datetimes without considering time zone.

`sort(<listDateTime>,<boolean>)`

Returns a list of datetimes.

`sort(<listBoolean>,<boolean>)`

Returns a list of booleans.

## Example

`sort(["A", "C", "B"], true)`

Returns `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returns `[3, 2, 1]`.
