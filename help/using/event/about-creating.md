---
product: adobe campaign
title: Creating an event
description: Learn how to create an event
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
---
# Creating a new event {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


Here are the main steps to configure a new event:

1. In the top menu, click on the **[!UICONTROL Events]** tab. The list of events is displayed. Refer to [this page](../about/user-interface.md) for more information on the interface.

    ![](../assets/journey5.png)

1. Click **[!UICONTROL Add]** to create a new event. The event configuration pane opens on the right side of the screen. Enter a name for your event. You can also add a description.

    ![](../assets/journey6.png)

    >[!NOTE]
    >
    >Do not use spaces or special characters. Do not use more than 30 characters.

1. In the **[!UICONTROL Event ID type]** field, select the event type you want to use. 

   ![](../assets/journey6bis.png)

   * **Rule-based** events: this type of event does not generate an eventID. In the **Event ID condition** field, you simply define a rule which will be used by the system to identify the relevant events that will trigger your journeys. This rule can be based on any field available in the event payload, for example the profile's location or the number of items added to the profile's cart.

   * **System-generated** events: this type requires an eventID. This eventID field is automatically generated when creating the event and added to the payload preview. The system pushing the event should not generate an ID, it should pass the one available in the payload preview. See [this section](../event/previewing-the-payload.md).
   
   >[!NOTE]
   >
   >Read more on event types in [this section](../event/about-events.md).
1. The number of journeys that use this event is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** icon to display the list of journeys using this event.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. You will then be able to use this information in your journey. See [this page](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >When you select the **[!UICONTROL System Generated]** type, only schemas that have the eventID type mixin are available. When you select the **[!UICONTROL Rule Based]** type, all Experience Event schemas are available.

1. For rule-based events, click inside the **[!UICONTROL Event ID condition]** field. Using the simple expression editor, define the condition that will be used by the system to identify the events that will trigger your journey.
  ![](../assets/alpha-event6.png)

   In our example, we wrote a condition based on the profile's city. This means that whenever the system receives an event that matches this condition (**[!UICONTROL City]** field and **[!UICONTROL Paris]** value), it will pass it to Journey Orchestration.

   >[!NOTE]
   >
   >The advanced expression editor is not available when defining the **[!UICONTROL Event ID condition]**. In the simple expression editor, not all operators are available, they depend on the data type. For example, for a string type of field, you can use "contains" or "equal to".

1. Add a namespace. This step is optional but recommended as adding a namespace allows you to leverage information stored in the Real-time Customer Profile Service. It defines the type of key the event has. See [this page](../event/selecting-the-namespace.md).
1. Define the key: choose a field from your payload fields or define a formula to identify the person associated to the event. This key is automatically setup (but can still be edited) if you select a namespace. Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). See [this page](../event/defining-the-event-key.md). 
1. Click **[!UICONTROL Save]**.

    ![](../assets/journey7.png)

    The event is now configured and ready to be dropped into a journey. Additional configuration steps are required to receive events. See [this page](../event/additional-steps-to-send-events-to-journey-orchestration.md).
