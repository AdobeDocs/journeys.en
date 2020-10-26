---
title: About journey building
description: As a business user, learn how to combine event, orchestration, and action activities to build a journey.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---


# Creating a journey {#concept_gq5_sqt_52b}

This step is performed by the **business user**. This is where you create your journeys. Combine the different event, orchestration and action activities to build your multi-step cross-channel scenarios.

The journey interface allows you to easily drag and drop activities from the palette into the canvas. You can also double-click on an activity to add it in the canvas at the next step available. Each activity has a specific role and place in the process. The activities are sequenced. When an activity is finished, the flow continues and processes the next activity, and so on.

Only one namespace is allowed per journey. When you drop the first event, events with different namespaces will be grayed out. If the first event doesn't have a namespace, then all events with a namespace will be grayed out. See [](../event/selecting-the-namespace.md). Also, Adobe Experience Platform field groups are grayed out if the journey has events without a namespace. And finally, if you use several events in the same journey, they need to use the same namespace.

## Quick start {#creating_journey}

Here are the main steps to create and publish a journey.

1. In the top menu, click the **[!UICONTROL Home]** tab. 

    The list of journeys is displayed. See [](../building-journeys/using-the-journey-designer.md) for more information on the interface.

    ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

    ![](../assets/journey31.png)

1. Edit the journey's properties in the configuration pane displayed on the right side. See [](../building-journeys/changing-properties.md).

    ![](../assets/journey32.png)

1. Start by drag and dropping an event activity from the palette into the canvas. You can also double-click on an activity to add it to the canvas.

    ![](../assets/journey33.png)

1. Drag and drop your other activities and configure them. See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

    ![](../assets/journey34.png)

1. Your journey is automatically saved. Test your journey and publish it. See [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

    ![](../assets/journey36.png)

## Ending a journey {#ending_a_journey}

There are two ways to end a journey:

* The person arrives at the last activity of a path. This last activity can be an end activity or another activity. There is no obligation to end a path with an end activity. See [](../building-journeys/end-activity.md).
* The person arrives at a condition activity (or a wait activity with a condition) and does not match any of the conditions.

The person can then re-enter the journey if re-entrance is allowed. See [](../building-journeys/changing-properties.md).
