---
product: adobe campaign
title: split
description: Learn about the function split
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
---
# split {#split}

Splits the first argument string with a separator string (second argument string, which can be a regular expression) to produce a list of strings (tokens).

## Category

String

## Function syntax

`split(<parameters>)`

## Parameters

|Parameter|Type|
|-----------|------------------|
|input string|string|
|separator string|string|

## Signatures and returned type

`split(<input string>, <separator string>)`

Returns a listString.

## Example

`split(["A_B_C"], "_")`

Returns `["A","B","C"]`

Example with an event field 'event.appVersion' with value: "20.45.2.3434"

`split(@{event.appVersion}, "\\.")`

Returns `["20", "45", "2", "3434"]`
