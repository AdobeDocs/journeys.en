---
title: toDuration
description: Learn about the function toDuration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toDuration {#toDuration}

Converts an argument value to a duration. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Conversion

## Function syntax

`toDuration(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string|formats based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours|
|integer|number of milliseconds|

If string expression: formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours.

The string starts with an optional sign, denoted by the ASCII negative or positive symbol. If negative, the whole period is negated. The ASCII letter "P" is next in upper or lower case. There are then four sections, each consisting of a number and a suffix. The sections have suffixes in ASCII of "D", "H", "M" and "S" for days, hours, minutes and seconds, accepted in upper or lower case. The suffixes must occur in order. The ASCII letter "T" must occur before the first occurrence, if any, of an hour, minute or second section. At least one of the four sections must be present, and if "T" is present there must be at least one section after the "T". The number part of each section must consist of one or more ASCII digits. The number may be prefixed by the ASCII negative or positive symbol. The number of days, hours and minutes must parse to along. The number of seconds must parse to along with optional fraction. The decimal point may be either a dot or a comma. The fractional part may have from zero to 9 digits.

## Signatures and returned type

`toDuration(<string>)`

`toDuration(<integer>)`

Returns a duration.

## Examples

`toDuration("PT10H")`

Returns duration of 10 hours.

`toDuration("PT4S")`

Returns duration of 4s.

`toDuration(4000)`

Returns duration of 4s.
