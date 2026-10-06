---
product: adobe campaign
title: toString
description: Learn about the function toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
# toString {#toString}

Converts an argument value into a string value, depending on its type. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Conversion

## Function syntax

`toString(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|dateTime|converts the date in UTC date format|
|dateTimeOnly|converts the date in UTC date format|
|duration|convert into the corresponding number of milliseconds as a string|
|integer|converts to string representation of the value (1 becomes “1”)|
|decimal|converts to string representation of the value (1.5 becomes “1.5”)|
|boolean|convert the boolean value as 'true' if true, 'false' if false|

## Signatures and returned type

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Return a string.

## Example

`toString(4)`

Returns "4".
