---
product: adobe campaign
title: journeyStep event identity fields
description: journeyStep event identity fields
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
---
# journeyStep event identity fields {#sharing-identity-fields}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


This mixin is specific to journeyStepEvent: this event is in relation with journey, and doesn't have the identityMap, describing the profile identity, if any.

For journeyStepEvent, we need also to add fields related to the identity:

## profileID

Profile identifier

Type: string

## profileNamespace

Profile identifier namespace

Type: string
