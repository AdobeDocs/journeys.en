---
product: adobe campaign
solution: Journey Orchestration
title: About Adobe Analytics data
description: Learn how to leverage Adobe Analytics data
feature: Journeys
role: Business Practitioner
level: Intermediate
---

# Leveraging Adobe Analytics data{#analytics-data}

>[!NOTE]
>
>This section only applies for rule-based events and customers who need to use Adobe Analytics data.

You can leverage all of the Adobe Analytics behavioral event data that you are already capturing and streaming into the Platform in order to trigger journeys and automate experiences for your customers.

For this to work, you need to activate, in Adobe Experience Platform, the report suite that you want to leverage:

1. In Adobe Experience Platform, select **[!UICONTROL Sources]** then **[!UICONTROL Add data]** in the Adobe Analytics section. The list of available Adobe Analytics report suites is displayed.

1. Pick the report suite you want to enable, click **[!UICONTROL Next]** and click **[!UICONTROL Finish]**. 

1. Share the source Data ID with your Alpha program point of contact. 

This enables the Analytics source connector for that report suite. Whenever the data comes in, it is transformed into an Experience event and sent into Adobe Experience Platform. 

![](../assets/alpha-event9.png)

For more information on the Adobe Analytics source connector, refer to the [documentation](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) and [tutorial](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
