---
title: updateTimeZone
description: Learn about the function updateTimeZone
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
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
