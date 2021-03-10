---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Learn about the function countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
---

# countWithNull {#countWithNull}

Counts all the elements of the list including null values.

## Category

Aggregation

## Function syntax

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

Returns an integer.

## Example

`count([10,2,10,null])`

Returns 4.
