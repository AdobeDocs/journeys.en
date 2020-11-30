---
product: adobe campaign
solution: Journey Orchestration
title: Journey properties
description: Learn about journey properties
---

# Journey properties {#journey-properties}

In the advanced expression editor, you will find the **Journey Properties** category, below the event and data source categories. This category contains technical fields related to the journey for a given profile. This is the information retrieved by the system from live journeys, such as the journey ID or the specific errors encountered. 

![](../assets/journey-properties.png)

You will find information, for example, about:

* journey version: journey uid, journey version uid, instance uid, etc.
* errors: data fetch, action execution, etc.
* current step, last current step, etc.
* discarded profiles

You can use these fields to build expressions. During the journey exection, the values will be retrieved directly from the journey. 

## Examples {#journey-properties-examples}

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

## List of fields {#journey-properties-fields}

|Category|Field name|Label|Description|
||-|-|----|
|Journey Version|journeyUID|Journey Identifier|?|
| |journeyVersionUID|Journey Version Identifier|?|
| |journeyVersionName|Journey Version Name|?|
| |journeyVersionDescription|Journey Version Description|?|
| |journeyVersion|Journey Version|?|
|Journey Instance|instanceUID|Journey Instance Identifier|ID of the instance|
| |externalKey|External Key|Individual identifier triggering the journey|
|Profile Identity|profileId|Profile Identity Identifier|Identifier of the profile in the journey|
| |namespace|Profile Identity Namespace|Namespace of the profile in the journey (example: ECID)

