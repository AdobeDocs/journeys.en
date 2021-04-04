---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Learn about the function endWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
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
