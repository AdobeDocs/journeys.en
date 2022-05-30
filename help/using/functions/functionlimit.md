---
product: adobe campaign
title: limit
description: Learn about the function limit
feature: Journeys
role: Data Engineer
level: Experienced
---
# limit {#limit}

Returns the first or last N elements of a list.

## Category

List

## Function syntax

`limit(<parameters>)`

## Parameters

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly, or listObject | List to sort out. For listObject, it must be a field reference. |
| numberOfItems | integer | Number of items to be returned from the given list. |
| firstOrLastItems | boolean | This parameter is optional (true by default). true returns the first items. false returns the last items. |

## Signature and returned type

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Returns a list of strings.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Returns a list of integers.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Returns a list of decimals.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Returns a list of booleans.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Returns a list of dates.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Returns a list of datetimes without considering time zone.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Returns a list of datetimes.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Returns a list of durations.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Returns a list of objects.

## Example

`limit(["A", "B", "C", "D", "E"], 3)`

Returns `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Returns `["C","D","E"]`.
