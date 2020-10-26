---
title: Custom action limitations
description: Learn about custom action limitations
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Custom action limitations {#concept_lh2_df1_2gb}

Here are a few limitations regarding the use of custom actions:

* There is no sending volume buffering/smoothing.
* Two retries are systematically performed in case of an error. You cannot adjust the number of retries according to the error message received. 
* The built-in **[!UICONTROL Reaction]** event allows you to react to out-of-the-box actions (see [](../building-journeys/reaction-events.md)). If you want to react to a message sent via a custom action, you need to configure a dedicated event.
* The custom action URL does not support dynamic parameters.
* Only POST and PUT call methods are supported.
* The name of the query parameter or header must not start with "." or "$".
* IP addresses are not allowed.
* Internal Adobe addresses (.adobe.) are not allowed.
