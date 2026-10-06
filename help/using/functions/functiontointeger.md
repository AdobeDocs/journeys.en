---
product: adobe campaign
title: toInteger
description: Learn about the function toInteger
feature: Journeys
role: Developer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
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
