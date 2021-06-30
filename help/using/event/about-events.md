---
product: adobe campaign
title: About events
description: Learn about events
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
---
# General principle {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="About events"
>abstract="An event is linked to a person. It relates to the behavior of a person or something happening linked to a person. This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

An event is linked to a person. It relates to the behavior of a person (for example, a person bought a product, visited a shop, exited a website, etc.) or something happening linked to a person (for example, a person reached 10 000 loyalty points). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

This configuration is **mandatory**, as [!DNL Journey Orchestration] is designed to listen to events, and always performed by a **technical user**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. You can use several events (in different steps of a journey) and several journeys can use the same event.

If you edit an event used in a draft or live journey, you can only change the name, the description or add payload fields. We strictly limit the edition of draft or live journeys to avoid breaking journeys.

You can define two types of events:

* **Rule-based** events: this type of event does not generate an eventID. Using the simple expression editor, you simply define a rule which will be used by the system to identify the relevant events that will trigger your journeys. This rule can be based on any field available in the event payload, for example the profile's location or the number of items added to the profile's cart. 

   >[!CAUTION]
   >
   >A capping rule is defined for rule-based events. It limits the number of qualified events that a journey can process to 5000 per seconds for a given Organization (ORG). It corresponds to Journey Orchestration SLAs. See this [page](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html).

* **System-generated** events: these events require an eventID. This eventID field is automatically generated when creating the event. The system pushing the event should not generate an ID, it should pass the one available in the payload preview. 

Journey Orchestration requires events to be streamed or batched into Adobe Experience Platform. This data does not necessarily need to go to the Real-Time Profile. If you would like to use the events for segmentation or lookup in a separate journey, we recommend you enable the dataset for profile.

To learn how to create an event, refer to this [page](../event/about-creating.md).
