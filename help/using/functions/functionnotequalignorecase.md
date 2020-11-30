---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Learn about the function notEqualWithIgnoreCase
---

# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Check if the first argument string with the second argument string are different, ignoring case considerations.

## Category

String

## Function syntax

`notEqualWithIgnoreCase(<parameters>)`

## Parameters

* string

## Signature and returned type

`notEqualWithIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
