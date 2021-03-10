---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Learn about the function toInteger
feature: Journeys
role: Data Engineer
level: Experienced
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

`toInteger("4")`

Returns 4.
