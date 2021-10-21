---
product: adobe campaign
title: countWithNull
description: Learn about the function countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
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

`countWithNull([10,2,10,null])`

Returns 4.
