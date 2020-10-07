---
title: distinctCountWithNull
description: Learn about the function distinctCountWithNull
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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

`distinctCountwithNull(<listAny>)`

Returns an integer.

## Example

`distinctCountWithNull([10,2,10,null])`

Returns 3.
