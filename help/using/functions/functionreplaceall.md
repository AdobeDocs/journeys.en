---
product: adobe campaign
title: replaceAll
description: Learn about the function replaceAll
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
---
# replaceAll {#replaceAll}

Replaces all occurrences matching the target string by the replacement string in the base string.

The replacement proceeds from the beginning of the string to the end, for example, replacing "aa" with "b" in the string "aaa" will result in "ba" rather than "ab".

## Category

String

## Function syntax

`replaceAll(<parameters>)`

## Parameters

| Parameter | Type         |
|-----------|--------------|
| base      | string       |
| target  | string (RegExp)       |
| replacement    | string       |

## Signature and returned type

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Returns a string.

## Example{#example}

`replaceAll("Hello World", "l", "x")`

Returns "Hexxo Worxd".

Because the target parameter is a RegExp, depending on the string you want to replace, you may need to escape some characters. Refer to the example in [this page](../functions/functionreplace.md#example_2).
