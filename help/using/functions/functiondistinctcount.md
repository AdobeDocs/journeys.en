---
title: distinctCount
description: Learn about the function distinctCount
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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

## Signature and returned type

`distinctCount(<listAny>)`

Returns an integer.

## Example

`distinctCount([10,2,10,null])`

Returns 2.
