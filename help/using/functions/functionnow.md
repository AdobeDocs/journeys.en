---
product: adobe campaign
title: now
description: Learn about the function now
badge: label="Legacy" type="Informative"
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
---
# now {#now}

Returns the current date in date time format. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Date

## Function syntax

`now(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|string||

## Signatures and returned type

`now()`

`now("<timeZone id>")`

Returns a dateTime.

## Examples

`now()`

 Returns 2019-06-03T06:30Z.

`toString(now())`

Returns "2019-06-03T06:30Z"

`now("Europe/Paris")`

Returns 2019-06-03T08:30+02:00.
