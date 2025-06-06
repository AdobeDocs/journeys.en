---
product: adobe campaign
solution: Journey Orchestration
title: Sending a message using Campaign v7/v8
description: Sending a message using Campaign v7/v8
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
---
# Sending a message using Campaign v7/v8 {#campaign-classic-use-case}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


This use case presents all the steps needed to send an email using the integration with Adobe Campaign Classic v7 and Adobe Campaign v8. 

We will first create a transactional email template in Campaign. Then, in Journey Orchestration, we'll create the event, action and design the journey.

To learn more on the Campaign integration, refer to these pages:

* [Creating a Campaign action](../action/acc-action.md)
* [Using the action in a journey](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Your Campaign instance needs to be provisioned for this integration. The Transactional Messaging feature needs to be configured.

1. Log in to your Campaign control instance. 

1. Under **Administration** > **Platform** > **Enumerations**, select the **Event type** (eventType) enumeration. Create a new event type ("journey-event", in our example). You will have to use the internal name of the event type when writing the JSON file later. 

    ![](../assets/accintegration-uc-1.png)

1. Disconnect and reconnect to the instance for the creation to be effective.

1. Under **Message Center** > **Transactional message templates**, create a new email template based on the event type previously created.

    ![](../assets/accintegration-uc-2.png)

1. Design your template. In this example, we use personalization on the profile's first name and the order number. The first name is in the Adobe Experience Platform data source, and the order number is a field from our Journey Orchestration event. Make sure you use the correct field names in Campaign. 

    ![](../assets/accintegration-uc-3.png)

1. Publish your transactional template.

    ![](../assets/accintegration-uc-4.png)

1. Now you need to write the JSON payload corresponding the template. 

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* For the channel, you need to type "email".
* For the eventType, use the internal name of the event type created previously.
* The email address will be a variable, so you can type any label.
* Under ctx, the personalization fields are also variables.

**Journey Orchestration**

1. First, you need to create an event. Make sure you include the "purchaseOrderNumber" field.

    ![](../assets/accintegration-uc-5.png)

1. You then need to create, in Journey Orchestration, an action corresponding to your Campaign template. In the **Action type** drop-down, select **Adobe Campaign Classic**. 

    ![](../assets/accintegration-uc-6.png)

1. Click the **Payload field** and paste the JSON created previously.

    ![](../assets/accintegration-uc-7.png)

1. For the email address and the two personalization fields, change **Constant** to **Variable**.

    ![](../assets/accintegration-uc-8.png)

1. Now create a new journey and start with the event previously created.

    ![](../assets/accintegration-uc-9.png)

1. Add the action and map each field to the correct field in Journey Orchestration. 

    ![](../assets/accintegration-uc-10.png)

1. Add an **End** activity and test your journey.

    ![](../assets/accintegration-uc-11.png)

1. You can now publish your journey.
