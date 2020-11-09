---
title: toDecimal
description: Learn about the function toDecimal
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toDecimal {#toDecimal}

Converts an argument value into a decimal value, depending on its type.

## Category

Conversion

## Function syntax

`toDecimal(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string|converts the string value as a decimal|
|dateTime|converts the date as the number of milliseconds (epoch milliseconds)|
|boolean|converts the boolean value as 1 if true, 0 if false|
|integer|converts to a decimal (example.: 1 becomes 1.0)|

## Signatures and returned types

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Return a decimal.

## Examples

`toDecimal("4.0")`

Returns 4.0.
