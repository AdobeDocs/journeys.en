---
product: adobe campaign
title: Configuring the data sources
description: Learn how to configure the data source for the journey advanced use case
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
---
# Configuring the data sources {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


In our use case, we want to use personalization data for our messages. We also need to check if the person is a loyalty member and has not been contacted in the last 24 hours. This information is stored in the Real-time Customer Profile database. The **technical user** needs to configure the Adobe Experience Platform data source to retrieve those fields.

For additional information on data source configuration, refer to [this page](../datasource/about-data-sources.md).

1. In the menu pane, select **[!UICONTROL Admin]**. In the **[!UICONTROL Data sources]** section, click **[!UICONTROL Manage]**.
1. Select the build-in Adobe Experience Platform data source.

    ![](../assets/journey23.png)

1. In the pre-configured group fields, check that the following fields are selected:

    * _person > name > firstName_
    * _person > name > lastName_
    * _personalEmail > address_

1. Click **[!UICONTROL Add a New Field Group]**, select a **[!UICONTROL Profiles]** schema and add the **Loyalty member** field for our condition. The **Loyalty member** field is a custom field and was added in XDM: "_customer > marlton > loyaltyMember"

    ![](../assets/journeyuc2_6.png)

1. Click **[!UICONTROL Add a New Field Group]**, select an **[!UICONTROL ExperienceEvent]** schema and choose the fields needed for our condition on the number of messages sent in a given period: _timestamp_ for the date and _directMarketing > sends > value_ for the number of messages sent.

    ![](../assets/journeyuc2_7.png)

1. Click **[!UICONTROL Save]**.

We also need to check if the person has a reservation in the hotel reservation system. The **technical user** needs to configure a second data source to retrieve this field.

1. In the list of data sources, click **[!UICONTROL Add]** to add a new external data source to define the connection to your hotel reservation system.

    ![](../assets/journeyuc2_9.png)

1. Enter a name for your data source and the URL of the external service, for example: _https://marlton.com/reservation_

    >[!CAUTION]
    >
    >We strongly recommend using HTTPS for security reasons.

1. Configure the authentication depending on the external service configuration: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** or **[!UICONTROL API key]**. In our example, we choose "Basic" for the type and specify the username and password for the API call.

    ![](../assets/journeyuc2_10.png)

1. Click **[!UICONTROL Add a New Field Group]** to define the information to be retrieved and the API parameters. For our example, there is only one parameter (the id), so we need to create one field group with the following information:

    * **[!UICONTROL Method]**: select the POST or GET method. In our case, we select the GET method.
    * **[!UICONTROL Response Payload]**: click inside the **[!UICONTROL Payload]** field and paste an example of the payload. Verify that the field types are correct. Each time the API is called, the system will retrieve all the fields included in the payload example. In our example, the payload only contains the reservation status:

    ```
    {
        "reservation" : true
    }
    ```

    * **[!UICONTROL Dynamic Values]**: enter the parameter corresponding to the key used to identify each customer, "id" in our example. The value of this parameter will be defined in the journey.

    ![](../assets/journeyuc2_11.png)

1. Click **[!UICONTROL Save]**.

    The data sources are now configured and ready to be used in your journey.
