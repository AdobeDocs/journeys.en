---
product: adobe campaign
solution: Journey Orchestration
title: Configuring the event
description: Learn how to configure the event for the journey simple use case
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
---
# Configuring the event{#concept_y44_hcy_w2b}

In our scenario, we need to receive an event each time a person walks near a beacon positioned next to the spa. The **technical user** needs to configure the event the system will listen to in our journey.

For additional information on event configuration, refer to [this page](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

    ![](../assets/journeyuc1_1.png)

1. We enter the name without spaces or special characters: "SpaBeacon".

    ![](../assets/journeyuc1_2.png)

1. We then select the schema and define the payload expected for this event. We select the fields needed from the XDM normalized model. We need the Experience Cloud ID to identify the person in the Real-time Customer Profile database: _endUserIDs > experience > mcid > id_. An ID is automatically generated for this event. This ID is stored in the **[!UICONTROL eventID]** field (_experience > campaign > orchestration > eventID_). The system pushing the event should not generate an ID, it should use the one available in the payload preview. In our use case, this ID is used to identify the beacon location. Each time a person walks near the spa beacon, an event will be sent containing this specific event ID. This allows the system to know which beacon triggered the event sending.

    ![](../assets/journeyuc1_3.png)

    >[!NOTE]
    >
    >The list of fields varies from one schema to another. According to the schema definition, some fields may be mandatory and pre-selected.

1. We need to select a namespace. A namespace is preselected based on schema properties. You can keep the one preselected. For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

    ![](../assets/journeyuc1_6.png)

1. A key is preselected based on schema properties and the namespace selected. You can keep it.

    ![](../assets/journeyuc1_5.png)

1. Click **[!UICONTROL Save]**.

1. Click the **[!UICONTROL View Payload]** icon to preview the payload expected by the system and share it with to the person responsible for the event sending. This payload will need to be configured in the postback of the Mobile Services administration console. 

    ![](../assets/journeyuc1_7.png)

    The event is ready to be used in your journey. You now need to configure the mobile application so that it can send the expected payload to the Streaming Ingestion APIs endpoint. See [this page](../event/additional-steps-to-send-events-to-journey-orchestration.md).
