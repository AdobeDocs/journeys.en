---
title: Selecting the namespace
description: Learn how to select the namespace
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Selecting the namespace {#concept_ckb_3qt_52b}

The namespace allows you to define the type of key used to identify the person associated to the event. Its configuration is optional. It is required if you want to retrieve, in your journeys, additional information coming from the [Real-time Customer Profile](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html). The namespace definition is not needed if you're only using data coming from a third-party system through a custom data source.

You can either use one of the predefined ones or create a new one using the Identity Namespace service. Refer to this [page](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html).

If you select a schema that has a primary identity, then the **[!UICONTROL Key]** and **[!UICONTROL Namespace]** fields are pre-filled. If there is no identity defined, we select _identityMap > id_ as the primary key. Then you have to select a namespace and the key will be pre-filled (below the **[!UICONTROL Namespace]** field) using _identityMap > id_.

When selecting fields, primary identity fields are tagged. 

![](../assets/primary-identity.png)


Select a namespace from the drop-down list.

![](../assets/journey17.png)

Only one namespace is allowed per journey. If you use several events in the same journey, they need to use the same namespace. See [](../building-journeys/journey.md).
