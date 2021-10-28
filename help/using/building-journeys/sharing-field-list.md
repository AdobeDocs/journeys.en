---
title: Step event field list
description: Step event field list
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
---
# Step event field list {#sharing-field-list}

Step event fields are organized by category.

* Debug information fields
* Journey fields
* Profile fields
* Service event fields

## debugInfo

|Field name|Type|Description|
|---|---|------------|
|requestId|String|The request Id used by Journey Orchestration to track the flow of a request.|

## journey

This field group is used in the journey schema (in relation with journeyStepEvent). It contains the following fields:

|Field name|Type|Description|
|---|---|------------|
|ID|String|Identifier for the given Journey|
|VersionID|String|Id of the journey version. This id represents the identity of a journey|
|name|String|Name of the journey|
|description|String|Description of the journey|
|version|String|version, represented as `major`.`minor`|

## profile

This field group is specific to journeyStepEvent: this event is in relation with journey, and doesn’t have the identityMap, describing the profile identity, if any.

For journeyStepEvent, we need also to add fields related to the identity:

|Field name|Type|Description|
|---|---|------------|
|ID|String|Profile identifier identifies the profile sent/used in a journey. E.g: foo@adobe.com.|
|namespace|String|This field describes the Namespace referenced by the Profile used in the Journey. E.g: Email, ECID|

## serviceEvents

This mixin contains all fields corresponding to a profile export job. 

|Field name|Type|Description|
|---|---|------------|
|ID|String|The identifier of the segment export job triggered|
|status|String|The status of segment export job: queued, started, finished|
|exportCountTotal|Integer|The max possible value of segment export job|
|exportCountRealized|Integer|The actual number of segments exported through the job|
|exportCountFailed|Integer|The number of segments failed while exporting through the job|
|exportSegmentID|String|The identifier of the segment being exported|
|eventType|String|The event type indicating whether it is an error event of info event: Info, Error|
|eventCode|String|The error code indicating the reason for corresponding eventType|

## stepEvents

This category contains the original step event fields. Refer to this [section](../reports/sharing-legacy-fields.md).
