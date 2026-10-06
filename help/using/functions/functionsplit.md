---
product: adobe campaign
title: split
description: Learn about the function split
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
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
