---
product: adobe campaign
solution: Journey Orchestration
title: Operators
description: Learn about operators in advanced expressions
feature: Journeys
role: Data Engineer
level: Experienced
---


# Operators {#concept_wd5_pj5_dgb}

There are two kinds of operators: unary operators and binary operators. There are left-hand unary operators and right-hand unary operators.

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Here is the list of supported operators:

## Logical  {#logical}

### and

```
<expression1> and <expression2>
```

Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean. The result is boolean.

Example:

```
3.14 > 2 and 3.15 < 1
```

### or



```
<expression1> or <expression2>
```

Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean. The result is boolean.

Example:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression&gt; must be boolean. The result is boolean.

Example:

```
not 3.15 < 1
```

## Comparison {#comparison}

### is null



```
<expression> is null
```

The result is boolean.

Note that null means the expression has no evaluated value.

Example:

```
@{BarBeacon.location} is null
```

### is not null



```
<expression> is not null
```

The result is boolean.

Note that null means the expression has no evaluated value.

Example:

```
@ is not null
```

### has null



```
<expression> has null
```

&lt;expression&gt; must be a list. The result is boolean.

Useful to identify that a list contains at least one null value.

Example:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type. The result is boolean.

Example:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type. The result is boolean.

Example:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

The result is boolean.

Example:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

The result is boolean.

Example:

```
42 >= 3.14
```

### <



```
<expression1> < <expression2>
```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

The result is boolean.

Example:

```
42 < 3.14
```

### <=



```
<expression1> <= <expression2>
```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

The result is boolean.

Example:

```
42 <= 3.14
```

## Arithmetic {#arithmetic}

### +



```
<expression1> + <expression2>
```

Both expressions must be numeric (integer or decimal). 

The result is also numeric.

Example:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

Example:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Both expressions must be numeric (integer or decimal). 

The result is also numeric.

&lt;expression2&gt; must not be equal to 0 (returns 0).

Example:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

Example:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

Example:

```
3 % 2 -- returns 1.
```

## Math {#math}

### is numeric



```
<expression> is numeric
```

The type of the expression is integer or decimal.

Example:

```
@ is numeric
```

### is integer



```
<expression> is integer
```

The type of the expression is integer.

Example:

```
@ is integer
```

### is decimal



```
<expression> is decimal
```

The type of the expression is decimal.

Example:

```
@ is decimal
```

## String {#string}

### + 



```
<string> + <expression>
```

```
<expression> + <string>
```

It concatenates two expressions. 

One expression must be a chained string.

Example:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Date {#date}

### +



```
<expression + <duration>
```

Append a duration to a dateTime, a dateTimeOnly or a duration.

Example:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
