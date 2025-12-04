---
product: adobe campaign
title: concat
description: Learn about the function concat
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
---
# concat {#concat}

Concatenates two string parameters or a list of strings.

## Category

String

## Function syntax

`concat(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| List      | listString       |
| string   | string |

## Signature and returned type

`concat(<string>,<string>)`

`concat(<listString>)`

Returns an string.

## Example

`concat("Hello","World")`

Returns "HelloWorld".

`concat(["Hello"," ","World"])`

Returns "Hello World".
