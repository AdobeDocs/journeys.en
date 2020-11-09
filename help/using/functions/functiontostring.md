---
title: toString
description: Learn about the function toString
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# toString {#toString}

Converts an argument value into a string value, depending on its type. For more information on data types, refer to [this page](../expression/data-types.md).

## Category

Conversion

## Function syntax

`toString(<parameter>)`

## Parameters

|Parameter|Description|
|--- |--- |
|dateTime|converts the date in UTC date format|
|dateTimeOnly|converts the date in UTC date format|
|duration|convert into the corresponding number of milliseconds as a string|
|time zone|convert into the time zone id string representation (JODA id)|
|integer|converts to string representation of the value (1 becomes “1”)|
|decimal|converts to string representation of the value (1.5 becomes “1.5”)|
|boolean|convert the boolean value as 'true' if true, 'false' if false|

## Signatures and returned type

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Return a string.

## Example

`toString(4)`

Returns "4".
