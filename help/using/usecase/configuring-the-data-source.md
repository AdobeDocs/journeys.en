---
product: adobe campaign
title: Configuring the data source
description: Learn how to configure the data source for the journey simple use case
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
---
# Configuring the data source{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


In our use case, we want to use personalization data for our messages. We also need to check is the person is a woman. This information is stored in the Real-time Customer Profile database. The **technical user** needs to check that those fields are defined in the built-in Adobe Experience Platform data source.

For additional information on data source configuration, refer to [this page](../datasource/about-data-sources.md). 

1. In the menu pane, select **[!UICONTROL Admin]**. In the **[!UICONTROL Data sources]** section, click **[!UICONTROL Manage]**.
1. Select the build-in Adobe Experience Platform data source.

    ![](../assets/journey23.png)

1. In the field groups, check that the following fields are selected:

    * _person > name > firstName_
    * _person > name > lastName_
    * _person > gender_
    * _personalEmail > address_

1. Click **[!UICONTROL Save]**.

The data source is now configured and ready to be used in your journey.
