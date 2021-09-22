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

Returns a listObject with objects having the key attribute matching one of the given key values

## Category

List

## Function syntax

`filter(<parameters>)`

## Parameters	

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToFilter | listObject | list of objects, to be filtered. It must be a field reference. |
| keyAttributeName | string | attribute name in the objects of the the given list, used as key for filtering |
| keyValuelist | list | array of key values for filtering |

## Signatures and returned types

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Returns a listObject.

## Examples

rajouter payload

```
filter(
	@{myevent.productListItems},
	"_id",
	["product 2","product 3","product 4"]
)
```

Returns a listobject containing product 2 and product 3. 
