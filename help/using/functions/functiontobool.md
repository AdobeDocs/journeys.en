---
product: adobe campaign
title: toBool
description: Learn about the function toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
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
# toBool {#toBool}

Converts an argument value into a boolean value, depending on its type.

* From string: try to convert the string value as a boolean, from "true" if the string value is "true", false otherwise
* From numerical: true if the numerical value is not equal to 0, false otherwise

## Category

Conversion

## Function syntax

`toBool(<parameter>)`

## Parameters

* decimal
* boolean
* string
* integer

## Signatures and returned types

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Return a boolean.

## Examples

`toBool("true")`

`toBool(1)`

Returns true.

`toBool("this is not a boolean")`

Returns false.
