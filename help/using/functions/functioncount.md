---
title: count
description: Learn about the function count
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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

## Signatures and returned type

`count(<listAny>)`

Returns an integer.

## Example

`count([10,2,10,null])`

Returns 3.
