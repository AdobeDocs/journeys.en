---
title: Building the journey
description: Learn how to build the simple use case journey
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Building the journey{#concept_eyw_mcy_w2b}

The **business user** can now build the journey. Our journey will only include one path with the following activities:

* the "SpaBeacon" **[!UICONTROL Event]**: when a person walks near the spa beacon, the system will receive an event and the journey will start for that person.
* a **[!UICONTROL Condition]** activity to check that the person is a woman
* an **[!UICONTROL Email]** activity (using Adobe Campaign Standard)
* an **[!UICONTROL End]** activity

>[!NOTE]
>
>The **[!UICONTROL Push]** and **[!UICONTROL Email]** activities are only available in the palette if you have Adobe Campaign Standard.

For additional information on how to build a journey, refer to [this page](../building-journeys/journey.md).

1. In the top menu, click the **[!UICONTROL Home]** tab and **[!UICONTROL Create]** to create a new journey.

    ![](../assets/journey31.png)

1. Edit the journey's properties in the configuration pane displayed on the right side. We name it "Spa journey" and set it to last for one month, from the 1st to the 31st of December.

    ![](../assets/journeyuc1_8.png)

1. Start designing your journey by drag and dropping the "SpaBeacon" event from the palette to the canvas. You can also double-click on the event in the palette to add it to the canvas.

    ![](../assets/journeyuc1_9.png)

1. Let's now add a condition to check that the person is a woman. Drag and drop a condition activity into your journey.

    ![](../assets/journeyuc1_10.png)

1. Choose the **[!UICONTROL Data Source Condition]** type and click in the **[!UICONTROL Expression]** field. You can also define a condition label that will appear on the arrow, in the canvas.

    ![](../assets/journeyuc1_11.png)

1. Using the simple expression editor, look for the gender field (_person > gender_) and drop it to the right to create the following condition: "gender is equal to "Female".

    ![](../assets/journeyuc1_12.png)

1. Drop an **[!UICONTROL Email]** activity and select your "Spa discount" transactional messaging template. This template was designed using Adobe Campaign. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

    ![](../assets/journeyuc1_13.png)

1. Click inside the **[!UICONTROL Email]** field and select the email address from the data source.

    ![](../assets/journeyuc1_14.png)

1. In the same way, define the first name and last name personalization fields from the data source.

    ![](../assets/journeyuc1_15.png)

1. Drop an **[!UICONTROL End]** activity.

    ![](../assets/journeyuc1_17.png)

1. Click on the **[!UICONTROL Test]** toggle and test your journey using test profiles. If there is any error, deactivate the test mode, modify your journey and test it again. For more information on the test mode, refer to [this page](../building-journeys/testing-the-journey.md). 

    ![](../assets/journeyuc1_18bis.png)

1. When the test is conclusive, you can publish your journey from the top right drop-down menu.

    ![](../assets/journeyuc1_18.png)

Next time a woman walks near the spa beacon, she will immediately receive a "Spa discount" personalized email.
