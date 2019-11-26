---
title: Using the advanced expression editor
description: Learn how to build advanced expressions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# Using the advanced expression editor {#concept_uyj_trt_52b}

## About the advanced expression editor {#section_llg_vnj_cjb}

The advanced expression editor allows you to build advanced expressions in various screens of the interface, for example, when defining a data source condition.
It is also available every time you need to define action parameters that require specific data manipulations. You can leverage data coming from the events or additional information retrieved from the data source. In a journey, the displayed list of event fields is contextual and varies according to the event(s) added in the journey.

The advanced expression editor offers a set of built-in functions and operators to let you manipulate values and define an expression that fits specifically your needs. The advanced expression editor also allows you to define the values of the external data source parameter, manipulate map fields and collections, such as experience events.

 ![](../assets/journey65.png)

_The advanced expression editor interface_

The advanced expression editor can be used to:

* create [advanced conditions](../building-journeys/condition.md#about_condition) on data sources and event information
* define custom [time zones](../building-journeys/timezone.md) in date conditions, fixed date wait activities, custom wait activities
* define custom [wait activities](../building-journeys/wait.md#custom)
* define action parameters mapping

When possible, you can switch between the two modes using the **Advanced mode** / **Simple mode** button. The simple mode is described [here](../building-journeys/condition.md#about_condition).

>[!NOTE]
>
>Conditions can be defined in the simple or advanced expression editor. They always return a boolean type.  
>
>Actions parameters can be defined by selecting fields or via the advanced expression editor. They return a specific data type according to their expression.  

## Accessing the advanced expression editor {#section_fdz_4nj_cjb}

You can access the advanced expression editor in different ways:

* When you create a data source condition, you can access the advanced editor by clicking on **Advanced mode**.

    ![](../assets/journeyuc2_33.png)

* When you create a custom time zone or a custom timer, the advanced editor will be directly displayed.
* When you map action parameter, click on **Advanced mode**.

## Discovering the interface{#section_otq_tnj_cjb}

This screen allows you to manually write your expression.

![](../assets/journey70.png)

On the left part of the screen are displayed available fields and functions:

* **Events**: choose one of the fields received from the inbound event. The displayed list of event fields is contextual and varies according to the event(s) added in the journey.
* **Data Sources**: choose from the list of fields available from your data sources' field groups.
* **Functions**: choose from the a list of built-in functions that allow to carry out complex filtering. Functions are organized by categories.

![](../assets/journey65.png)

An autocompletion mechanism displays contextual suggestions.

![](../assets/journey68.png)

A syntax validation mechanism checks the integrity of your code. Errors are displayed on top of the editor.

![](../assets/journey69.png)

**Need for parameters when building conditions with the advanced expression editor**

If you select a field from an external data source requiring a parameter to be called (see [](../datasource/dsexternal.md). For example, in a weather-related data source, a frequently used parameter will be "city". As a result, you must select where you want to get this city parameter. Functions can also be applied to parameters to perform format changes or concatenations.

![](../assets/journeyuc2_19.png)

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the "params" keyword. See [this page](../expression/expressionfields.md).
