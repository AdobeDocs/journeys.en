---
product: adobe campaign
solution: Journey Orchestration
title: About events
description: Learn about events
---

# General principle {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="About events"
>abstract="An event is linked to a person. It relates to the behavior of a person (for example, a person bought a product, visited a shop, exited a website, etc.) or something happening linked to a person (for example, a person reached 10 000 loyalty points). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

An event is linked to a person. It relates to the behavior of a person (for example, a person bought a product, visited a shop, exited a website, etc.) or something happening linked to a person (for example, a person reached 10 000 loyalty points). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

This configuration is **mandatory**, as [!DNL Journey Orchestration] is designed to listen to events, and always performed by a **technical user**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. You can use several events (in different steps of a journey) and several journeys can use the same event.

If you edit an event used in a draft or live journey, you can only change the name, the description or add payload fields. We strictly limit the edition of draft or live journeys to avoid breaking journeys.

You can define two types of events:

* **Rule based** events: this type of event does not generate an eventID. Using the simple expression editor, you simply define a rule which will be used by the system to identify the relevant events that will trigger your journeys. This rule can be based on any field available in the event payload, for example the profile's location or the number of items added to the profile's cart. [Learn more about rule-based event creation].

* **System generated** events: these events require an eventID. This eventID field is automatically generated when creating the event. The system pushing the event should not generate an ID, it should pass the one available in the payload preview. Learn more in the [Journey Orchestration documentation].

To learn how to create an event, refer to this [page](../event/about-creating.md).

