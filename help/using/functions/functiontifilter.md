---
product: adobe campaign
title: filter
description: Learn about the function fister
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
---
# filter{#filter}

Returns a JsonArray with objects having the key attribute matching one of the given key values.

## Category

List

## Function syntax

`filter(jsonArray arrayToFilter, string keyAttributeName, list keyValueList`: jsonArray

## Arguments	

| Argument | Description             |
|-----------|------------------|
| arrayToFilter | json array of objects, to be filtered |
| keyAttributeName | attribute name in the objects of arrayToFilter, used as key for filtering |
| keyValuelist | array of key values for filtering |

## Signatures and returned types

`filter(listObject, string, listString)`
`filter(listObject, string, listlnteger)`
`filter(listObject, string, listDecimal)`
`filter(listObject, string, listDateTime)`
`filter(listObject, string, listDateTimeOnly)`
`filter(listObject, string, listDateOnly)`
`filter(listObject, string, listDuration)`
`filter(lisObject, string, listBoolean)`

Returns a lisObject.

## Examples

