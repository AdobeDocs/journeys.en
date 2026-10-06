---
product: adobe campaign
title: replace
description: Learn about the function replace
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
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

Because the target parameter is a RegExp, depending on the string you want to replace, you may need to escape some characters. Here is an example:

* string to evaluate: `|OFFER_A|OFFER_B`
* provided by a profile attribute `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* String to be replaced: `|OFFER_A`
* String replaced by: `''`
* You need to add `\\` before the `|` character.

The expression is:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

The returned string is: `|OFFER_B`

You can also build the string to be replaced from a given attribute:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
