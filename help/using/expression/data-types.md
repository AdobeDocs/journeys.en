---
title: Data types
description: Learn about data types in advanced expressions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Data types {#concept_gp3_rj5_dgb}

Technically, a constant always contains a data type. In the literal expression, we only specify the value. The data type can be inferred from the value (for example string, integer, decimal, etc.). For specific cases such as date time, we use dedicated functions for the representation.

Here is how data type expressions are represented:

<table>
    <thead>
        <tr>
        <td>Data Type</td>
        <td>Description</td>
        <td>Literal Representation</td>
        <td>Example</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Common sequence of characters.</p><p>It doesn't have any specific size except the implicit one that comes from the environment such as the amount of memory available.</p><p>JSON format: String</p><p>Serialization format: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Integer value from -2^63 to 2^63-1.</p><p>JSON format: Number</p></td>
        <td>&lt;integer value&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Decimal number.</p><p>It represents a floating value:</p>
        <p>- largest positive finite value of type double, (2-2^-52)x2^1023</p>
        <p> - smallest positive normal value of type double, 2-1022</p>
        <p> - smallest positive nonzero value of type double, 2 p-1074</p><p>JSON format: Number</p><p>Serialization format: using '.' as the decimal separator.</p></td>
        <td>&lt;integer value&gt;.&lt;integer value&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Boolean value written lowercase: true or false</p><p>JSON format: Boolean</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Represents a date time without a time zone, viewed as year-month-day-hour-minute-second-millisecond.</p><p>It does not store or represent a time zone.</p><p>Instead, it is a description of the date, as used for birthdays, combined with the local time as seen on a wall clock.</p><p>It cannot represent an instant on the time-line without additional information such as an offset or time zone.</p><p>Serialization format: ISO-8601 extended offset date-time format.</p><p>It uses DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME to deserialize and serialize the value.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Learn more</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Date time constant that also considers time zone.</p><p>It represents a date-time with an offset from UTC. It can be viewed as an instant in time with the additional information of the offset. </p><p>It is a way to represent a specific “moment” at a certain place of the world.</p><p>JSON format: String.</p><p> It must be encapsulated in a toDateTime function.</p><p>
        Serialization format: ISO-8601 extended offset date-time format.</p><p> It uses DateTimeFormatter.ISO_OFFSET_DATE_TIME to deserialize and serialize the value.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Learn more</a>. 
        <p>You can also pass an integer passing an epoch value.</p> <a href="https://www.epochconverter.com/">Read more</a>.</p>
        <p>Time zone can be specified by an offset or a time zone code (example: Europe/Paris, Z - meaning UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime in ISO-8601 format&gt;")</p>
        <p>toDateTime(&lt;integer value of an epoch in milliseconds&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>It represents a time-based amount of time, such as '34.5 seconds'.</p><p> It models a quantity or amount of time in terms of milliseconds.</p><p>The supported temporal units are: milliseconds, seconds, minutes, hours, days where a day equals to 24 hours.</p><p> Years and months are not supported since they're not a fixed amount of time.</p><p>JSON format: String. It must be encapsulated in a toDuration function.</p><p>Serialization format: To deserialize a time zone ID, it uses the java function java.time.</p><p>Duration.parse: the formats accepted are based on the ISO-8601 duration format PnDTnHnMn.nS with days considered to be exactly 24 hours.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Learn more</a>.</td>
        <td><p>toDuration("&lt;duration in ISO-8601 format&gt;")</p><p>toDuration(&lt;duration in milliseconds&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 seconds</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>-- parses as "20.345 seconds"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> -- parses as "15 minutes"</pre></p>
        <p><pre>(where a minute is 60 seconds)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>-- parses as "10 hours"</pre></p>
        <p><pre>(where an hour is 3600 seconds)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>-- parses as "2 days"</pre></p>
        <p><pre>(where a day is </pre></p>
        <p><pre>24 hours or 86400 seconds)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"2 days, 3 hours and 4 minutes"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"-6 hours and +3 minutes"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"-6 hours and -3 minutes"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"+6 hours and -3 minutes"</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>Comma separated list of expressions using square brackets as delimiters. Polymorphism is not supported, hence all the expressions contained in the list should have the same type.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
