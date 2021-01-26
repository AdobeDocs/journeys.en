---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Learn about the function gstListItem
---

# getListItem {#gestListItem}

Returns the item of the list at the given index.

## Category

List

## Function syntax

`getListItem(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| list      | listString       |
| list      | listBoolean      |
| list      | listInteger      |
| list      | listDecimal      |
| list      | listDuration     |
| list      | listDateTime     |
| list      | listDateTimeOnly |
| index   | integer          |

## Signatures and returned type

`getListItem(<listInteger>,<index>)`

Returns a list of integers.

`getListItem(<listDecimal>,<index>)`

Returns a list of decimals.

`getListItem(<listString>,<index>)`

Returns a list of strings.

`getListItem(<listDateTimeOnly>,<index>)`

Returns a list of datetimes without considering time zone.

`getListItem(<listDateTime>,<index>)`

Returns a list of datetimes.

`getListItem(<listBoolean>,<index>)`

Returns a list of booleans.

`getListItem(<listDuration>,<index>)`

Returns a list of durations.

## Example

`getListItem([10, 2, 3], 1)`

Returns "2"

`getListItem(["A", "B", "C"], 3)`
Returns "C"

Examples with an event field 'event.appVersion' with value: "20.45.2.3434"

`split(@{event.appVersion}, "\\.")`

Returns `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Returns "20"