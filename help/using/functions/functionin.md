---
product: adobe campaign
title: in
description: Learn about the function in
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
