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
|-|-|-|----|
|Journey Version|journeyUID|Journey Identifier|?|
| |journeyVersionUID|Journey Version Identifier|?|
| |journeyVersionName|Journey Version Name|?|
| |journeyVersionDescription|Journey Version Description|?|
| |journeyVersion|Journey Version|?|
|Journey Instance|instanceUID|Journey Instance Identifier|ID of the instance|
| |externalKey|External Key|Individual identifier triggering the journey|
|Profile Identity|profileId|Profile Identity Identifier|Identifier of the profile in the journey|
| |namespace|Profile Identity Namespace|Namespace of the profile in the journey (example: ECID)
|Current Node|currentNodeId|Current Node Identifier|Identifier of the current activity (node)|
| |currentNodeName|Current Node Name|Name of the current activity (node)|
|Previous Node|previousNodeId|Previous Node Identifier|Identifer of the previous activity (node)|
| |previousNodeName|Previous Node Name|Name of the previous activity (node)|
|Errors|lastNodeUIDInError|Last Node Identifier in Error|Identifer of the latest activity (node) in error|
| |lastNodeNameInError|Last Node Name in Error|Name of the latest activity (node) in error|
| |lastNodeTypeInError|Last Node Type in Error|Error type of the latest activity (node) in error. Possible types:<ul><li>Events: Events, Reactions, SQ (example: Segment Qualification)</li><li>Flow control: End, Condition, Wait</li><li>Actions:ACS actions, Jump, Custom Action</li></ul>|
| |lastErrorCode|Last Error Code|Error code of the latest activity (node) in error. Possible errors: <ul><li>HTTP error codes</li><li>capped</li><li>timedOut</li><li>error (example: default in case of an unexpected error. Should not/extremely rarely happen)</li></ul>|
| |lastExecutedActionErrorCode|Last Executed Action Error Code|Error code of the latest action in error |
| |lastDataFetchErrorCode|Last Data Fetch Error Code|Error code of the latest data fetch from data sources|
|Time|lastActionExecutionElapsedTime|Last action execution elapsed time|Time spent to execute the latest action|
| |lastDataFetchElapsedTime|Last data fetch elapsed time|Time spent to execute the latest data fetch from data sources|
