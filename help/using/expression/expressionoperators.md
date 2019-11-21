---
title: Operators
description: Learn about operators in journeys' advanced conditions
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

<!--<table>
<thead>
<tr ><th  >Category</th><th  >Operator</th><th  >Literal Expression</th><th  >Example</th></tr>
</thead>
<tbody>
<tr ><td>Logical</td><td>and</td><td><p>&lt;expression1&gt; and &lt;expression2&gt;</p><p>Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean.</p><p> The result is boolean.</p></td><td>3.14 &gt; 2 and 3.15 &lt; 1</td></tr>
<tr ><td>Logical</td><td>or</td><td><p>&lt;expression1&gt; or &lt;expression2&gt;</p><p>Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean.</p><p> The result is boolean.</p></td><td>3.14 &gt; 2 or 3.15 &lt; 1</td></tr>
<tr ><td>Logical</td><td>not</td><td><p>not &lt;expression&gt;``&lt;expression&gt; must be boolean.</p><p> The result is boolean.</p></td><td>not 3.15 &lt; 1</td></tr>
<tr ><td>Comparison</td><td>is null</td><td><p>&lt;expression&gt; is null</p><p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p></td><td>@{BarBeacon.location} is null</td></tr>
<tr ><td>Comparison</td><td>is not null</td><td><p>&lt;expression&gt; is not null</p><p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p></td><td>@ is not null</td></tr>
<tr ><td>Comparison</td><td>has null</td><td><p>&lt;expression&gt; has null``&lt;expression&gt; must be a list.</p><p>The result is boolean.</p><p>Useful to identify that a list contains at least one null value.</p></td><td><p><pre>[&#34;foo&#34;, &#34;bar&#34;, null]</pre></p> has null</pre></p> returns true<p><pre>[&#34;foo&#34;, &#34;bar&#34;, &#34;&#34;] has null</pre></p> returns false because &#34;&#34; is not considered as null.</td></tr>
<tr ><td>Comparison</td><td>==</td><td><p>&lt;expression1&gt; == &lt;expression2&gt;</p><p>Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type.</p><p> The result is boolean.</p></td><td>3.14 == 42<br />&#34;foo&#34; == &#34;bar&#34;</td></tr>
<tr ><td>Comparison</td><td>!=</td><td><p>&lt;expression1&gt; != &lt;expression2&gt;</p><p> Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type.</p><p> The result is boolean.</p></td><td>3.14 != 42<br />&#34;foo&#34; != &#34;bar&#34;</td></tr>
<tr ><td>Comparison</td><td>&gt;</td><td><p>&lt;expression1&gt; &gt; &lt;expression2&gt;</p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td>3.14 &gt; 42</td></tr>
<tr ><td>Comparison</td><td>&gt;=</td><td><p>&lt;expression1&gt; &gt;= &lt;expression2&gt;</p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td>42 &gt;= 3.14</td></tr>
<tr ><td>Comparison</td><td>&lt;</td><td><p>&lt;expression1&gt; &lt; &lt;expression2&gt;</p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td>42 &lt; 3.14</td></tr>
<tr ><td>Comparison</td><td>&lt;=</td><td><p>&lt;expression1&gt; &lt;= &lt;expression2&gt;</p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td>42 &lt;= 3.14</td></tr>
<tr ><td>Arithmetic</td><td>+</td><td><p>&lt;expression1&gt; + &lt;expression2&gt;</p><p>Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p></td><td><p><pre>1 + 2</pre></p><br />Returns 3</td></tr>
<tr ><td>Arithmetic</td><td>-</td><td><p>&lt;expression1&gt; - &lt;expression2&gt;</p><p> Both expressions must be numeric (integer or decimal).</p><p> The result is also numeric.</p></td><td><p><pre>2 - 1</pre></p>Returns 1</td></tr>
<tr ><td>Arithmetic</td><td>/</td><td><p>&lt;expression1&gt; / &lt;expression2&gt;</p><p>Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p><p>&lt;expression2&gt; must not be equal to 0 (returns 0).</p></td><td><p><pre>4 / 2</pre></p>Returns 2</td></tr>
<tr ><td>Arithmetic</td><td>*</td><td><p>&lt;expression1&gt; * &lt;expression2&gt;</p><p> Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p></td><td><p><pre>3 * 4</pre></p>Returns 12</td></tr>
<tr ><td>Arithmetic</td><td>%</td><td><p>&lt;expression1&gt; % &lt;expression2&gt;</p><p>Both expressions must be numeric (integer or decimal).</p><p> The result is also numeric</p>.</td><td><p><pre>3 % 2</pre></p>Returns 1</td></tr>
<tr ><td>Math</td><td>is numeric</td><td><p>&lt;expression&gt; is numeric</p><p>The type of the expression is integer or decimal.</p></td><td>@ is numeric.</td></tr>
<tr ><td>Math</td><td>is integer</td><td><p>&lt;expression&gt; is integer</p><p>The type of the expression is integer.</p></td><td>@ is integer</td></tr>
<tr ><td>Math</td><td>is decimal</td><td><p>&lt;expression&gt; is decimal</p><p>The type of the expression is decimal.</p></td><td>@ is decimal</td></tr>
<tr ><td>String</td><td>+</td><td><p>&lt;string&gt; + &lt;expression&gt;</p><p>&lt;expression&gt; + &lt;string&gt;</p><p>It concatenates two expressions or more. </p><p>The first expression must be a string.</p><p> The other expressions can be of any type.</p><p> The result is a string.</p></td><td><p><pre>&#34;the current time is &#34; + (now())</pre></p> Returns  &#34;the current time is 2019-09-23T09:30:06.693Z&#34;<p><pre>(now()) + &#34; is the current time&#34;</pre></p>Returns 2019-09-23T09:30:06.693Z is the current time<p><pre>`&#34;a&#34; + &#34;b&#34; + &#34;c&#34; + 1234</pre></p> Returns abc1234</td></tr>
<tr ><td>Date</td><td>+</td><td><p>&lt;expression + &lt;duration&gt;</p><p>Append a duration to a dateTime, a dateTimeOnly or a duration.</p></td><td><p><pre>toDateTime(&#34;2011-12-03T15:15:30Z&#34;) + toDuration(&#34;PT15M&#34;)</pre></p>Returns 2011-12-03T15:30:30Z<p><pre>toDateTimeOnly(&#34;2011-12-03T15:15:30&#34;) + toDuration(&#34;PT15M&#34;)</pre></p>Returns 2011-12-03T15:30:30<p><pre>now() + toDuration(&#34;PT1H&#34;)</pre></p>Returns a dateTime (with UTC timezone) one hour later from current time<p><pre>toDuration(&#34;PT1H&#34;) + toDuration(&#34;PT1H&#34;)</pre></p>Returns  PT2H</td></tr>
</tbody>
  </table>-->

## Logical 

  <table>
<thead>
<tr ><th  >Operator</th><th  >Literal Expression        </th><th  >Example</th></tr>
</thead>
<tbody>
<tr >><td>and</td><td><p><pre>&lt;expression1&gt; and &lt;expression2&gt;</pre></p>Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean. The result is boolean.</td><td>3.14 &gt; 2 and 3.15 &lt; 1</td></tr>
<tr ><td>or</td><td><p><pre>&lt;expression1&gt; or &lt;expression2&gt;</pre></p><p>Both &lt;expression1&gt; and &lt;expression2&gt; must be boolean.</p><p> The result is boolean.</p></td><pre>3.14 &gt; 2 or 3.15 &lt; 1</pre></td></tr>
<tr ><td>not</td><td><p>not &lt;expression&gt;``&lt;expression&gt; must be boolean.</p><p> The result is boolean.</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Comparison

<table>
<thead>
<tr ><th  >Operator</th><th  >Literal Expression </th><th  >Example</th></tr>
</thead>
<tbody><tr ><td>is null</td><td><p><pre>&lt;expression&gt; is null</pre></p><p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p></td><td><pre>@{BarBeacon.location} is null</pre></td></tr>
<tr ><td>is not null</td><td><p><pre>&lt;expression&gt; is not null</pre></p><p>The result is boolean.</p><p>Note that null means the expression has no evaluated value.</p></td><td><pre>@ is not null</pre></td></tr>
<tr ><td>has null</td><td><p><pre>&lt;expression&gt; has null</pre>&lt;expression&gt; must be a list.</p><p>The result is boolean.</p><p>Useful to identify that a list contains at least one null value.</p></td><td><p><pre>[&#34;foo&#34;, &#34;bar&#34;, null]</pre></p> has null</pre></p> returns true<p><pre>[&#34;foo&#34;, &#34;bar&#34;, &#34;&#34;] has null</pre></p> returns false because &#34;&#34; is not considered as null.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type.</p><p> The result is boolean.</p></td><td><pre>3.14 == 42<br />&#34;foo&#34; == &#34;bar&#34;</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> Both &lt;expression1&gt; and &lt;expression2&gt; must have the same data type.</p><p> The result is boolean.</p></td><td><pre>3.14 != 42<br />&#34;foo&#34; != &#34;bar&#34;</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>Datetime can be compared with Datetime.</p><p>Datetimeonly can be compared with Datetimeonly.</p><p>Both integer or decimal can be compared with both integer or decimal.</p><p>Any other combination is forbidden.</p><p>The result is boolean.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Arithmetic

<table>
<thead>
<tr ><th  >Operator</th><th>Literal Expression </th><th  >Example</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Returns 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Both expressions must be numeric (integer or decimal).</p><p> The result is also numeric.</p></td><td><p><pre>2 - 1</pre></p>Returns 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p><p>&lt;expression2&gt; must not be equal to 0 (returns 0).</p></td><td><p><pre>4 / 2</pre></p>Returns 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Both expressions must be numeric (integer or decimal). </p><p>The result is also numeric.</p></td><td><p><pre>3 * 4</pre></p>Returns 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Both expressions must be numeric (integer or decimal).</p><p> The result is also numeric</p>.</td><td><p><pre>3 % 2</pre></p>Returns 1</td></tr>
</tbody>
</table>

## Math

<table>
<thead>
<tr ><th  >Operator</th><th  >Literal Expression </th><th  >Example</th></tr>
</thead>
<tbody><tr ><td>is numeric</td><td><p><pre>&lt;expression&gt; is numeric</pre></p><p>The type of the expression is integer or decimal.</p></td><td><pre>@ is numeric.</pre></td></tr>
<tr ><td>is integer</td><td><p><pre>&lt;expression&gt; is integer</pre></p><p>The type of the expression is integer.</p></td><td><pre>@ is integer</pre></td></tr>
<tr ><td>is decimal</td><td><p>&lt;expression&gt; is decimal</p><p>The type of the expression is decimal.</p></td><td><pre>@ is decimal</pre></td></tr>

## String

<table>
<thead>
<tr ><th  >Operator</th><th  >Literal Expression </th><th  >Example</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p>&lt;expression&gt; + &lt;string&gt;</p><p>It concatenates two expressions or more. </p><p>The first expression must be a string.</p><p> The other expressions can be of any type.</p><p> The rest is a string.</p></td><td><p><pre>&#34;the current time is &#34; + (now())</pre></p> Returns  &#34;the current time is 2019-09-23T09:30:06.693Z&#34;<p><pre>(now()) + &#34; is the current time&#34;</pre></p>Returns 2019-09-23T09:30:06.693Z is the current time<p><pre>`&#34;a&#34; + &#34;b&#34; + &#34;c&#34; + 1234</pre></p> Returns abc1234</td></tr>
</tbody>
</table>

## Date

<table>
<thead>
<tr ><th  >Operator</th><th  >Literal Expression </th><th  >Example</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>Append a duration to a dateTime, a dateTimeOnly or a duration.</p></td><td><p><pre>toDateTime(&#34;2011-12-03T15:15:30Z&#34;) + toDuration(&#34;PT15M&#34;)</pre></p>Returns 2011-12-03T15:30:30Z<p><pre>toDateTimeOnly(&#34;2011-12-03T15:15:30&#34;) + toDuration(&#34;PT15M&#34;)</pre></p>Returns 2011-12-03T15:30:30<p><pre>now() + toDuration(&#34;PT1H&#34;)</pre></p>Returns a dateTime (with UTC timezone) one hour later from current time<p><pre>toDuration(&#34;PT1H&#34;) + toDuration(&#34;PT1H&#34;)</pre></p>Returns  PT2H</td></tr>
</tbody>
</table>