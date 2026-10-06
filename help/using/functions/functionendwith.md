---
product: adobe campaign
title: endWith
description: Learn about the function endWith
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
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
# endWith {#endWith}

Returns true if the second parameter is a suffix of the first one.

## Category

String

## Function syntax

`endWith(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| suffix   | string |

## Signature and returned type

`endWith(<string>,<string>)`

Returns a boolean.

## Example

`endWith("Hello World", "World")`

Returns true.

`endWith("Hello World", "Hello")`

Returns false.
