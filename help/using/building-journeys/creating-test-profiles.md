---
product: adobe campaign
title: Creating a test profile
description: Learn about test profile creation
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
---
# Create test profiles {#create-test-profiles}


>[!CAUTION]
>
>**Looking for Adobe Journey Optimizer**? Click [here](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} for Journey Optimizer documentation.
>
>
>_This documentation refers to legacy Journey Orchestration materials which has been replaced by Journey Optimizer. Please contact your account team if you have questions about your access to Journey Orchestration or Journey Optimizer._


Test profiles are required when using the test mode in a journey. To learn how to use the test mode, refer to [this section](../building-journeys/testing-the-journey.md).

There are different ways to create a test profile in Adobe Experience Platform. In this documentation, we focus on two methods: uploading a [csv file](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) and using [API calls](../building-journeys/creating-test-profiles.md#create-test-profiles-api). You can also upload a json file in a dataset, refer to the [Data Ingestion documentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

These import methods also allow you to update profile attributes. This way, you can turn an existing profile into a test profile. Simply use a similar file or API call and only include the "testProfile" field with the value "true".

Creating a test profile is similar to creating regular profiles in Adobe Experience Platform. For more information, refer to the [Real-time Customer Profile documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

## Prerequisites{#test-profile-prerequisites}

In order to be able to create profiles, you first need to create a schema and a dataset in Adobe Experience Platform.

First, you need to **create a schema**. Follow these steps:

1. In Adobe Experience Platform, click **[!UICONTROL Schemas]**, in the left menu.
    ![](../assets/test-profiles-0.png)
1. Click **[!UICONTROL Create schema]**, in the top right, then select a schema type, for example **[!UICONTROL XDM Individual Profile]**.
    ![](../assets/test-profiles-1.png)
1. Choose a name for your schema.
1. In the **[!UICONTROL Mixins]** section, click **[!UICONTROL Add]**. 
    ![](../assets/test-profiles-1-bis.png)
1. Select the appropriate mixins. Make sure you add the **[!UICONTROL Profile test details]** mixin. Click **[!UICONTROL Add mixin]**.
    ![](../assets/test-profiles-1-ter.png)
    The list of mixins is displayed on the schema overview screen.
    ![](../assets/test-profiles-2.png)
1. In the list of fields, click on the field that you want to define as the primary identity.
    ![](../assets/test-profiles-3.png)
1. In the **[!UICONTROL Field properties]** right panel, check the **[!UICONTROL Identity]** and **[!UICONTROL Primary Identity]** options and select a namespace. If you want the primary identity to be an email address, choose the **[!UICONTROL Email]** namespace. Click **[!UICONTROL Apply]**.
    ![](../assets/test-profiles-4.png)
1. Select the schema and enable the **[!UICONTROL Profile]** option in the **[!UICONTROL Schema properties]**.
    ![](../assets/test-profiles-5.png) 
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>For more information on schema creation, refer to the [XDM documentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Then you need to **create the dataset** in which the profiles will be imported. Follow these steps:

1. In Adobe Experience Platform, click **[!UICONTROL Datasets]**, in the left menu, then click **[!UICONTROL Create dataset]**.
    ![](../assets/test-profiles-6.png) 
1. Choose **[!UICONTROL Create dataset from schema]**.
    ![](../assets/test-profiles-7.png) 
1. Select the previously created schema then click **[!UICONTROL Next]**.
    ![](../assets/test-profiles-8.png) 
1. Choose a name then click **[!UICONTROL Finish]**.
    ![](../assets/test-profiles-9.png) 
1. Enable the **[!UICONTROL Profile]** option. 
    ![](../assets/test-profiles-10.png) 

>[!NOTE]
>
> For more information on dataset creation, refer to the [Catalog Service documentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Creating a test profile using a csv file{#create-test-profiles-csv}

In Adobe Experience Platform, you can create profiles by uploading a csv file containing the different profile fields into your dataset. This is the easiest method.

1. Create a simple csv file using a spreadsheet software.
1. Add one column for each needed field. Make sure you add the primary identity field ("personID" in our example above) and the "testProfile" field set to "true". 
    ![](../assets/test-profiles-11.png) 
1. Add one line per profile and fill in the values for each field. 
    ![](../assets/test-profiles-12.png) 
1. Save the spreadsheet as a csv file. Make sure commas are used as separators.
1. In Adobe Experience Platform, click **[!UICONTROL Workflows]**, in the left menu. 
    ![](../assets/test-profiles-14.png) 
1. Choose **[!UICONTROL Map CSV to XDM schema]**, then click **[!UICONTROL Launch]**.
    ![](../assets/test-profiles-16.png) 
1. Select the dataset you want to import the profiles into. Click **[!UICONTROL Next]**.
    ![](../assets/test-profiles-17.png) 
1. Click **[!UICONTROL Choose files]** and select your csv file. When the file is uploaded, click **[!UICONTROL Next]**.
    ![](../assets/test-profiles-18.png) 
1. Map the source csv fields to the schema fields, then click **[!UICONTROL Finish]**.
    ![](../assets/test-profiles-19.png) 
1. The data import begins. The status will move from **[!UICONTROL Processing]** to **[!UICONTROL Success]**. Click **[!UICONTROL Preview data set]**, in the top right.
    ![](../assets/test-profiles-20.png)
1. Check that the test profiles have been correctly added.
    ![](../assets/test-profiles-21.png)

Your test profiles are added and can now be used when testing a journey. Refer to [this section](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> For more information on csv imports, refer to the [Data Ingestion documentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Creating test profiles using API calls{#create-test-profiles-api}

You can also create test profiles via API calls. See this [page](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

You must use a Profile schema that contains the "Profile test details" mixin. The testProfile flag is part of this mixin.

When creating a profile, make sure you pass the value: testProfile = true.

Note that you can also update an existing profile to change its testProfile flag to "true".

Here is an example of an API call to create a test profile:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
