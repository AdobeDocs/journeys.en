---
product: adobe campaign
title: Using custom actions
description: Learn about action activities
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
---
# Using custom actions {#section_f2c_hbg_nhb}

When adding a custom action to a journey, you must specify the value of dynamic header fields. Dynamic header fields are HTTP header fields whose value is configured as a variable. [Learn more](../action/about-custom-action-configuration.md).

Follow these steps:

1. Select the custom action in the journey.
1. In the configuration pane, click the pencil icon next to the header field in the **[!UICONTROL URL Configuration]** section.
1. Select a field and click **[!UICONTROL OK]**.

By default, in the activity configuration pane, the **[!UICONTROL URL Configuration]** section shows only dynamic header fields. To view all the parameters, click the **Show read-only fields** icon.

>[!NOTE]
>
>You cannot pass a collection in custom action parameters. If the custom action expects collections, it will not work. Also note that the parameters have an expected format (example: string, decimal, etc.). You must be careful to respect these expected formats.

In the **[!UICONTROL Action parameters]** section, you'll see the message parameters defined as _"Variable"_. For these parameters, you can define where to get this information (example: events, data sources), pass values manually or use the advanced expression editor for advanced use cases. Advanced uses cases can be data manipulation and other function usage. See [this page](../expression/expressionadvanced.md).

**Related topics**

[About custom action configuration](../action/about-custom-action-configuration.md)