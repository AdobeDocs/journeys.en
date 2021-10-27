---
product: adobe campaign
title: distinctCount
description: Learn about the function distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
---
# distinctCount{#distinctCount}

Counts the number of different values ignoring the null values.

## Category

Aggregation

## Function syntax

`distinctCount(<listAny>)`

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
| List      | listDateOnly     |

## Signature and returned type

`distinctCount(<listAny>)`

Returns an integer.

## Example

`distinctCount([10,2,10,null])`

Returns 2.
