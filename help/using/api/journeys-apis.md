---
product: adobe campaign
title: Get started with journeys APIs
description: Learn more about journeys APIs
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
---
# Get started with journeys APIs

## About Capping and Throttling APIs

When configuring a datasource or an action, you establish a connection to a system to either retrieve additional information to use in your journeys or send messages or API calls.

Journeys APIs support up to 5000 event per second but some external systems or API may not have an equivalent throughput. To prevent overloading these systems, you can use the **Capping** and **Throttling** APIs to limit the the number of events sent per second.

Every time an API call is performed by journeys, it passes through the API engine. If the limit set in the API is reached, the call is either rejected if you are using the Capping API, or queued up to 6 hours and processed as soon as possible in the order they were received if you are using the Throttling API.

For example, let's say that you have defined a capping or throttling rule of 100 calls per second for your external system. Your system is called by a custom action in 10 different journeys. If one journey receives 200 calls per second, it will use the 100 slots available and discard or queue the 100 remaining slots. Since the maximum rate has exceeded, the other 9 journeys will not have any slot left. This granularity helps to protect the external system from over-loading and crashing. 

>[!IMPORTANT]
>
>**Capping rules** are configured at sandbox level, for a specific endpoint (the URL called) but global to all journeys of that sandbox.
>
>**Throttling rules** are configured on production sandboxes only, for a specific endpoint but global to all journeys across all sandboxes. You can have only one throttling configuration per organization.

For more information on how to work with these APIs, refer to these sections:

* [Capping API](capping.md)
* [Throttling API](throttling.md)

Both of the APIs are also described in a Swagger file available [here](https://adobedocs.github.io/JourneyAPI/docs/). 

## Data sources & custom actions capacity {#capacity}

For **external data sources**, the maximum number of calls per second is limited to 15. If this limit is exceeded, any additional calls are either discarded or queued depending on the API in use. It is possible to increase this limit for private external data sources by contacting Adobe to include the endpoint in the allowlist, but this is not an option for public external data sources. * [Learn how to configure data sources](../datasource/about-data-sources.md).

>[!NOTE]
>
>If a datasource uses a custom authentication with a different endpoint than the one used for the datasource, you need to contact Adobe to also include that endpoint in the allowlist.

For **custom actions**, you need to evaluate the capacity of your external API. For example, if Journey Optimizer sends 1000 calls per second and your system can only support 100 calls per second, you need to define a capping or throtlling configuration so that your system does not saturate. [Learn how to configure actions](../action/action.md)

## Setting up API access {#api}

To use these APIs with your [!DNL Journey Orchestration] instance, you need to use the AdobeI/O Console. [!DNL Journey Orchestration] API access is set up through the steps below. Each of these steps is detailed in the [Adobe I/O documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>To manage certificates in Adobe I/O, make sure you have <b>System administrator</b> rights on the organization or a [developer account](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Admin console.

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.
1. **Create a new integration to [!DNL Journey Orchestration] Service** in Adobe I/O and configure it. The product profile access is needed for [!DNL Journey Orchestration] and Adobe Experience Platform. Your credentials will then be generated (API Key, Client secret...).

>[!CAUTION]
>
>The JWT method to generate access tokens has been deprecated. All new integrations must be created using the [OAuth Server-to-Server authentication method](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe also recommends that you migrate your existing integrations to the OAuth method.
>
>Read the following important documentations: 
>[Migration guide for your applications from JWT to OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/), 
>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Advantages of using the OAuth Server-to-Server credentials method](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

To establish a secure service-to-service Adobe I/O API session, every request to an Adobe service must include in the Authorization header the information below.

```

curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'

```

* **<ORGANIZATION>**: This is your personal ORGANIZATION ID, one ORGANIZATION ID is provided by Adobe for each of your instances. To obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the [Adobe I/O documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)).

* **<ACCESS_TOKEN>**: Your personal access token

* **<API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.
