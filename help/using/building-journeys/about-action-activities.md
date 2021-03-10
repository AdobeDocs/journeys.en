---
product: adobe campaign
solution: Journey Orchestration
title: About action activities
description: Learn about action activities
feature: Journeys
role: Business Practitioner
level: Intermediate
---

# About action activities {#concept_hbj_hrt_52b}

From the palette, on the left-hand side of the screen, below **[!UICONTROL Events]** and **[!UICONTROL Orchestration]**, you will find the **[!UICONTROL Actions]** category.

![](../assets/journey58.png)

These activities represent the different available communication channels. You can combine them to create a cross-channel scenario. 

If you have Adobe Campaign Standard, the following out-of-the-box action activities are available: **[!UICONTROL Email]**, **[!UICONTROL Push]** and **[!UICONTROL SMS]**. Refer to [this page](../building-journeys/using-adobe-campaign-actions.md).

If you've configured custom actions, they will also appear here (see [this page](../building-journeys/using-custom-actions.md)).

When you drop an action activity in the canvas, you can define a **[!UICONTROL Label]**. This allows you to add a suffix to the action name that will appear under your activity in the canvas. This is useful if you use the same action several times in your journey and want to identify them more easily. Reports will also be easier to read. You can also add an optional **[!UICONTROL Description]**.

![](../assets/journey59bis.png)

When an error occurs in an action or a condition, the journey of an individual stops. The only way to make it continue is to check the box **[!UICONTROL Add an alternative path in case of a timeout or an error]**. See [this section](../building-journeys/using-the-journey-designer.md#paths).
