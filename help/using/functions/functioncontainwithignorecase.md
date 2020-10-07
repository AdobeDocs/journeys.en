---
title: containWithIgnoreCase
description: Learn about the function containWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# containWithIgnoreCase {#containWithIgnoreCase}

Checks if the second argument string is contained in the first argument string, without taking into account the case.

## Category

String

## Function syntax

`containWithIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| string   | string |
| string searched   | string |

## Signature and returned type

`containWithIgnoreCase(<string>,<string>)`

Returns a boolean.

## Example

`containWithIgnoreCase("rowing is great', "GREAT")`

Returns true.
