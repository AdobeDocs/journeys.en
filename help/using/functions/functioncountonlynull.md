---
product: adobe campaign
title: countOnlyNull
description: Learn about the function countOnlyNull
badge: label="Legacy" type="Informative"
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
