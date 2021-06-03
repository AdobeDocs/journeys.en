---
product: adobe campaign
title: Building the journey
description: Learn how to build the advanced use case journey 
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: cca6ed3c-e151-4494-9e2d-9ed504bfc54b
---
# Building the journey {#concept_owm_kdy_w2b}

The **business user** can now build the journey. Our journey will include the following activities:

* two **[!UICONTROL Event]** activities: "LobbyBeacon" and "RestaurantBeacon"
* two **[!UICONTROL Condition]** activities
* three **[!UICONTROL Push]** activities and one **[!UICONTROL Email]** activity (using Adobe Campaign Standard)
* a **[!UICONTROL Wait]** activity
* four **[!UICONTROL End]** activities

>[!NOTE]
>
>The **[!UICONTROL Push]** and **[!UICONTROL Email]** activities are only available in the palette if you have Adobe Campaign Standard.

For additional information on how to build a journey, refer to [this page](../building-journeys/journey.md).

## First steps{#section_ntb_ws1_ffb}

1. In the top menu, click the **[!UICONTROL Home]** tab and **[!UICONTROL Create]** to create a new journey.

    ![](../assets/journey31.png)

1. Edit the journey's properties in the configuration pane displayed on the right side. Add a name and set it to last for one month, from the 1st to the 31st of December.

    ![](../assets/journeyuc2_12.png)

1. Start designing your journey by drag and dropping the "LobbyBeacon" event from the palette to the canvas. You can also double-click on the event in the palette to add it to the canvas.

    ![](../assets/journeyuc2_13.png)

1. Let's now add a condition to check that the person has not been contacted in the last 24 hours and check if he is a loyalty member. Drag and drop a condition activity into your journey.

    ![](../assets/journeyuc2_14.png)

1. Choose the **[!UICONTROL Data Source Condition]** type and click in the **[!UICONTROL Expression]** field. You can also define a condition label that will appear on the arrow, in the canvas. In our example, we replace "Condition 1" with "Loyalty member".

    ![](../assets/journeyuc2_15.png)

1. Click **[!UICONTROL Advanced mode]** and define the following condition based on the "timestamp" and "directMarketing.sends.value" fields coming from the Adobe Experience Platform data source. The syntax of the expression is:

    ```
    count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
        currentDataPackField.directMarketing.sends.value > 0 and
        currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
    and
        #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
    ```

    ![](../assets/journeyuc2_30.png)

1. Click the **[!UICONTROL Add a path]** button and create a second path for customers who have not been contacted in the last 24 hours and are not a loyalty member. Name the path "Not loyalty member". The syntax of the expression is:

    ```
    count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
        currentDataPackField.directMarketing.sends.value > 0 and
        currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
    and not
        #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
    ```

    >[!NOTE]
    >
    >In the second part of expression, "Profile" is optional.

1. We need to select a namespace. A namespace is preselected based on schema properties. You can keep the one preselected. For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

In our use case, we only want to react to those two conditions, so we don't check the box **[!UICONTROL Show path for other cases than the one(s) above]**.

Two paths are created after your condition:

* _Customers who have not been contacted in the last 24 hours and are loyalty members._
* _Customers who have not been contacted in the last 24 hours and are not loyalty members._

![](../assets/journeyuc2_16.png)

## First path: the customer is a loyalty member {#section_otb_ws1_ffb}

1. In the first path, let's add a condition to check if he has a reservation. Drag and drop a condition activity into your journey.

    ![](../assets/journeyuc2_17.png)

1. Choose the **[!UICONTROL Data Source Condition]** type, and define the condition based on the reservation status information retrieved from the reservation system:

    ```
    #{MarltonReservation.MarltonFieldGroup.reservation} == true
    ```

    ![](../assets/journeyuc2_18.png)

1. When you select a field from an external data source, the right part of the screen displays the list of parameters that were defined when configuring the external data source (see [this page](../usecase/configuring-the-data-sources.md)). Click on the parameter name and define the value of the reservation system key, the Experience Cloud ID, in our example:

    ```
    @{LobbyBeacon.endUserIDs._experience.mcid.id}
    ```

    ![](../assets/journeyuc2_19.png)

1. Since we also want to react to customers who do not have a reservation, we need to check the box **[!UICONTROL Show path for other cases than the one(s) above]**.

    ![](../assets/journeyuc2_20.png)

    Two paths are created:

    * _Customers who have booked a room_
    * _Customers who have not booked a room._

    ![](../assets/journeyuc2_21.png)

1. In the first path (room booked), drop a **[!UICONTROL Push]** activity, select your mobile app and your "Welcome" template.

    ![](../assets/journeyuc2_22.png)

1. Define the **[!UICONTROL Target]** fields required by the system to send the push. 

    * **[!UICONTROL Push platform]**: select the platform: **[!UICONTROL Apple Push Notification Server]** (Apple) or **[!UICONTROL Firebase Cloud Messaging]** (Android).
    * **[!UICONTROL Registration token]**: add the following expression (based on the configured event) using the advanced mode:

        ```
        @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
        ```

1. Define the Push notification personalization fields. In our example: first name and last name.

1. Add a "RestaurantBeacon" event.

    ![](../assets/journeyuc2_23.png)

1. Add a new **[!UICONTROL Push]** activity, select the "Meal discount" template and define the **[!UICONTROL Address]** and **[!UICONTROL Personalization]** fields. Add an **[!UICONTROL End]** activity.

    ![](../assets/journeyuc2_24.png)

1. We want to send a meal discount push notification only if the person enters the restaurant within the next 6 hours after the welcome push. To do this, we need to use a wait activity. Place your cursor on the welcome push activity and click on the "+" symbol. In the new path, add a wait activity and define a duration of 6 hours. The first eligible activity will be chosen. If the restaurant event is received less than 6 hours after the welcome push, the push activity is sent. If no restaurant event is received within the next 6 hours, the wait is chosen. Place an **[!UICONTROL End]** activity after the wait activity.

    ![](../assets/journeyuc2_31.png)

1. In the second path that follows the reservation condition (no room booked), add a **[!UICONTROL Push]** activity and select your "Room rates" template. Add an **[!UICONTROL End]** activity.

    ![](../assets/journeyuc2_25.png)

## Second path: the customer is not a loyalty member{#section_ptb_ws1_ffb}

1. In the second path that follows the first condition (customer is not a loyalty member), add an **[!UICONTROL Email]** activity and select your "Loyalty membership" template.

    ![](../assets/journeyuc2_26.png)

1. In the **[!UICONTROL Address]** field, select the email address from the data source.

    ![](../assets/journeyuc2_27.png)

1. Define the first name and last name personalization fields from the data source.

    ![](../assets/journeyuc2_28.png)

1. Add an **[!UICONTROL End]** activity.

Click on the **[!UICONTROL Test]** toggle and test your journey. If there is any error, deactivate the test mode, modify your journey and test it again. For more information on the test mode, refer to [this page](../building-journeys/testing-the-journey.md). 

![](../assets/journeyuc2_32bis.png)

When the test is conclusive, you can publish your journey from the top right drop-down menu.

![](../assets/journeyuc2_32.png)
