---
title: toBool
description: Learn about the function toBool
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
---

# toBool {#toBool}

Converts an argument value into a boolean value, depending on its type.

* From string: try to convert the string value as a boolean, from "true" or "false" string to true or false.
* From numerical: true if the numerical value is not equal to 0, false if equal to 0.
* From boolean: idempotent

## Category

Conversion

## Function syntax

`toBool(<parameter>)`

## Parameters

* decimal
* boolean
* string
* integer

## Signatures and return types

`toBool(<decimal>)`
`toBool(<boolean>)`
`toBool(<string>)`
`toBool(<integer>)`

Return a boolean.

## Examples

`toBool("true")`
`toBool(1)`

Returns true.

`toBool("this is not a boolean")`

Returns false.
