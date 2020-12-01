---
product: adobe campaign
solution: Journey Orchestration
title: Defining the payload fields
description: Learn about how to define the payload fields
---

# Defining the payload fields {#concept_yrw_3qt_52b}

The payload definition allows you to choose the information the system expects to receive from the event in your journey and the key to identify which person is associated to the event. The payload is based on the Experience Cloud XDM field definition. For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).

1. Select an XDM schema from the list and click on the **[!UICONTROL Payload]** field or on the **[!UICONTROL Edit]** icon.

    ![](../assets/journey8.png)

    All the fields defined in the schema are displayed. The list of fields varies from one schema to another. You can search for a specific field or use the filters to display all nodes and fields or only the selected fields. According to the schema definition, some fields may be mandatory and pre-selected. You cannot unselect them. 

    >[!NOTE]
    >
    >Make sure that you have added the "orchestration" mixin to the XDM schema. This will ensure that your schema contains all the required information to work with [!DNL Journey Orchestration].

    ![](../assets/journey9.png)

1. Select the fields you expect to receive from the event. These are the fields which the business user will leverage in the journey. They must also include the key that will be used to identify the person associated to the event (see [this page](../event/defining-the-event-key.md)).

    ![](../assets/journey10.png)

    >[!NOTE]
    >
    >The **[!UICONTROL eventID]** field is automatically added in the list of fields selected so that [!DNL Journey Orchestration] can identify the event. The system pushing the event should not generate an ID, it should use the one available in the payload preview. See [this page](../event/previewing-the-payload.md).

1. When you're done selecting the needed fields, click **[!UICONTROL Save]** or press **[!UICONTROL Enter]**.

    ![](../assets/journey11.png)

    The number of selected fields appears in the **[!UICONTROL Payload]** field.

    ![](../assets/journey12.png)
