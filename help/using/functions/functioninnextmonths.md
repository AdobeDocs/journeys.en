---
title: inNextMonths
description: Learn about the function inNextMonths
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# inNextMonths {#inNextMonths}

Returns true if a given date or dateTime is between now and now + delta months.

## Category

Date

## Function syntax

`inNextMonths(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inNextMonths(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Returns true.
