---
title: toTimeZone
description: Learn about the function toTimeZone
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toTimeZone {#toTimeZone}

Converts a string value to a time zone.

## Category

Conversion

## Function syntax

`toTimeZone(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string|The string value must contain the zone id. It can be a field reference or an expression|

## Signatures and returned types

`toTimeZone(<string>)`

Returns a time zone.

## Examples

`toTimeZone("UTC")`

Returns UTC.
