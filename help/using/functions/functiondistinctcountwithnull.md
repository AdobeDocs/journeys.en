---
product: adobe campaign
title: distinctCountWithNull
description: Learn about the function distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
---
# distinctCountWithNull {#distinctCountWithNull}

Counts the number of different values including the null values.

## Category

Aggregation

## Function syntax

`distinctCountWithNull(<listAny>)`

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

## Signature and returned type

`distinctCountWithNull(<listAny>)`

Returns an integer.

## Example

`distinctCountWithNull([10,2,10,null])`

Returns 3.
