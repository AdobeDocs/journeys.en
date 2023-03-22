---
product: adobe campaign
title: Get started with journeys APIs
description: Learn more about journeys APIs
products: journeys
feature: Journeys
role: User
level: Intermediate
---
# Get started with journeys APIs

## About the Capping and Throttling APIs

When configuring a datasource or an action, you establish a connection to a system to either retrieve additional information to use in your journeys or send messages or API calls.

Journeys APIs support up to 5000 event per second but some external systems or API may not have an equivalent throughput. To prevent overloading these systems, you can use the [Capping](capping.md) and [Throttling](throttling.md) APIs to limit the the number of events sent per second.

Every time an API call is performed by journeys, it passes through the API engine. If the limit set in the API reached, the call is either rejected if you are using the Capping API, or queued and processed as soon as possible in the order they were received if you are using the Throttling API.

For external data sources, the maximum number of calls per second is limited to 15. If this limit is exceeded, any additional calls are either discarded or queued, depending on the API in use. It is possible to increase this limit for private external data sources by contacting Adobe to include the endpoint in the allowlist, but this is not an option for public external data sources.

For more information, refer to these section:
* [Best practices and guardails when integrating external systems](../about/external-systems.md),
* [Configure data sources](../datasource/about-data-sources.md).
* [Configure actions](../action/action.md)

## Setting up API access {#api}

To use these APIs with your [!DNL Journey Orchestration] instance, you need to use the AdobeI/O Console. [!DNL Journey Orchestration] API access is set up through the steps below. Each of these steps is detailed in the [Adobe I/O documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>To manage certificates in Adobe I/O, make sure you have <b>System administrator</b> rights on the organization or a [developer account](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Admin console.

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.
1. **Create a new integration to [!DNL Journey Orchestration] Service** in Adobe I/O and configure it. The product profile access is needed for [!DNL Journey Orchestration] and Adobe Experience Platform. Your credentials will then be generated (API Key, Client secret...).
1. **Create a JSON Web Token (JWT)** from the credentials previously generated and sign it with your private key. The JWT encodes all of the identity and security information that is needed by Adobe to verify your identity and grant you access to the API. This step is detailed in this [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Exchange your JWT for an Access Token** through a POST request or via the Developer Console Interface. This Access Token will have to be used in each header of your API requests.

To establish a secure service-to-service Adobe I/O API session, every request to an Adobe service must include in the Authorization header the information below.

```

curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'

```

* **&lt;ORGANIZATION&gt;**: This is your personal ORGANIZATION ID, one ORGANIZATION ID is provided by Adobe for each of your instances. To obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the <a href="https://www.adobe.io/authentication.html">Adobe I/O documentation</a>).

* **<ACCESS_TOKEN>**: Your personal access token, that was retrieved when exchanging your JWT through a POST request.

* **<API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.
