---
product: adobe campaign
title: Update profile
description: Update profile
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
---
# Update profile {#update-profile}

The **[!UICONTROL Update profile]** action activity allows you to update an existing Adobe Experience Platform profile with information coming from the event, a datasource or using a specific value.

## Important notes

* The **Update profile** action can only be used in journeys starting with an event that has a namespace.
* The action only updates existing fields, it does not create new profile fields.
* You cannot use the **Update profile** action to generate experience events, for example a purchase.
* Just like any other action, you can define an alternative path in case of error or timeout and you cannot place two actions in parallel.
* The update request sent to Platform will be fast but not immediate/within a second. It will take normally a few seconds but sometimes more with no guarantee. As a result, for example, if an action is using "field 1" updated by an Update Profile action positioned right before, you should not expect that "field 1" will be updated in the action.
* In test mode, the profile update will not be simulated. The update will be performed on the test profile. 
* The **Update profile** activity does not support XDM fields that are defined as an enumeration.

## Using the profile update

1. Design your journey by starting with an event. See this [section](../building-journeys/journey.md).

1. In the **Action** section of the palette, drop the **Update profile** activity into the canvas.

   ![](../assets/profileupdate0.png)

1. Select a schema from the list.

1. Click on **Fields** to select the field you want to update. Only one field can be selected.

   ![](../assets/profileupdate2.png)

1. Select a dataset from the list. 

   >[!NOTE]
   >
   >The **Update profile** action updates the profile data in realtime, but it does not update datasets. The dataset selection is needed as the profile is a record related to a dataset.

1. Click on the **Value** field to define the value you want to use:

   * Using the simple expression editor, you can select a field from a data source or from the incoming event.

      ![](../assets/profileupdate4.png)

   * If you want to define a specific value or leverage advanced functions, click on **Advanced mode**.

      ![](../assets/profileupdate3.png)

The **Update profile** is now configured.

![](../assets/profileupdate1.png)
