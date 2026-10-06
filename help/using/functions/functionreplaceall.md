---
product: adobe campaign
title: replaceAll
description: Learn about the function replaceAll
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
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
