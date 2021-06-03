---
product: adobe campaign
title: containWithIgnoreCase
description: Learn about the function containWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
---
# containWithIgnoreCase {#containWithIgnoreCase}

Checks if the second argument string is contained in the first argument string, without taking into account the case.

## Category

String

## Function syntax

`containWithIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| string searched   | string |

## Signature and returned type

`containWithIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`containWithIgnoreCase("rowing is great', "GREAT")`

Returns true.
