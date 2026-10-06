---
product: adobe campaign
title: endWithIgnoreCase
description: Learn about the function endWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
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
# endWithIgnoreCase {#endWithIgnoreCase}

Checks if the first argument string ends with a specific string (second argument string), not taking into account the case.

## Category

String

## Function syntax

`endWithIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| suffix  | string |

## Signature and returned type

`endWithIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`endWithIgnoreCase("rowing is great", "AT")`

Returns true.
