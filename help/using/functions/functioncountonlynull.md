---
product: adobe campaign
title: countOnlyNull
description: Learn about the function countOnlyNull
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
---
# countOnlyNull {#countOnlyNull}

Counts the number of null values in the list.

## Category

Aggregation

## Function syntax

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Returns an integer.

## Example

`countOnlyNull([10,2,10,null])`

Returns 1.
