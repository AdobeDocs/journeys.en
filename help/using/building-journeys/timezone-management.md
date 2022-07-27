---
product: adobe campaign
title: Time zone management
description: Learn about time zone management
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
---
# Time zone management {#timezone_management}

You can define a time zone in the [properties](../building-journeys/changing-properties.md) of your journey.

To access Properties,click on the pencil icon in the top-right of the screen.

This time zone will be used for every activity of the journey containing a time element such as:

* [Time condition](../building-journeys/condition-activity.md#time_condition)
* [Date condition](../building-journeys/condition-activity.md#date_condition)
* [Custom wait](../building-journeys/wait-activity.md#custom)

You can select a time zone or choose to use the time zone defined in the user profile.

>[!NOTE]
>
>The profile time zone works with the **timeZone** field existing in the **Preference Details** field group.

## Defining a fixed time zone {#fixed-timezone}

The time zone can also be fixed. Clear the pre-defined time zone and pick one from the drop-down list. If you use a fixed time zone, it will be the same for all individuals entering the journey.

To do so, in **[!UICONTROL Properties]**, select a time zone. 

![](../assets/journey72.png)

## Using profiles to define the journey time zone {#timezone-from-profiles}

If the entry event of the journey has a namespace, meaning that the journey can reach the Real-time Customer Profile service of Adobe Experience Platform, you may want to use the time zone defined at the profile level. To do so, in **Properties**, check **Use Profile time zone in waits and conditions**. This option is not checked by default.

If a time zone has been defined for a profile, it will be retrieved and used by the journey. If it hasn't, the time zone used will be the one defined in the timezone field.

![](../assets/journey73.png)

## Using time zones in expressions {#timezone-in-expressions}

The start and end dates of a journey cannot be linked to a specific time zone. They are automatically associated to the instance's time zone.
