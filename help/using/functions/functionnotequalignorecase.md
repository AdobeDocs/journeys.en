---
title: notEqualWithIgnoreCase
description: Learn about the function notEqualWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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
