---
title: substr
description: Learn about the function substr
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# substr {#substr}

Returns the sub-string of the string expression between the begin index and the end index. If the end index is not defined, then it is between the begin index and the end.

## Category

String

## Function syntax

`substr(<parameters>)`

## Parameters

| Parameter  | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Signature and returned type

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Return a string.

## Example

`substr("Hello World",6)`

Returns "World".

`substr("Hello World", 0, 5)`

Returns "Hello".