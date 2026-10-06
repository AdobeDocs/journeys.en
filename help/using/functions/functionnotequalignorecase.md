---
product: adobe campaign
title: notEqualIgnoreCase
description: Learn about the function notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
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
# notEqualIgnoreCase {#notEqualIgnoreCase}

Check if the first argument string with the second argument string are different, ignoring case considerations.

## Category

String

## Function syntax

`notEqualIgnoreCase(<parameters>)`

## Parameters

* string

## Signature and returned type

`notEqualIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
