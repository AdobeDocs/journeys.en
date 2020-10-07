---
title: Configuring the events
description: Learn how to configure the events for the journey advanced use case
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Configuring the events {#concept_sbp_5cy_w2b}

In our scenario, we need to receive an event each time a person enters the Marlton hotel and the restaurant. The **technical user** needs to configure the two events we want the system to listen to in our journey.

For additional information on event configuration, refer to [](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

    ![](../assets/journeyuc1_1.png)

1. We enter the name with no spaces or special characters: "LobbyBeacon".

    ![](../assets/journeyuc2_1.png)

1. We then select the schema and define the payload expected for this event. We select the fields needed from the XDM normalized model. We need the Experience Cloud ID to identify the person in the Real-time Customer Profile database: "endUserIDs > _experience > mcid > id". 

    We also need the registration token to send push messages: "_experience > campaign > message > profile > pushNotificationTokens > token"

    An ID is automatically generated for this event. This ID is stored in the **[!UICONTROL eventID]** field ("_experience > campaign > orchestration > eventID"). The system pushing the event should not generate an ID, it should use the one available in the payload preview. In our use case, this ID is used to identify the beacon location. Each time a person walks near the lobby beacon, an event will be sent containing this specific event ID. The same principle applies to the restaurant beacon events. This allows the system to know which beacon triggered the event sending.

    ![](../assets/journeyuc2_2.png)
 
    >[!NOTE]
    >
    >The list of fields varies from one schema to another. According to the schema definition, some fields may be mandatory and pre-selected.

1. We need to select a namespace. A namespace is preselected based on schema properties. You can keep the one preselected. For more information on namespaces, see [](../event/selecting-the-namespace.md).

    ![](../assets/journeyuc2_4.png)

1. A key is preselected based on schema properties and the namespace selected. You can keep it.

    ![](../assets/journeyuc2_4bis.png)

1. Click **[!UICONTROL Save]**.

1. Click the **[!UICONTROL View Payload]** icon to preview the payload expected by the system and share it with to the person responsible for the event sending.  This payload will need to be configured in the postback of the Mobile Services administration console.

    ![](../assets/journeyuc2_5.png)

In the same way, create the "RestaurantBeacon" event. Your two beacon events are created and can now be used in our journey. You now need to configure the mobile application so that it can send the expected payload to the Streaming Ingestion APIs endpoint. See [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
