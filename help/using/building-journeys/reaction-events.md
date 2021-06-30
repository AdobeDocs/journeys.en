---
product: adobe campaign
title: Reactions events
description: Learn about reaction events
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
---
# Reaction events {#section_dhx_gss_dgb}

Among the different event activities available in the palette, you will find the built-in **[!UICONTROL Reactions]** event. This activity allows you to react to tracking data related to a message sent with email, SMS or push activities within the same journey. This information comes from transactional messaging in Adobe Campaign Standard. We capture this information in real-time at the moment it is shared with the Adobe Experience Platform. For push notifications, you can react to clicked, sent or failed messages. For SMS messages, you can react to sent or failed messages. For emails, you can react to clicked, sent, opened or failed messages.

You can also use this mechanism to perform an action when there is no reaction to your messages. To do this, create a second path parallel to the reaction activity and add a wait activity. If there is no reaction during the period defined in the wait activity, the second path will be chosen. You can choose to send, for example, a follow-up message. 

Note that you can only use a reaction activity in the canvas if there is an email, push or SMS activity before.

See [About action activities](../building-journeys/about-action-activities.md).

 ![](../assets/journey45.png)

Here are the different steps to configure the reaction events:

1. Add a **[!UICONTROL Label]** to the reaction. This step is optional.
1. From the drop-down list, select the action activity you want to react to. You can select any action activity positioned in the previous steps of the path.
1. Depending on the action you selected (an email, SMS or a push notification), choose what you want to react to. 
1. You can define an event timeout (between 40 seconds and 30 days) and a timeout path. This will create a second path for individuals who did not react within the defined duration. When testing a journey that uses a reaction event, the test mode **[!UICONTROL Wait time]** default and minimum value is 40 seconds. See [this section](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Reactions events work with Adobe Campaign Standard, wether it's deployed on AWS or Azure servers.
>
>Reaction events cannot track email, SMS or push actions that take place in a different journey.
>
>Reaction events track clicks on links of the type "tracked" (see this [page](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Unsubscription and mirror page links are not taken into account.

>[!IMPORTANT]
>
>Email clients such as Gmail allow image blocking. Emails opens are tracked using a 0-pixel image included in the email. If images are blocked, email opens will not be taken into account.
