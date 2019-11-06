---
title: sort
description: Learn about the function sort
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
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

## Signature and return type

`sort(<listInteger>,<boolean>)`

Returns a list of integers.

`sort(<listDecimal>,<boolean>)`

Returns a list of decimals.

`sort(<listString>,<boolean>)`

Returns a list of strings.

`sort(<listDateTimeOnly>,<boolean>)`

Returns a list of datetimes without considering timezone.

`sort(<listDateTime>,<boolean>)`

Returns a list of datetimes.

`sort(<listBoolean>,<boolean>)`

Returns a list of booleans.

## Example

`sort(["A", "C", "B"], true)`

Returns ["A","B","C"]

`sort([1, 3, 2], false)`

Returns [3, 2, 1]
