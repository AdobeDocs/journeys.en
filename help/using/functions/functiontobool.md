---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Learn about the function toBool
---

# toBool {#toBool}

Converts an argument value into a boolean value, depending on its type.

* From string: try to convert the string value as a boolean, from "true" if the string value is "true", false otherwise
* From numerical: true if the numerical value is not equal to 0, false otherwise

## Category

Conversion

## Function syntax

`toBool(<parameter>)`

## Parameters

* decimal
* boolean
* string
* integer

## Signatures and returned types

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
