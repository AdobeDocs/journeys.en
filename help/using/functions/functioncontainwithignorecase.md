---
product: adobe campaign
title: containIgnoreCase
description: Learn about the function containIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
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
# containIgnoreCase {#containIgnoreCase}

Checks if the second argument string is contained in the first argument string, without taking into account the case.

## Category

String

## Function syntax

`containIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| string searched   | string |

## Signature and returned type

`containIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`containIgnoreCase("rowing is great", "GREAT")`

Returns true.
