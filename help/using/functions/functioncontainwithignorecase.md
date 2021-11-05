---
product: adobe campaign
title: containIgnoreCase
description: Learn about the function containIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
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
