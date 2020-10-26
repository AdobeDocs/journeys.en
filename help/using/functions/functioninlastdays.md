---
title: inLastDays
description: Learn about the function inLastDays
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# inLastDays {#inLastDays}

Returns true if a given date or dateTime is between now and now - delta days.

## Category

Date

## Function syntax

`inLastDays(<dateTime>,<delta>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time | dateTime    |
| delta   | integer     |

## Signatures and returned type

`inLastDays(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Returns true.
