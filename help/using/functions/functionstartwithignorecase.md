---
product: adobe campaign
title: startWithIgnoreCase
description: Learn about the function startWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
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
# startWithIgnoreCase {#startWithIgnoreCase}

Returns true if the second parameter is a prefix of the first one without considering case.

## Category

String

## Function syntax

`startWithIgnoreCase(<parameters>)`

## Parameters

| Parameter   | Type  |
|-------------|--------|
| string      | string |
| prefix      | string |

## Signature and returned type

`startWithIgnoreCase(<string>,<string>)`

Return a boolean.

## Example

`startWithIgnoreCase("rowing is great", "RO")`

Returns true.
