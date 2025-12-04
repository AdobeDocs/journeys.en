---
product: adobe campaign
title: toDateTime
description: Learn about the function toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
---
# toDateTime {#toDateTime}

Converts parameters into a date time value, depending on their types.

## Category

Conversion

## Function syntax

`toDateTime(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| date time in ISO-8601 format| string |
| time zone id | string |
| date time without time zone | dateTimeOnly|
| integer value of an epoch in milliseconds| integer |

>[!NOTE]
>
>Time zone id must be a string constant. It cannot be a field reference nor an expression. For more information on data types, refer to [this page](../expression/data-types.md).

## Signatures and returned types

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

Return a **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Examples

`toDateTime ("2016-08-18T23:17:59.123Z")`

Returns 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

Returns 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Returns 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
