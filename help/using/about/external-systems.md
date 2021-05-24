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

This page presents the different guardrails provided by Journey Orchestration when integrating an external system, as well as best practices: how to optimize the protection of your external system with the capping API, how to configure journey timeout, and how retries work. 

Journey Orchestration allows you to configure connections to external sytems via custom data sources and custom actions. This allows you, for example, to enrich your journeys with data coming from an external reservation system, or send messages using a third-party systems such as Epsilon or Facebook.

When integrating an external system, you can encounter several issues, the system can be slow, can stop responding, or it might not be able to handle a large volume. Journey Orchestration offers several guardrails to protect your system from over-loading.

All external systems are different in terms of performance. You need to adapt the configuration to each use case.

When Journey Orchestration executes a call to an external API, the technical guardrails are executed as follows:

1. Capping: capping rules are applied
2. Timeout and retry: 

## Capping

The built-in Capping API offers an upstream technical guardrail that will help protect your external system. Beforehand, you need to evaluate the capacity of your external API. For example, if Journey Orchestration sends 1000 calls per second and your system can only support 100 calls per second, you need to define a capping rule so that your system does not saturate.

Capping rules are defined at sanddox level for a specific endpoint (URL called). At runtime, Journey Orchestration verifies if there is a capping rule defined and applies the defined rate during the calls to that endpoint. If the number of calls exceeds the defined rate, the remaining calls are discarded. 

A capping rule is specific to one endpoint but global to all journeys of a sandbox. This means that call slots are shared between all journeys of a sandbox. For example, let's say that your external system has a defined capping of 100 calls per second and it is called by a custom action in 10 different journeys. If one journey receives 200 calls per second, it will keep the 100 slots available and discard the 100 remaining slots. Since the maximum rate is already exceeded, the other 9 journeys will not have any slot available. This granularity helps to protect the external system from over-loading and crashing. 

A call discarded due to capping limits is counted as an error in reporting.  

To learn how to configure capping rules, refer to [this page](../api/timezone-management.md). 

## Timeout and retries

Ensuite -> timeout defini, et qui definir le temps maximal qu'on aloue a lappel au sys externe. Pendant ce temps là, on essaie de faire des appels. On fait un appel, si l'appel dure moinre longtemps que le timeout ca marche, si plus longtemps on voit ca comme une timeout error, et coté reporting compabilisé comme une erreur. si l'appel echoue, (planter sur 500 ou autre), retry. 3 retry max, pas configurable. SI ca excede le timeoutglobal (par exemple 2 essais,  mais depasse le timeout) erreur de timeout. plsu de temps que necessaire. Timeout durée max qu'on alloue a appel et aux retries si erreurs.

