---
product: adobe campaign
title: toDecimal
description: Learn about the function toDecimal
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
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
