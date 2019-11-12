---
title: inLastDays
description: Learn about the function inLastDays
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
---

# inLastDays {#inLastDays}

Function defining if a given date or dateTime is between now and now - delta days.

## Category

Date

## Function syntax

`inLastDays(<parameter>)`

## Parameters

* dateTime
* integer

## Signatures and return type

`inLastDays(<dateTime>,<integer>)`

Returns a boolean.

## Examples

`inLastDays(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returns true.