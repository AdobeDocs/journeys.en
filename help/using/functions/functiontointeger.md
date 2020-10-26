---
title: toInteger
description: Learn about the function toInteger
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toInteger {#toInteger}

Converts an argument value to an integer.

## Category

Conversion

## Function syntax

`toInteger(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string|converts the string value as an integer|
|dateTime|converts the date as the number of milliseconds (epoch milliseconds)|
|decimal|converts into integer by removing the decimal part (example: 1.5 becomes 1)|
|boolean|converts the boolean value as 1 if true, 0 if false|

## Signatures and returned type

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Return an integer.

## Examples

`toInteger(4)`

Returns 4.
