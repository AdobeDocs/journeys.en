---
product: adobe campaign
title: Journey Orchestration limitations
description: Learn more on Journey Orchestration limitations
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
---
# Limitations {#limitations}

Here are limitations related to the use of Journey Orchestration.

## General actions limitations

* There is no sending throttling. 
* Three retries are systematically performed in case of an error. You cannot adjust the number of retries according to the error message received. 
* The built-in **Reaction** event allows you to react to out-of-the-box actions (see this [page](../building-journeys/reaction-events.md)). If you want to react to a message sent via a custom action, you need to configure a dedicated event. 

## Journey versions limitations {#journey-versions-limitations}

* A journey starting with an event activity in v1 cannot start with something else than an event in further versions. You cannot start a journey with a **Segment Qualification** event. 
* A journey starting with a **Segment Qualification** activity in v1 must always start with a **Segment Qualification** in further versions. 
* The segment and namespace chosen in **Segment qualification** (first node) can not be changed in new versions.
* The re-entrance rule must be the same in all journey versions.

## Segment qualification {#segment-qualification}

* The **Segment qualification** activity cannot be used in conjunction with Adobe Campaign Standard Transactional Messaging due to throughput constraints. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## Custom actions limitations

* The custom action URL does not support dynamic parameters. 
* Only POST and PUT call methods are supported. 
* The name of the query parameter or header must not start with "." or "$". 
* IP addresses are not allowed. 
* Internal Adobe addresses (.adobe.) are not allowed.
 
## Adobe Campaign actions limitations

* Adobe Campaign Standard Transactional Messaging has a scale of 50 000 messages per hour maximum across channels for a given instance. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## Events limitations

* For system-generated events, streaming data used to initiate a customer journey must be configured within Journey Orchestration first to get a unique orchestration ID. This orchestration ID must be appended to the streaming payload coming into Adobe Experience Platform. This limitation does not apply to rule-based events.
 
## Data sources limitations

* External data sources can be leveraged within a customer journey to lookup external data in real-time. These sources must be usable via REST API, support JSON and be able to handle the volume of requests.

## Journeys starting at the same time as a profile creation {#journeys-limitation-profile-creation}
 
There is a delay associated to API based profile creation/update in Adobe Experience Platform. The Service Level Target (SLT) in terms of latency is < 1 min from ingestion to Unified Profile for 95th percentile of requests, at a volume of 20K Requests per second (RPS).

If a Journey is triggered simultaneously to a profile creation and immediately checks/retrieves information from Profile Service, it might not work properly.

You can choose from one of these two solutions:

* Add a wait activity after the first event, to give Adobe Experience Platform the time it needs to perform the ingestion to Profile Service.

* Set up a journey that does not immediately leverage the profile. For example, if the journey is designed to confirm an account creation, the experience event could contain information needed to send the first confirmation message (first name, last name, email address, etc).
