---
product: adobe campaign
solution: Journey Orchestration
title: Jumping from one journey to another
description: Jumping from one journey to another
---

# Update profile {#update-profile}

The **[!UICONTROL Update profile]** action activity allows you to update an existing Adobe Experience Platform profile with information coming from the event, a datasource or using a specific value.

## Important notes

* The **Update profiles** action can only be used in journeys starting with an event that has a namespace.
* This action has the same timeout management of other actions.
* Like any other action, you cannot place two actions in parallel.
* In test mode, the profile update will update the test profile.  
* In case of errors, you can use an alternative path, just like for any errors in custom action.
* The action does update only, no creation.

## Using the profile update

1. Design your journey by starting with an event. See this [section](../building-journeys/journey.md).
1. In the **Action** section of the palette, drop the **Update profile** activity into the canvas.
   ![](../assets/profileupdate0.png)
1. Select a schema from the list and then click on **Fields** to select the field you want to update in the Adobe Experience Platform profiles. Only one field can be selected. 
   ![](../assets/profileupdate2.png)
1. Select a dataset from the list and then click on the **Value** field. Using the simple expression editor, you can select a field from a data source or from the incoming event. If you want to define a specific value, click on **Advanced mode** and type in the value.
   ![](../assets/profileupdate3.png)

   ![](../assets/profileupdate1.png)

When an individual enters the journey and reaches the **Update profile** activity, this information will be sent to Adobe Experience Platform and his profile will be updated. The selected field will be updated with the value defined.
