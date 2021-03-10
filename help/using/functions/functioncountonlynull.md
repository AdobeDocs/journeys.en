---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Learn about the function countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
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

## Signature and returned type

`countOnlyNull(<listAny>)`

Returns an integer.

## Example

`count([10,2,10,null])`

Returns 1.
