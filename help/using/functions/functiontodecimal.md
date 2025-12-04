---
product: adobe campaign
title: toDecimal
description: Learn about the function toDecimal
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
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
