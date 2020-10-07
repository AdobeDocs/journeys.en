---
title: startWith
description: Learn about the function startWith
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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
