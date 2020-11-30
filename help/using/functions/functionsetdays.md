---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Learn about the function setDays
---

# setDays {#setDays}

Sets the day of a date time or date time only. For example, if you want to wait until a certain day of the month, you can force the day.

## Category

Date

## Function syntax

`setDays(<parameter>)`

## Parameters

|Parameter|Type|
|--- |--- |
|date time|dateTime|
|date time without considering time zone|dateTimeOnly|
|days|integer|

## Signatures and returned type

`setDays(<dateTime>,<days>)`

Returns a datetime.

`setDays(<dateTimeOnly>,<days>)`

Returns a datetime without considering time zone.

## Examples

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Returns 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
