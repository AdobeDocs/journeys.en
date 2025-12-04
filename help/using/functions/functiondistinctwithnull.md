---
product: adobe campaign
title: distinctWithNull
description: Learn about the function distinctWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
---
# distinctWithNull {#distinctWithNull}

Returns the distinct values or objects of a given list. If the list has at least one null entry, a null entry will be present in the returned list.

## Category

List

## Function syntax

`distinctWithNull(<parameters>)`

## Parameters

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | List to process. For listObject, it must be a field reference. |
| keyAttributeName | string | This parameter is optional and only for listObject. If the parameter is not provided, an object is considered as duplicated if all the attributes have the same values. Otherwise, an object is considered as duplicated if the given attribute has the same value. |

## Signatures and returned types

`distinctWithNull(<listInteger>)`

Returns a list of integers.

`distinctWithNull(<listDecimal>)`

Returns a list of decimals.

`distinctWithNull(<listString>)`

Returns a list of strings.

`distinctWithNull(<listDateTimeOnly>)`

Returns a list of datetimes without considering time zone.

`distinctWithNull(<listDateTime>)`

Returns a list of datetimes.

`distinctWithNull(<listDateOnly>)`

Returns a list of dates.

`distinctWithNull(<listBoolean>)`

Returns a list of booleans.

`distinctWithNull(<listDuration>)`

Returns a list of durations.

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

Returns a list of objects.

## Examples

`distinctWithNull([10,2,10,null])`

Returns [10, 2, null]
