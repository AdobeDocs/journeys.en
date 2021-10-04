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

Returns a listObject with objects having the key attribute matching one of the given key values.

## Category

List

## Function syntax

`filter(<parameters>)`

## Parameters

| Parameter | Type             | Description             |
|-----------|------------------|------------------|
| listToFilter | listObject | list of objects, to be filtered. It must be a field reference. |
| keyAttributeName | string | attribute name in the objects of the given list, used as key for filtering |
| keyValueList | list | array of key values for filtering |

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

Here is an example of a payload passed in an incoming event "myevent":

```
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

You can use the following expression:

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

Returns a listObject containing the two objects with "product2" and "product3" as id.