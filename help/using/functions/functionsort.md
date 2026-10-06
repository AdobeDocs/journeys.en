---
product: adobe campaign
title: sort
description: Learn about the function sort
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
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
# sort {#sort}

Sorts a list of values or objects in the natural order.

## Category

List

## Function syntax

`sort(<parameters>)`

## Parameters

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | List to sort out. For listObject, it must be a field reference. |
| keyAttributeName | string | This parameter is only for listObject. The attribute name in the objects of the given list is used as key for sorting. |
| sortingOrder | boolean | Ascending (true) or descending (false) |

## Signature and returned type

`sort(<listInteger>,<boolean>)`

Returns a list of integers.

`sort(<listDecimal>,<boolean>)`

Returns a list of decimals.

`sort(<listString>,<boolean>)`

Returns a list of strings.

`sort(<listDateTimeOnly>,<boolean>)`

Returns a list of datetimes without considering time zone.

`sort(<listDateTime>,<boolean>)`

Returns a list of datetimes.

`sort(<listDateOnly>,<boolean>)`

Returns a list of dates.

`sort(<listBoolean>,<boolean>)`

Returns a list of booleans.

`sort(<listObject>,<string>,<boolean>)`

Returns a list of objects.

## Example

`sort(["A", "C", "B"], true)`

Returns `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returns `[3, 2, 1]`.

