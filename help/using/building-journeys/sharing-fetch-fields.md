---
product: adobe campaign
title: journeyStep events data fetch fields
description: journeyStep events data fetch fields
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
---
# journeyStep events data fetch fields {#sharing-fetch-fields}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


This mixin will be shared by the journeyStepEvent and journeyStepProfileEvent.

During a step processing, we can have N data fetch on field groups.

## fetchTotalTime 

Total amount of time spent in data fetch in millis during the step processing.

Type: long

## fetchTypeInError

Defines if the fetch in error is on the Adobe Experience Platform or on a custom data source.

Type: string

Values: 
* aep
* custom
  
## fetchError

Type of error that happens when the data fetch is processed.

Type: string

Values: 
* http
* capping
* timedout
* error
  
## fetchErrorCode  
  
Code for fetch error. Present if the error has a code, such as an HTTP one. For instance, if the actionExecError is http, the code 404 represents the HTTP 404 error.

Type: string

## fetchOriginError
  
A timeout can occur, in two cases:

* at the first attempt the action is executed. In this case, the execution is not finished, so there is no underlying error
* on a retry: in this case, the actionExecOrigError/actionExecOrigErrorCode describes the error encountered on the attempt before the retry.

For instance, data is being fetched from Unified Profile Service and an HTTP 500 error is returned at the first attempt. The fetch is retried, but the duration of the 2 attempts exceeds the timeout. Then the action execution is tagged as timedout. The action part will look like:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type: string

## fetchOriginErrorCode

The Error code provided by the system [!DNL Journey Orchestration] is querying. For example it can be a 404, 500, etc.

Type: string
  
## fetchCount

How many times the data is fetched, regardless of the type of source.

Type: long

## fetchPlatformTotalTime

The total amount of time taken to fetch the data from Adobe Experience Platform in millis. Remark: this amount of time is computed from the time the engine sends the enrichment event to the enrichment service and receives the response.

Type: long

## fetchPlatformCount

How many times the data is fetched from Adobe Experience Platform.

Type: long

## fetchCustomTotalTime

Amount of time to fetch the custom data in millis. Remark: this amount of time is computed from the time the engine sends the enrichment event to the enrichment service and receives the response

Type: long

## fetchCustomCount

How many times the custom data is fetched from external systems.

Type: long
