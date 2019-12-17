---
title: startWithIgnoreCase
description: Learn about the function startWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# startWithIgnoreCase {#startWithIgnoreCase}

Returns true if the second parameter is a prefix of the first one without considering case.

## Category

String

## Function syntax

`startWithIgnoreCase(<parameters>)`

## Parameters

| Parameter   | Type  |
|-------------|--------|
| string      | string |
| prefix      | string |

## Signature and returned type

`startWithIgnoreCase(<string>,<string>)`

Return a boolean.

## Example

`startWith("rowing is great', "RO")`

Returns true.
