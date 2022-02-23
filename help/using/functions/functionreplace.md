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
| target    | string (RegExp)       |
| replacement  | string    |

## Signature and returned type

`replace(<base>,<target>,<replacement>)`

Return a string.

## Example 1

`replace("Hello World", "l", "x")`

Returns "Hexlo World".

## Example 2 {#example_2}

Because the target parameter is a RegExp, depending on the string you want to replace, you may need to escape some characters. Here is an example.

* string to evaluate : `|OFFER_A|OFFER_B`
* provided by a profile attribute `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* String to be replaced : `|OFFER_A`
* String replaced by : `''`
* You need to add `\\` before the `|` character.

The expression is:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

The returned string is: `|OFFER_B`

You can also build the string to be replaced from a given attribute:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
