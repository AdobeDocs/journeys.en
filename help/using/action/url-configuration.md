---
product: adobe campaign
title: URL configuration
description: Learn about URL configuration
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
---
# URL configuration {#concept_gbg_1f1_2gb}

When configuring a custom action, you need to define the following **[!UICONTROL URL Configuration]** parameters:

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

    >[!NOTE]
    >
    >We strongly recommend using HTTPS for security reasons. We don't allow the use of Adobe addresses that are not public and the use of IP addresses.

1. Select the call **[!UICONTROL Method]**: it can be either **[!UICONTROL POST]** or **[!UICONTROL PUT]**.
1. In the **[!UICONTROL Headers]** section, click **[!UICONTROL Add a header field]** to define a new key/value pair. They correspond to the HTTP headers of the request made to the external service. To delete key/value pairs, place your cursor on the **[!UICONTROL Headers]** field and click on the **[!UICONTROL Delete]** icon.

    **[!UICONTROL Content-Type]** and **[!UICONTROL Charset]** are set by default and cannot be deleted or overridden.

    >[!NOTE]
    >
    >Headers are validated according to the following [parsing rules](https://tools.ietf.org/html/rfc7230#section-3.2.4).
