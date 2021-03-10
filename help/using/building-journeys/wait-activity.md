---
product: adobe campaign
solution: Journey Orchestration
title: Wait activity
description: Learn about the wait activity
feature: Journeys
role: Business Practitioner
level: Intermediate
---

# Wait activity{#section_rlm_nft_dgb}

If you want to wait before executing the next activity in the path, you can use a **[!UICONTROL Wait]** activity. It allows you to define the moment when the next activity will be executed. Four options are available:

* [Duration](#duration) 
* [Fixed date](#fixed_date) 
* [Custom](#custom) 
<!--* [Email send time optimization](#email_send_time_optimization)-->

## About the Wait activity{#about_wait}

Here is how waits are prioritized when you use several waits in parallel. If they have the same time configuration and a different but overlapping condition, the wait positioned above will be the one prioritized. For example, the condition of the first wait is “being a woman” and the condition of the second wait in parallel is “being a VIP”. The first wait activity will be prioritized

Also note that if two different waits are in parallel, the one occurring first will be prioritized, regardless of its vertical position. For example, if a 1-hour wait is above and a 30-minute wait is below, after 30 minutes, the 30-minute wait will be processed.

You can define a condition if you want to restrict the wait to a certain population.

>[!NOTE]
>
>The maximum wait duration is 30 days.
>
>In test mode, the **[!UICONTROL Wait time in test]** parameter allows you to define the time that each wait activity will last. The default time is 10 seconds. This will ensure that you get the test results quickly. See [this page](../building-journeys/testing-the-journey.md) 

## Duration wait{#duration}

Select the duration of the wait before the execution of the next activity.

![](../assets/journey55.png)

## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![](../assets/journey56.png)

## Custom wait{#custom}

This option lets you define a custom date, for example 12 July 2020 at 5pm, using an advanced expression based on a field coming from an event or a data source. It does not let you define a custom duration, for example, 7 days. The expression in the expression editor should provide a dateTimeOnly format. See [this page](../expression/expressionadvanced.md). For more information on dateTimeOnly format, see [this page](../expression/data-types.md).

>[!NOTE]
>
>You can leverage a dateTimeOnly expression or use a function to convert to a dateTimeOnly. For example: ```toDateTimeOnly(@{Event.offerOpened.activity.endTime})```, the field in the event being of the form 2016-08-12T09:46:06Z.
>
>The **time zone** is expected in the properties of your journey. As a result, it is not possible today from the interface to directly point at a full ISO-8601 timestamp mixing time and time zone offset like 2016-08-12T09:46:06.982-05. See [this page](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
