---
title: Import export API description
description: Learn more about the import export API.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
---

# Working with Export-Import API

Export a journey version and all its related objects (journey, events, data sources, field groups, custom actions) with a single API call. The export resulting payload can be used to easily import the journey into another environment (instance or sandbox).
This feature allows you to manage your journeys across multiple instances or for multiple test environments workflows.


## Resources

The Journey Orchestration Export-Import API is described within a Swagger file available [here](https://adobedocs.github.io/JourneyAPI/docs/).

To use this API with your Journey Orchestration instance, you need to use the AdobeI/O Console. You can start by following this [Getting Started with Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) and then use the sections in this page.

To test and prepare your integration, a Postman collection is available [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json). 


## Export-Import flow

We recommend to follow these steps to export and import your journeys across environments:

1. Create and parameter a journey in your start environment. [More info here](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/about-journey-building/journey.html)
1. Check if the journey version has no error. [More info here](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Call **/list/journeys** API to retrieve the UID journey and the UID of your latest journey version. If needed, you can call **/journeys/`{uid}`/latest** to find the UID of your latest journey version.  
1. Call the **export** API with your start environment parameters (orgID and sandboxName).
1. Open the return payload, then check the following items:
   * If your exported journey contains **specific credentials**, you need to replace these credentials with those corresponding to the new environment.
   * If your exported journey contains **events** that point to an **XDM schema**, you need to manually update the schema ID reference with the schema ID of the new environment in the xdmEntity node if IDs values are different. This update needs to be done for each event. [More info here](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * If your journey contains email, sms or push actions, you may have to update the template name or the mobileApp name if the name in the target environment is different from the one in your start environment.
1. Call the **Import** API with your target environment parameters (orgID and sandboxName). Note that you can call the import API as many times as you want. The UUID and the name of each object contained in the journey are generated each time you call the import API.
1. Once the Journey is imported, you can publish it in the Journey Orchestration application. More info [here](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Authentification

### Setting up API access

Journey Orchestration API access is set up through the steps below. Each of these steps is detailed in the [Adobe I/O documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>To manage certificates in Adobe I/O, make sure you have <b>System administrator</b> rights on the organization or a [developer account](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Admin console.

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.
1. **Create a new integration to [!DNL Journey Orchestration] Service** in Adobe I/O and configure it. The product profile access is needed for Journey Orchestration and Adobe Experience Platform. Your credentials will then be generated (API Key, Client secret...).
1. **Create a JSON Web Token (JWT)** from the credentials previously generated and sign it with your private key. The JWT encodes all of the identity and security information that is needed by Adobe to verify your identity and grant you access to the API. This step is detailed in this [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Exchange your JWT for an Access Token** through a POST request or via the Developer Console Interface. This Access Token will have to be used in each header of your API requests.

To establish a secure service-to-service Adobe I/O API session, every request to an Adobe service must include in the Authorization header the information below.

```

curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'

```

* **&lt;ORGANIZATION&gt;**: This is your personal ORGANIZATION ID, one ORGANIZATION ID is provided by Adobe for each of your instances :

    * &lt;ORGANIZATION&gt; : your production instance

    To obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the [Adobe I/O documentation](https://www.adobe.io/authentication.html)).

* **<ACCESS_TOKEN>**: Your personal access token, that was retrieved when exchanging your JWT through a POST request.

* **<API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.



## Export-Import API description

This API lets you export a journey version identified by its UID and all the related objects (journey, events, data sources, field groups, custom actions) by its uid.
The resulting payload can be used to import the journey version in another environment (sandbox or instance).

| Method | Path | Description |
|---|---|---|
| `[POST]` | /journeyVersions/import  | Import a journey version content resulting from a journey version export |
| `[GET]` | /journeyVersions/`{uid}`/export  | Export a journey version |
| `[GET]` | /journeys/`{uid}`/latest  | Get the latest journey version for a journey |
| `[POST]` | /list/journeys  | List the metadata of the journeys and their journey versions |


### Export characteristics and guardrails

* The journey must be valid before export.

* The credentials are not exported and a placeholder (i.e INSERT_SECRET_HERE) is inserted in the response payload.
  After the export call, you must manually insert the new credentials (corresponding to the target environment) before importing the payload in the target environment.
  
* The following objects are exported but they will never be imported in the target environment. These are system resources automatically managed by Journey Orchestration. You don't need to replace "INSERT_SECRET_HERE".
   * **DataProviders**:  "Adobe Campaign Standard Data Provider" (acsDataProvider) and "Experience Platform" (acppsDataProvider)
   * **Field groups** (dataEntities): "ProfileFieldGroup" (acppsDataPack)



### Import characteristics

* During the import, the journey objects are created with new UID and a new name to ensure uniqueness in the target environment (instance or sandbox).

* If the import payload contains secret placeholders, an error is thrown. You must replace the credential information before the POST call to import the journey.

## Warning and errors 

The potential errors are:

* At **export time**, if the journey version is not valid : error 500

* At **import time**, if the payload is not valid after modifications or if credentials are not well defined in the payload : error 400

* After the import step, if the XDM Schema ID for your events is not valid in the target environment, an error appears in the Journey Orchestration application. It will not be possible to publish the journey in such case.