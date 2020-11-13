---
title: Journey Orchestration limitations
description: Learn more on Journey Orchestration limitations
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Limitations {#limitations}

Here are limitations related to the use of Journey Orchestration.

## General actions limitations

* There is no sending throttling. 
* Two retries are systematically performed in case of an error. You cannot adjust the number of retries according to the error message received. 
* The built-in **Reaction** event allows you to react to out-of-the-box actions (see this [page](../building-journeys/reaction-events.md)). If you want to react to a message sent via a custom action, you need to configure a dedicated event. 
* There is no Adobe Campaign Classic productized integration.
 
## Custom actions limitations

* The custom action URL does not support dynamic parameters. 
* Only POST and PUT call methods are supported. 
* The name of the query parameter or header must not start with "." or "$". 
* IP addresses are not allowed. 
* Internal Adobe addresses (.adobe.) are not allowed.
 
## Adobe Campaign actions limitations

* Adobe Campaign Standard Transactional Messaging has a scale of 50 000 messages per hour maximum across channels for a given instance. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
* The **Segment qualification** activity should not be used in conjunction with Adobe Campaign Standard Transactional Messaging due to throughput constraints.
 
## Events limitations

* Streaming data used to initiate a customer journey must be configured within Journey Orchestration first to get a unique orchestration ID. This orchestration ID must be appended to the streaming payload coming into Adobe Experience Platform.
 
## Data sources limitations:

* External data sources can be leveraged within a customer journey to lookup external data in real-time. These sources must be usable via REST API, support JSON and be able to handle the volume of requests.