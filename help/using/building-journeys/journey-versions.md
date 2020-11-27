---
title: Journey versions
description: Learn about journey versions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Journey versions{#concept_ldc_k55_zgb}

In the journey list, all journey versions are displayed with the version number. See [this page](../building-journeys/using-the-journey-designer.md). When you search for a journey, newest versions appear at the top of the list the first time the application opens. Then, you can define the sorting you want and the application will keep it as a user preference. The journey's version is also displayed at the top of the journey edition interface, above the canvas.

![](../assets/journeyversions1.png)

## Limitations {#version-limitations}

- a journey starting with an event activity in v1 cannot start with something else than an event in further versions. You cannot start a journey with a **Segment Qualification** event. 
- a journey starting with a **Segment Qualification** activity in v1 must always start with a **Segment Qualification** in further versions. 
- The segment and namespace chosen in **Segment qualification** (first node) can not be changed in new versions.
- The re-entrance rule must be the same in all journey versions.

## Creating a new version {#creating-a-new-version}

If you need to modify to a live journey, you need to create a new version of your journey.

1. Open the latest version of your live journey, click **[!UICONTROL Create a new version]** and confirm.

    ![](../assets/journeyversions2.png)

    >[!NOTE]
    >
    >You can only create a new version from the latest version of a journey.

1. Make your modifications, click **[!UICONTROL Publish]** and confirm.

    ![](../assets/journeyversions3.png)

From the moment the journey is published, individuals will start to flow into the latest version of the journey. People who have already entered a previous version stay in it until they finish the journey. If they later re-enter the same journey, they will go into the latest version.

Journey versions can be stopped individually. All versions of journeys have the same name.

>[!NOTE]
>
>When you publish a new version of a journey, the previous version automatically ends and switches to the **Closed** status. No entrance in the journey will happen. Even if you stop the latest version, the previous version will stay closed. 
