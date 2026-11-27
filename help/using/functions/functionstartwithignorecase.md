---
product: adobe campaign
title: startWithIgnoreCase
description: Learn about the function startWithIgnoreCase
badge: label="Legacy" type="Informative"
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
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
