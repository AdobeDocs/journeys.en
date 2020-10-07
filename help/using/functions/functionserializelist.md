---
title: serializeList
description: Learn about the function serializeList
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# serializeList {#serializeList}

Converts the list (any type) given in the first parameter to a string. The second parameter represents the separator to use. The third parameter is a boolean value indicating if each element of the expression should include quotes.

## Category

List

## Function syntax

`serializeList(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| String    | String           |
| Boolean   | Boolean          |
| DateTimeOnly | DateTimeOnly  |
| List      | listString       |
| List      | listBoolean      |
| List      | listPoint        |
| List      | listDecimal      |
| List      | listDuration     |
| List      | listDateTime     |
| List      | listDateTimeOnly |

## Signature and returned type

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Return a string.

## Example

`serializeList(["Hello","World"], " ", false)`

Returns "Hello World".

`serializeList(["Hello", "World"], ",", true)`

Returns ""Hello","World"".
