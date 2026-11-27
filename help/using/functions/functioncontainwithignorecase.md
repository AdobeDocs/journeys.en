---
product: adobe campaign
title: containIgnoreCase
description: Learn about the function containIgnoreCase
badge: label="Legacy" type="Informative"
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
---
# containIgnoreCase {#containIgnoreCase}

Checks if the second argument string is contained in the first argument string, without taking into account the case.

## Category

String

## Function syntax

`containIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| string searched   | string |

## Signature and returned type

`containIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`containIgnoreCase("rowing is great", "GREAT")`

Returns true.
