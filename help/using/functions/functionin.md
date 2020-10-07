---
title: in
description: Learn about the function in
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# in {#in}

Checks if the first argument value is in the list. The check is performed through an Equal on each argument value. It returns true if the argument value is found, false otherwise.

The type of the `<expression>` must match with items of the list. Types of items of the list, as a reminder, must match with each other.

## Category

List

## Function syntax

`in(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| String    | String       |
| Boolean   | Boolean      |
| Integer   | Integer      |
| Decimal   | Decimal      |
| Duration  | Duration     |
| DateTime  | DateTime     |
| DateTimeOnly  | DateTimeOnly |
| List      | listString       |
| List      | listBoolean      |
| List      | listInteger      |
| List      | listDecimal      |
| List      | listDuration     |
| List      | listDateTime     |
| List      | listDateTimeOnly |

## Signature and returned type

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Return a boolean.

## Example

`in(4,[4,5,3,4])`

Returns true.

`in(8,[4,5,3,4])`

Returns false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
