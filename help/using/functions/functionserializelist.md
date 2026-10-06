---
product: adobe campaign
title: serializeList
description: Learn about the function serializeList
feature: Journeys
role: Developer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
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
# serializeList {#serializeList}

Converts the list (any type) given in the first parameter to a string. The second parameter represents the separator to use. The third parameter is a boolean value indicating if each element of the expression should include quotes.

## Category

List

## Function syntax

`serializeList(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| String    | String           |
| Boolean   | Boolean          |
| DateTimeOnly | DateTimeOnly  |
| List      | listString       |
| List      | listBoolean      |
| List      | listPoint        |
| List      | listDecimal      |
| List      | listDuration     |
| List      | listDateTime     |
| List      | listDateTimeOnly |
| List      | listDateOnly     |

## Signature and returned type

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Return a string.

## Example

`serializeList(["Hello","World"], " ", false)`

Returns "Hello World".

`serializeList(["Hello", "World"], ",", true)`

Returns ""Hello","World"".
