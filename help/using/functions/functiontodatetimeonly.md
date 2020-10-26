---
title: toDateTimeOnly
description: Learn about the function toDateTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toDateTimeOnly{#toDateTimeOnly}

Converts an argument value into a date time only value.

## Category

Conversion

## Function syntax

`toDateTimeOnly(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time in ISO-8601 format | string |
| date time | dateTime|

## Signatures and returned types

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Return a datetime without considering time zone.

## Examples

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Returns 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
