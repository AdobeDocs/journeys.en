---
product: adobe campaign
title: in
description: Learn about the function in
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
| List      | listDateOnly     |

## Signature and returned type

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Return a boolean.

## Example

`in(4,[4,5,3,4])`

Returns true.

`in(8,[4,5,3,4])`

Returns false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
