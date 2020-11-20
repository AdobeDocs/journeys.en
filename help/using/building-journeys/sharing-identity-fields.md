---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep event identity fields
description: journeyStep event identity fields
---

# journeyStep event identity fields {#sharing-identity-fields}

This mixin is specific to journeyStepEvent: this event is in relation with journey, and doesn't have the identityMap, describing the profile identity, if any.

For journeyStepEvent, we need also to add fields related to the identity:

## profileID

Profile identifier

Type: string

## profileNamespace

Profile identifier namespace

Type: string