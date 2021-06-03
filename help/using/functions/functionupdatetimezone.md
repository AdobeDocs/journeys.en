---
product: adobe campaign
title: updateTimeZone
description: Learn about the function updateTimeZone
---

# updateTimeZone {#updateTimeZone}

Returns a new date time, with a new time zone on the same instant.

## Category

Date

## Function syntax

`updateTimeZone(<parameters>)`

## Parameters

* time zone id: string
* dateTime

## Signature and returned type

`updateTimeZone(<dateTime>,<timeZone id>)`

Returns a datetime.

## Example

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Returns 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
