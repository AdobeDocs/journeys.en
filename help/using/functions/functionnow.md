---
title: now
description: Learn about the function now
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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