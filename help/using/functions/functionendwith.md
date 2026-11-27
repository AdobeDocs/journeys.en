---
product: adobe campaign
title: endWith
description: Learn about the function endWith
badge: label="Legacy" type="Informative"
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
---
# endWith {#endWith}

Returns true if the second parameter is a suffix of the first one.

## Category

String

## Function syntax

`endWith(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| suffix   | string |

## Signature and returned type

`endWith(<string>,<string>)`

Returns a boolean.

## Example

`endWith("Hello World", "World")`

Returns true.

`endWith("Hello World", "Hello")`

Returns false.
