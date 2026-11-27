---
product: adobe campaign
title: notEqualIgnoreCase
description: Learn about the function notEqualIgnoreCase
badge: label="Legacy" type="Informative"
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
