---
product: adobe campaign
solution: Journey Orchestration
title: gestListItem
description: Learn about the function gestListItem
---

# gestListItem {#gestListItem}

Returns the item of the list at the given index.

## Category

List

## Function syntax

`gestListItem(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| List      | listString       |
| List      | listBoolean      |
| List      | listInteger      |
| List      | listDecimal      |
| List      | listDuration     |
| List      | listDateTime     |
| List      | listDateTimeOnly |

## Signatures and returned type

`gestListItem(<listInteger>)`

Returns a list of integers.

`gestListItem(<listDecimal>)`

Returns a list of decimals.

`gestListItem(<listString>)`

Returns a list of strings.

`gestListItem(<listDateTimeOnly>)`

Returns a list of datetimes without considering time zone.

`gestListItem(<listDateTime>)`

Returns a list of datetimes.

`gestListItem(<listBoolean>)`

Returns a list of booleans.

`gestListItem(<listDuration>)`

Returns a list of durations.

## Example

`getListItem([10, 2, 3], 1)`

Returns "2"

`getListItem(["A", "B", "C"], 3)`
Returns "C"

Examples with an event field 'event.appVersion' with value: 20.45.2.3434

`split(@{event.appVersion}, "\\.")`

Returns `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Returns "20"