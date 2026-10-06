---
product: adobe campaign
title: limit
description: Learn about the function limit
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
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
