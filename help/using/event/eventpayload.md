---
title: Defining the payload fields
description: Learn about how to define the payload fields
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
index: n
internal: n
snippet: y
---

# Defining the payload fields {#concept_yrw_3qt_52b}

The payload definition allows you to choose the information the system expects to receive from the event in your journey and the key to identify which person is associated to the event. The payload is based on the Experience Cloud XDM field definition. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Select an XDM schema from the list and click on the **Payload** field or on the **Edit** icon.

    ![](../assets/journey8.png)

    All the fields defined in the schema are displayed. The list of fields varies from one schema to another. You can search for a specific field or use the filters to display all nodes and fields or only the selected fields. According to the schema definition, some fields may be mandatory and pre-selected. You cannot unselect them. 

    >[!NOTE]
    >
    >Make sure that you have added the "orchestration" mixin to the XDM schema. This will ensure that your schema contains all the required nodes to work with Journey Orchestration.

    ![](../assets/journey9.png)

1. Select the fields you expect to receive from the event. These are the fields which the business user will leverage in the journey. They must also include the key that will be used to identify the person associated to the event (see [](../event/eventkey.md).

    ![](../assets/journey10.png)

    >[!NOTE]
    >
    >The **eventID** field is automatically added in the list of fields selected so that Journey Orchestration can identify the event. The system pushing the event should not generate an ID, it should use the one available in the payload preview. See [](../event/eventpayloadpreview.md).

1. When you're done selecting the needed fields, click **Save** or press **Enter**.

    ![](../assets/journey11.png)

    The number of selected fields appears in the **Payload** field.

    ![](../assets/journey12.png)
