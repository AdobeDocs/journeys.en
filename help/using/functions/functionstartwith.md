---
product: adobe campaign
title: startWith
description: Learn about the function startWith
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
---
# startWith {#startWith}

Returns true if the second parameter is a prefix of the first one.

## Category

String

## Function syntax

`startWith(<parameters>)`

## Parameters

| Parameter   | Type  |
|-------------|--------|
| string      | string |
| prefix      | string |

## Signature and returned type

`startWith(<string>,<string>)`

Return a boolean.

## Example

`startWith("Hello World", "Hello")`

Returns true.

`startWith("Hello World", "World")`

Returns false.
