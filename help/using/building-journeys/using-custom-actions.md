---
title: Using custom actions
description: Learn about action activities
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Using custom actions {#section_f2c_hbg_nhb}

If you're using a custom action, you will see, in read-only, the **[!UICONTROL URL Configuration]** and **[!UICONTROL Authentication]** parameters defined in the action configuration screen (see [this page](../action/about-custom-action-configuration.md)).

>[!NOTE]
>
>You cannot pass a collection in custom action parameters. If the custom action expects collections, it will not work. Also note that the parameters have an expected format (example: string, decimal, etc.). You must be careful to respect these expected formats. 

In the **[!UICONTROL Action parameters]** section, you'll see the message parameters defined as _"Variable"_. For these parameters, you can define where to get this information (example: events, data sources), pass values manually or use the advanced expression editor for advanced use cases. Advanced uses cases can be data manipulation and other function usage. See [this page](../expression/expressionadvanced.md)
