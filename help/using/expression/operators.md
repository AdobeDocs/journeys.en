---
product: adobe campaign
solution: Journey Orchestration
title: Operators
description: Learn about operators in advanced expressions
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

**Literal expression**

```<expression1> and <expression2>```

Both <expression1> and <expression2> must be boolean. The result is boolean.

**Example**

```3.14 > 2 and 3.15 < 1```

### or

**Literal expression**

```<expression1> or <expression2>```

Both <expression1> and <expression2> must be boolean. The result is boolean.

**Example**

```3.14 > 2 or 3.15 < 1```

### not

**Literal expression**

```not <expression>```

<expression> must be boolean. The result is boolean.

**Example**

```not 3.15 < 1```

## Comparison {#comparison}

### is null

**Literal expression**

```<expression> is null```

The result is boolean.

Note that null means the expression has no evaluated value.

**Example**

```@{BarBeacon.location} is null```

### is not null

**Literal expression**

```<expression> is not null```

The result is boolean.

Note that null means the expression has no evaluated value.

**Example**

```@ is not null```

### has null

**Literal expression**

```<expression> has null```

<expression> must be a list. The result is boolean.

Useful to identify that a list contains at least one null value.

**Example**

```[&#34;foo&#34;, &#34;bar&#34;, null] has null``` returns true

```[&#34;foo&#34;, &#34;bar&#34;, &#34;&#34;] has null``` returns false because &#34;&#34; is not considered as null.

### ==

**Literal expression**

```<expression1> == <expression2>```

Both <expression1> and <expression2> must have the same data type. The result is boolean.

**Example**

```3.14 == 42```

```&#34;foo&#34; == &#34;bar&#34;```

### !=

**Literal expression**

```<expression1> != <expression2>```

Both <expression1> and <expression2> must have the same data type. The result is boolean.

**Example**

```3.14 != 42```

```&#34;foo&#34; != &#34;bar&#34;```

### >

**Literal expression**

```<expression1> > <expression2>```

Datetime can be compared with Datetime and Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

The result is boolean.

**Example**

```3.14 > 42```

### >=

**Literal expression**

```<expression1> >= <expression2>```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal.
Any other combination is forbidden.

The result is boolean.

**Example**

```42 >= 3.14```

### <

**Literal expression**

```<expression1> < <expression2>```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal. Any other combination is forbidden.

The result is boolean.

**Example**

```42 < 3.14```

### <=

**Literal expression**

```<expression1> <= <expression2>```

Datetime can be compared with Datetime.

Datetimeonly can be compared with Datetimeonly.

Both integer or decimal can be compared with both integer or decimal. Any other combination is forbidden.

The result is boolean.

**Example**

```42 <= 3.14```

## Arithmetic {#arithmetic}

### +

**Literal expression**

```<expression1> + <expression2>```

Both expressions must be numeric (integer or decimal). 

The result is also numeric.

**Example**

```1 + 2``` returns 3

### -

**Literal expression**

```<expression1> - <expression2>```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

**Example**

```2 - 1``` returns 1

### /

**Literal expression**

```<expression1> / <expression2>```

Both expressions must be numeric (integer or decimal). 

The result is also numeric.

<expression2> must not be equal to 0 (returns 0).

**Example**

```4 / 2``` returns 2

### *

**Literal expression**

```<expression1> * <expression2>```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

**Example**

```3 * 4``` returns 12

### %

**Literal expression**

```<expression1> % <expression2>```

Both expressions must be numeric (integer or decimal).

The result is also numeric.

**Example**

```3 % 2``` returns 1.

## Math {#math}

### is numeric

**Literal expression**

```<expression> is numeric```

The type of the expression is integer or decimal.

**Example**

```@ is numeric```

### is integer

**Literal expression**

```<expression> is integer```

The type of the expression is integer.

**Example**

```@ is integer```

### is decimal

**Literal expression**

```<expression> is decimal```

The type of the expression is decimal.

**Example**

```@ is decimal```

## String {#string}

### + 

**Literal expression**

```<string> + <expression>```

```<expression> + <string>```

It concatenates two expressions. 

One expression must be a chained string.

**Example**

```&#34;the current time is &#34; + (now())``` returns "the current time is 2019-09-23T09:30:06.693Z"

```(now()) + &#34; is the current time&#34;``` returns "2019-09-23T09:30:06.693Z is the current time"

```&#34;a&#34; + &#34;b&#34; + &#34;c&#34; + 1234``` returns "abc1234".

## Date {#date}

### +

**Literal expression**

```<expression + <duration>```

Append a duration to a dateTime, a dateTimeOnly or a duration.

**Example**

```toDateTime(&#34;2011-12-03T15:15:30Z&#34;)```

``` + toDuration(&#34;PT15M&#34;)``` returns 2011-12-03T15:30:30Z

```toDateTimeOnly(&#34;2011-12-03T15:15:30&#34;)```

``` + toDuration(&#34;PT15M&#34;)``` returns 2011-12-03T15:30:30

```now() + toDuration(&#34;PT1H&#34;)``` returns a dateTime (with UTC time zone) one hour later from current time

```toDuration(&#34;PT1H&#34;) + toDuration(&#34;PT1H&#34;)``` returns  PT2H
