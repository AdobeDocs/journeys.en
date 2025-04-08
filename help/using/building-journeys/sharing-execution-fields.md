---
product: adobe campaign
title: journeyStep events action execution fields
description: journeyStep events action execution fields
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
---
# journeyStep events action execution fields {#sharing-execution-fields}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

If the step has an action to be processed, those fields will be added to the event payload. 

## actionID

ID of the action that is being executed.

Type: string

## actionName

Name of the action. If no name has been set, the stepName will be taken.

Type: string

## actionType

Type of the action.

Type: string

## actionParameterized

Indicates if the action is parameterized or not.

Type: boolean

## actionExecutionTime

The amount of time (in milliseconds) taken to execute a current action.

Type: long

## actionExecutionError

Type of error that happens when the action is called.

Type: string

Values:
* http
* capping
* timeout
* error

## actionExecutionErrorCode

Code for action execution error. Present if the error has a code, such as an HTTP one. 

Type: string

## actionExecutionOriginError

A timeout can occur, in two cases:

* at the first attempt an action is executed. In this case, the execution is not finished, so there is no underlying error
* on a retry: in this case, the actionExecOrigError/actionExecOrigErrorCode describes the error encountered on the attempt before the retry.

For instance, an email is being sent and an HTTP 500 error is returned at the first attempt. The fetch is retried, but the duration of the 2 attempts exceeds the timeout. Then the action execution is tagged as timedout. The action part will look like:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Type: string

## actionExecutionOriginCode

Error code of the actionExecOrigError.

Type: string

## actionBusinessType

Indicates the type of action. 

Values:

* builtin
 * ACS Email
 * ACS SMS
 * ACS Push
* customer
 * Epsilon
 * ...

Type: string

## deliveryJobID

This describes the delivery Job Id for the batch Journey.

Type: string

## batchDeliveryID

This describes the delivery Id for the batch Journey.

Type: string

## fromSegmentTrigger

This describes if the Batch Journey is triggered from Audience Segment.

Type: boolean

## actionSchedulerCount

Count of scheduler notification requests sent to the scheduler service during the step processing.

Type: long
