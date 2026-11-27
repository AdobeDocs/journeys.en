---
product: adobe campaign
title: endWithIgnoreCase
description: Learn about the function endWithIgnoreCase
badge: label="Legacy" type="Informative"
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
