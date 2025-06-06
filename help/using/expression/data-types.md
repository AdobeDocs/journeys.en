---
product: adobe campaign
title: Data types
description: Learn about data types in advanced expressions
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
---
# Data types {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


Technically, a constant always contains a data type. In the literal expression, we only specify the value. The data type can be inferred from the value (for example string, integer, decimal, etc.). For specific cases such as date time, we use dedicated functions for the representation.

The sections below provide information on the different data type expressions and how they are represented.

## string {#string}

**Description**

Common sequence of characters. It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available.

JSON format: String

Serialization format: UTF-8

**Literal representation**

```json
"<value>"
```

```json
'<value>'
```

**Example**

```json
"hello world"
```

```json
'hello world'
```

## integer {#integer}

**Description**

Integer value from -2^63 to 2^63-1.

JSON format: Number

**Literal representation**

```json
<integer value>
```

**Example**

```json
42
```

## decimal {#decimal}

**Description**

Decimal number. It represents a floating value:

* largest positive finite value of type double, (2-2^-52)x2^1023
* smallest positive normal value of type double, 2-1022
* smallest positive nonzero value of type double, 2 p-1074

JSON format: Number

Serialization format: using '.' as the decimal separator.

**Literal representation**

```json
<integer value>.<integer value>
```

**Example**

```json
3.14
```

## boolean {#boolean}

**Description**

Boolean value written lowercase: true or false

JSON format: Boolean

**Literal representation**

```json
true
```

```json
false
```

**Example**

```json
true
```

## dateOnly {#date-only}

**Description**

Represents a date only without a time zone, viewed as a year-month-day.

It is a description of the date, as used for birthdays.

JSON format: String.

Format is: YYYY-MM-DD (ISO-8601), for example: "2021-03-11".

It can be encapsulated in a toDateOnly function.

It uses DateTimeFormatter ISO_LOCAL_DATE_TIME to deserialize and serialize the value. [Learn more](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Literal representation**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Example**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Description**

Represents a date time without a time zone, viewed as year-month-day-hour-minute-second-millisecond.

JSON format: String.

It does not store or represent a time zone. Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock.

It cannot represent an instant on the time-line without additional information such as an offset or time zone.

It can be encapsulated in a toDateTimeOnly function.

Serialization format: ISO-8601 extended offset date-time format.

It uses DateTimeFormatter ISO_LOCAL_DATE_TIME to deserialize and serialize the value. [Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME")

**Literal representation**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Examples**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Description**

Date time constant that also considers time zone. It represents a date-time with an offset from UTC.

It can be viewed as an instant in time with the additional information of the offset. It is a way to represent a specific "moment" at a certain place of the world.

JSON format: String.

It can be encapsulated in a toDateTime function.

Serialization format: ISO-8601 extended offset date-time format.

It uses DateTimeFormatter ISO_OFFSET_DATE_TIME to deserialize and serialize the value. [Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME) 

You can also pass an integer passing an epoch value. [Read more](https://www.epochconverter.com)

Time zone can be specified by an offset or a time zone code (example: Europe/Paris, Z - meaning UTC).

**Literal representation**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Examples**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## duration {#duration}

**Description**

It represents a time-based amount of time, such as '34.5 seconds'. It models a quantity or amount of time in terms of milliseconds.

The supported temporal units are: milliseconds, seconds, minutes, hours, days where a day equals to 24 hours. Years and months are not supported since they're not a fixed amount of time.

JSON format: String.

It must be encapsulated in a toDuration function.

Serialization format: To deserialize a time zone ID, it uses the java function java.time.

Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours. [Learn more](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Literal representation**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Example**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Description**

Comma separated list of expressions using square brackets as delimiters.

Polymorphism is not supported, hence all the expressions contained in the list should have the same type.

**Literal representation**

```json
[<expression>, <expression>, ... ]
```

**Example**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
