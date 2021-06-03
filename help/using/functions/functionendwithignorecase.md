---
product: adobe campaign
title: endWithIgnoreCase
description: Learn about the function endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
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

`endWithIgnoreCase("rowing is great', "AT")`

Returns true.
