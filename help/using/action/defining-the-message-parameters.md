---
product: adobe campaign
title: Defining the message parameters
description: Learn how to define the message parameters
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
---
# Defining the message parameters {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

In the **[!UICONTROL Message parameters]** section, paste an example of the JSON payload to send to the external service.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Field names in the payload cannot contain a "." character.

You will be able to define the parameter type (e.g.: string, integer, etc.).

You will also have a choice between specifying if a parameter is a constant or a variable:

* Constant means that the value of the parameter is defined in the action configuration pane by a technical persona. The value will be always the same across journeys. It will not vary and the marketer won’t see it when using the custom action in the journey. It could be for example an ID the third-party system expects. In that case, the field on the right of the toggle constant/variable is the value passed.
* Variable means the value of the parameter will vary. The marketer using this custom action in a journey will be free to pass the value he wants or to specify where to retrieve the value for this parameter (e.g. from the event, from the Adobe Experience  Platform, etc.). In that case, the field on the right of the toggle constant/variable is the label the marketer will see in the journey to name this parameter.

![](../assets/customactionpayloadmessage2.png)
