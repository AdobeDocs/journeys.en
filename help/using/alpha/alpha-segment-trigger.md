---
product: adobe campaign
solution: Journey Orchestration
title: Read Segment activity
description: Learn more about the Read Segment activity.
---

# Read Segment activity {#segment-trigger-activity}

## About the Read Segment activity {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>If an Adobe Campaign Standard out-of-the-box action activity is present in the canvas at publication time or test mode activation time, the journey will be throttled at 13 entrances per second. Otherwise, the journey will be throttled at 1000 events per second.

The Read Segment activity allows you to make all individuals belonging to an Adobe Experience Platform segment enter a journey. Entrance into a journey can be executed either once, or on a regular basis.

Let's say you have a Gold customer segment on Adobe Experience Platform. With the Read Segment activity, you can make all individuals belonging to the Gold customer segment enter a journey and make them flow into individualized journeys that will leverage all journey functionalities: conditions, timers, events, actions.

## Configuring the activity {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Due to segment export latencies, it is not possible to trigger a segment-based journey in a shorter timeframe than 1 hour.

1. Unfold the **[!UICONTROL Orchestration]** category and drop a **[!UICONTROL Read Segment]** activity into your canvas.

    The activity must be positioned as the first step of a journey.

1. Add a **[!UICONTROL Label]** to the activity (optional).

1. In the **[!UICONTROL Segment]** field, choose the Adobe Experience Platform segment that will enter the journey, then click **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Note that you can customize the columns displayed in the list and sort them.

    ![](../assets/segment-trigger-segment-selection.png)

   Once the segment is added, the **[!UICONTROL Copy]** button allows you to copy its name and ID:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. In the **[!UICONTROL Namespace]** field, choose the namespace to use in order to identify the individuals. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

    >[!NOTE]
    >
    >Individuals belonging to a segment that does not have the selected identity (namespace) among their different identities cannot enter the journey.

1. The **[!UICONTROL Read Segment]** activity allows you to specify the time at which the segment will enter the journey. To do this, click the **[!UICONTROL Edit journey schedule]** link to access the journey's properties, then configure the **[!UICONTROL Scheduler type]** field.

    ![](../assets/segment-trigger-schedule.png)

    By default, segments enter the journey **[!UICONTROL As soon as possible]**, meaning 1 hour after the journey is published. If you want to make the segment enter the journey on a specific date/time or on a recurring basis, select the desired value from the list.

    >[!NOTE]
    >
    >Note that the **[!UICONTROL Schedule]** section is only available when a **[!UICONTROL Read Segment]** activity has been dropped in the canvas.

    ![](../assets/segment-trigger-properties.png)

## Testing and publishing the journey {#testing-publishing}

The **[!UICONTROL Read Segment]** activity allows you to test the journey either on a unitary profile, or on 100 randomly test profiles selected among the profiles qualified for the segment.

To do this, activate the test mode, then select the desired option from the left pane.

![](../assets/segment-trigger-test-modes.png)

You can then configure and run the test mode as usual. Detailed steps on how to test a journey are presented in [this section](../building-journeys/testing-the-journey.md).

Once the test is running, the **[!UICONTROL Show logs]** button allows you to see the test results according to the selected test option:

* **[!UICONTROL Single profile at a time]**: the test logs display the same information as when using the unitary test mode. For more on this, refer to [this section](../building-journeys/testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**: the test logs allow you to track the progression of the segment export from Adobe Experience Platform, as well as the individual progress of all the persons that entered the journey.

    Note that testing the journey using up to 100 profiles at once does not allow you to track the progress of the individuals in the journey using the visual flow.

    ![](../assets/read-segment-log.png)

Once the tests are successfull, you can publish your journey (see [Publishing the journey](../building-journeys/publishing-the-journey.md)). Individuals belonging to the segment will enter the journey on the date/time specified in the journey's properties **[!UICONTROL Scheduler]** section.

>[!NOTE]
>
>When doing a new version of a segment-based journey that is not recurrent (starting as soon as possible or "once"), all the individuals who entered the journey previously will not re-enter its new version when you will publish it. If you want to allow them to re-enter, you should duplicate the journey.
