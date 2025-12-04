---
product: adobe campaign
title: sort
description: Learn about the function sort
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
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

