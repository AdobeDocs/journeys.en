---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Learn about the function notEqualWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
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
