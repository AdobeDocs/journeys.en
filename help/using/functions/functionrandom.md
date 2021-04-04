---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Learn about the function random
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
---
# random {#random}

Generates a random number between 0 and 1.

## Category

Maths

## Function syntax

`random(<parameters>)`

## Signature and returned type

`random()`

Returns a decimal.

## Example

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explanation: if the success ratio has no value/is null, the default value will be applied and will be a random figure between 0 and 1 * 100 (meaning 0 to 100).
