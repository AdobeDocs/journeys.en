---
title: Defining the event key
description: Learn how to define the event key
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Defining the event key {#concept_ond_hqt_52b}

The key is the field or combination of fields is part of the event payload data and that will allow the system to identify the person associated to the event. The key can be, for example, the Experience Cloud ID, a CRM ID or an email address.

If you plan to leverage data stored in the Real-time Customer Profile database, you must select, as the event key, information you defined as a profile's identity in the [Real-time Customer Profile Service](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html).

It will allow the system to perform the reconciliation between the event and the individual's profile. If you select a schema that has a primary identity, then the **[!UICONTROL Key]** and **[!UICONTROL Namespace]** fields are pre-filled. If there is no identity defined, we select _identityMap > id_ as the primary key. Then you have to select a namespace and the key will be pre-filled (below the **[!UICONTROL Namespace]** field) using _identityMap > id_.

When selecting fields, primary identity fields are tagged. 

![](../assets/primary-identity.png)

If you need to use a different key, such as a CRM ID or an email address, you need to add it manually:

1. Click inside the **[!UICONTROL Key]** field or on the pencil icon.

    ![](../assets/journey16.png)

1. Select the field chosen as the key in the list of payload fields. You can also switch to the advanced expression editor to create more complex keys (for example, a concatenation of two field of the events). See below, in this section.

    ![](../assets/journey20.png)

When the event is received, the value of the key will allow the system to identify the person associated to the event. Associated to a namespace (see [this page](../event/selecting-the-namespace.md)), the key can be used to perform queries on the Adobe Experience Platform. See [this page](../building-journeys/about-orchestration-activities.md).
The key is also used to check that a person is in a journey. Indeed, a person cannot be at two different places in the same journey. As a result, the system does not allow the same key, for example the key CRMID=3224, to be at different places in the same journey.

You also have access to the advanced expression functions (**[!UICONTROL Advanced mode]**) if you want to perform additional manipulations. These functions let you manipulate the values used to carry out specific queries such changing formats, performing field concatenations, taking into account only a part of a field (for example the 10 first characters). See [this page](../expression/expressionadvanced.md).  
