---
title: journeysteps events common fields
description: journeysteps events common fields
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# journeysteps events common fields {#sharing-common-fields}

This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

These are the common XDM fields that [!DNL Journey Orchestration] sends to Adobe Experience Platform. Common fields will be sent for every step that is processed in a journey. More specific fields are used for custom actions and enrichments.

Some of those fields are only available in specific processing patterns (action execution, data fetch, etc.) in order to limit the size of events.

## entrance

Indicates if the user has entered the journey. If not present, we assume that the value is false.

Type: boolean

Values: true/false

## reentrance

Indicates if the user has reentered the journey with the same instance. If not present, we assume that the value is false.

Type: boolean

Values: true/false

## instanceEnded

Indicates if the instance has ended (successfully or not).

Type: boolean

## eventID

Event id in processing, for the step processing. If the event is an external one, the value is its eventId. If the event is an internal one, the value is the internal eventId (such as scheduledNotificationReceived, executedAction, etc.).

Type: string

## nodeID

Client node id (from the canvas). 

Type: string

## stepID

Unique id of the step that is currently being processed.

Type: string

## stepName

Name of the step that is currently being processed.

Type: string

## stepType

Type of the step.

Type: string

Possible values:

* Condition
* Action
* Scheduler
* Timer

## stepStatus

Status of the step, representing the status of the step, when its processing has been done (and the step event fired).

Type: string

The status can be:

* ended: the step has no transition and its processing has ended successfully.
* error: the step processing has raised an error.
* transitions: the step is waiting for an event to transition to another step.
* capped: the step has failed on a capping error, raised during an action or enrichment.
* timedout: the step has failed on a timeout error, raised during an action or enrichment.
* instanceTimedout: the step has stopped its processing, because the instance has reached its timeout.

## journeyID

ID of the journey.

Type: string

## journeyVersionID

ID of the journey version. This id represents the identity reference to the journey, in the case of the journeyStepEvent.

Type: string

## journeyVersionName

Name of the journey version.

Type: string

## journeyVersion

Version of the journey version.

Type: string

## instanceID

Internal ID of the journey instance.

Type: string

## externalKey

External key extracted from the event to process it.

Type: string

## parentStepID

Step ID of the parent of the current processed step in the instance.

Type: string

## parentStepName

Step name of the parent of the current step.

Type: string

## parentTransitionID

Id of the transition which has brought the instance to the processed step.

Type: string

## parentTransitionName

Name of the transition which has brought the instance to the processed step.

Type: string

## inTest

Indicated if this journey is in test mode or not.

Type: boolean

## processingTime

Total amount of time in milliseconds from the instance step entrance to the end of the processing.

Type: long

## instanceType

Indicates the instance type, if it is batch or unitary.

Type: string

Values: batch/unitary

## recurrenceIndex

Index of the recurrence if the journey is batch and recurring (first run has recurrenceIndex = 1).

Type: long

## isBatchToUnitary

Indicates if this unitary instance has been triggered from a batch instance.

Type: boolean

## batchExternalKey

External Key for batch event.

Type: string

## batchInstanceID

this is the batch instance ID.

Type: string

## batchUnitaryBranchID

if the instance has been triggered from a batch instance, unitary branch ID.

Type: string
