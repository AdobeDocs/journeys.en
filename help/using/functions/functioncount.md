---
product: adobe campaign
title: count
description: Learn about the function count
feature: Journeys
role: Developer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
---
# count {#count}

Counts the elements of the list not taking into account the null values.

## Category

Aggregation

## Function syntax

`count(<listAny>)`

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

## Signatures and returned type

`count(<listAny>)`

Returns an integer.

## Example

`count([10,2,10,null])`

Returns 3.
