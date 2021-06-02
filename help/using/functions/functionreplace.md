---
product: adobe campaign
title: replace
description: Learn about the function replace
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
---
# replace {#replace}

Replaces the first occurrence matching the target string by the replacement string in the base string.

The replacement proceeds from the beginning of the string to the end, for example, replacing "aa" with "b" in the string "aaa" will result in "ba" rather than "ab".

## Category

String

## Function syntax

`replace(<parameters>)`

## Parameters

| Parameter | Type         |
|-----------|--------------|
| base      | string       |
| target    | string       |
| replacement  | string    |

## Signature and returned type

`replace(<base>,<target>,<replacement>)`

Return a string.

## Example

`replace("Hello World", "l", "x")`

Returns "Hexlo World".
