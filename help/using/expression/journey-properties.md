---
title: Operators
description: Learn about operators in advanced expressions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---


# Journey properties {#concept_wd5_pj5_dgb}

We want to expose to the customer technical attributes to be used in expressions, coming from the execution in the backend for a given profile. Those attributes are related to the journey version / instance, such as:

info about the journey version (journey uid, journey version uid, instance uid, ...)
info about the errors (data fetch, action execution, ...)
info about the current step, last current step, ...
info about discarded people
In the Expression Editor, in the context, beside the events, we will have a new bucket called "Journey instance details", containing all those attributes.

The user can use them as the event of fieldgroup fields in the expression.

At runtime, we will get those attribute values from the journey version definition and the instance state directly.

IMPORTANT: all those attributes will not contain any PII or sensitive data about the internal data processed on the backend. We will enforce that as we are fully controlling their evaluations.

Examples of use cases:

Park discard by capping people
An example of a use case is to set up a path in case of timeout and error, potentially filtering a certain error type "discard people by capping rule", to push people in a third party system to log rejected people.
Information.

Infos that would have to be used among instance details:

Profile id
Namespace
Last execution error code

Push alerts in case of errors:
In case of errors, we would be able to push error alerts to systems like slack to help customers detects issues.

This would be done using errors information to a custom action

This is a request from Nespresso.

Show in reporting error-related information
Having in the canvas error path with potentially a condition by error type would naturally display in the reporting sankey the error path and allow the brand to understand the type of errors happening

Call third party systems passing some journey information
For actions: For logging purpose, reporting purpose, AB test purpose, passing nodeid, journey id could allow brands to cover more use cases.

For data sources: Passing journey information could potentially be parameters to get data back. BOA has this requirement to integrate JO and OD.

