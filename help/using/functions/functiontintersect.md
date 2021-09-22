---
product: adobe campaign
title: intersect
description: Learn about the function intersect
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
---
# intersect{#intersect}

Returns the common values in the two input lists. If one of the two lists is null, returns an empty list.

## Category

List

## Function syntax

`intersect(list listl, list list2)`: list

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date in ISO-8601 or "YYYY-MM-DD" format (XDM Date format) | string |
| date | date |

## Signatures and returned types

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listlnteger,listlnteger)`: listlnteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Returns a list.

## Examples

