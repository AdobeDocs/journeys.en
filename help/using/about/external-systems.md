---
product: adobe campaign
solution: Journey Orchestration
title: Integrating with external systemps
description: Learn the best practices when integrating external systems
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
---
# Integrating with external systems {#external-systems}

This page presents the different guardrails provided by Journey Orchestration when integrating an external system, as well as best practices: how to optimize the protection of your external system using the capping API, how to configure journey timeout, and how retries work. 

Journey Orchestration allows you to configure connections to external systems via custom data sources and custom actions. This allows you, for example, to enrich your journeys with data coming from an external reservation system, or send messages using a third-party system such as Epsilon or Facebook.

When integrating an external system, you can encounter several issues, the system can be slow, can stop responding, or it might not be able to handle a large volume. Journey Orchestration offers several guardrails to protect your system from over-loading.

All external systems are different in terms of performance. You need to adapt the configuration to your use cases.

When Journey Orchestration executes a call to an external API, the technical guardrails are executed as follows:

1. Capping rules are applied: if the maximum rate is reached, remaining calls are discarded.

2. Timeout and retry: if the capping rule is fulfilled, Journey Orchestration tries to perform the call until the end of the timeout duration is reached. 

## Capping{#capping}

The built-in Capping API offers an upstream technical guardrail that helps to protect your external system. Beforehand, you need to evaluate the capacity of your external API. For example, if Journey Orchestration sends 1000 calls per second and your system can only support 100 calls per second, you need to define a capping rule so that your system does not saturate.

Capping rules are defined at sandbox level for a specific endpoint (the URL called). At runtime, Journey Orchestration verifies if there is a capping rule defined and applies the defined rate during the calls to that endpoint. If the number of calls exceeds the defined rate, the remaining calls are discarded and are counted as errors in reporting.

A capping rule is specific to one endpoint but global to all the journeys of a sandbox. This means that capping slots are shared between all journeys of a sandbox.

For example, let's say that you have defined a capping rule of 100 calls per second for your external system. Your system is called by a custom action in 10 different journeys. If one journey receives 200 calls per second, it will use the 100 slots available and discard the 100 remaining slots. Since the maximum rate has exceeded, the other 9 journeys will not have any slot left. This granularity helps to protect the external system from over-loading and crashing. 

To learn more on the capping API and how to configure capping rules, refer to [this page](../api/capping.md). 

## Timeout and retries{#timeout}

If the capping rule is fulfilled, then the timeout rule is applied.

In each journey, you can define a timeout duration. This allows you to set a maximum duration when calling an external system. Timeout duration is configured in the properties of a journey. Refer to [this page](../building-journeys/changing-properties.md#timeout_and_error).

This timeout is global to all external calls (external API calls in custom actions and custom data sources). By default, it is set to 5 seconds. 

During the defined timeout duration, Journey Orchestration tries to call the external system. After the first call, a maximum of three retries can be performed until the end of timeout duration is reached. The number of retries cannot be changed. 

Each retry uses one slot. If you have a capping of 100 calls per second and each of your calls require two retries, the rate drops to 30 calls per second (each call uses 3 slots: the first call and two retries). 

The timeout duration value depends on the use case. If you want to send your message quickly, for example when the client enters the store, then you do not want to set up a long timeout. Also, the longer the timeout is, the more items will be placed in queue. This can greatly impact performance. If Journey Orchestration performs 1000 calls per seconds, keeping 5 or 15 seconds of data can quickly overwhelm the system.

Let's take an example for a timeout of 5 seconds.

* The first call lasts less than 5 seconds: the call is successful, no retry is performed.
* The first call lasts longer 5 seconds: the call is cancelled and there is no retry. It is counted as a timeout error in reporting. 
* The first call fails after 2 seconds (the external system returns an error): 3 seconds are left for retries, if capping slots are available.
    * If one of the three retries is successful before the end of the 5 seconds, the call is performed, and there is no error.
    * If the end of the timeout duration is reached during the retries, the call is cancelled andcounted as a timeout error in reporting. 

## Frequently asked questions{#faq}

**How can I setup a capping rule? Is there a default capping rule?**

By default, there is no capping rule. Capping rules are defined at sandbox level for a specific endpoint (the URL called), using the Capping API. Refer to [this section](../about/external-systems.md#capping) and [this page](../api/capping.md). 

**How many retries are performed? Can I change the number of retries or define a minumim wait period between retries c?**

For a given call, a maximum of three retries can be performed after the first call, until the end of timeout duration is reached. The number of retries and the time between each retry cannot be changed. Refer to [this section](../about/external-systems.md#timeout). 

**Where can I setup the timeout? Is there a maximum value?**

In each journey, you can define a timeout duration. Timeout duration is configured in the properties of a journey. Timeout duration must be between 1 second and 30 seconds. Refer to [this section](../about/external-systems.md#timeout) and [this page](../building-journeys/changing-properties.md#timeout_and_error). 