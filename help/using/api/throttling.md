---
product: adobe campaign
title: Work with the Throttling API
description: Learn more about the Throttling API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
---
# Work with the Throttling API

The Throttling API helps you to create, configure and monitor your throttling configurations in order to limit the number of events sent per second.

>[!IMPORTANT]
>
>Only one configuration is currently allowed per organisation. A configuration must be defined on a production sandbox (given through x-sandbox-name in the headers).
>
>A configuration is applied at organization level.
>
>When the limit set in the API is reached, further events are queued for up to 6 hours. This value cannot be modified.

## Throttling API description {#description}

| Method  | Path   | Description   |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs  | Get a list of the throttling configurations |
| [!DNL POST] | /throttlingConfigs  | Create a throttling configuration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy  | Deploy a throttling configuration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy  | Undeploy a throttling configuration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy  | Check if a throttling configuration can be deployed or not |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Update a throttling configuration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Retrieve a throttling configuration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Delete a throttling configuration |

## Throttling configuration {#configuration}

Here is the structure of a throttling configuration. **name** and **description** attributes are optional.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Example:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Errors

When creating or updating a configuration, the process validates the given configuration and returns the validation status identified by its Unique ID, either:

```

"ok" or "error"

```

>[!IMPORTANT]
>
>The attributes **maxThroughput**, **urlPattern** and **methods** are mandatory.
>
>**maxThroughput** value must be in 200-5000 range.

When creating, deleting or deploying throttling configuration, the following errors can occur :

* **ERR_THROTTLING_CONFIG_100**: throttling config: `<mandatory attribute>` required
* **ERR_THROTTLING_CONFIG_101**: throttling config: maxThroughput is required and must be greater than or equal to 200 and less than or equal to 5000
* **ERR_THROTTLING_CONFIG_104**: throttling config: malformed url pattern
* **ERR_THROTTLING_CONFIG_105**: throttling config: wildcards not allowed in host part of the url pattern
* **ERR_THROTTLING_CONFIG_106**: throttling config: invalid payload
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, "Can't delete a deployed throttling config. Undeploy it before deleting it"
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, "Can't delete throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, "Can't deploy throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, "Can't undeploy throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_GET_ERROR: 1460**, "Can't get throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, "Can't update throttling config: runtime version is not active"
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, "Can't update throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, "Operation not allowed on throttling config: non prod sandbox"
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**,  "Can't create throttling config: unexpected error occurs"
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, "Can't create throttling config: only one config allowed per org"
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, "Can't deploy throttling config: already deployed"
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, "throttling config not found"
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, "Can't undeploy throttling config: not deployed yet"

**Errors examples**

When trying to create a config on non-prod sandbox:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

In case given sanbox does not exist:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

When trying to create another config:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Use-cases {#uc}

To help you in your testing and configuration, a Postman collection is available [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

This Postman Collection has been set up to share the Postman Variable collection generated via __[Adobe I/O Console's Integrations](https://console.adobe.io/integrations) > Try it out > Download for Postman__, which generates a Postman Environment file with the selected integrations values.

Once downloaded and uploaded into Postman, you need to add three variables: `{JO_HOST}`,`{BASE_PATH}` and `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway URL
* `{BASE_PATH}` : entry point for the API. The value is '/authoring'
* `{SANDBOX_NAME}` : the header **x-sandbox-name** (for example, 'prod') corresponding to the sandbox name where the API operations will take place. See the [sandboxes overview](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) for more information. 

In the following section, you will find the Rest API calls ordered list to perform the use-case.

Use-Case n°1: **Creation and deployment of a new throttling configuration**

1. list
1. create
1. candeploy
1. deploy

Use-Case n°2: **Update and deploy a throttling configuration not deployed yet**

1. list
1. get
1. update
1. candeploy
1. deploy

Use-Case n°3: **Undeploy and delete a deployed throttling configuration**

1. list
1. undeploy
1. delete

Use-Case n°4: **Delete a deployed throttling configuration**

In only one API call, you can undeploy and delete the configuration with the use of the forceDelete parameter.

1. list
1. delete, with forceDelete param

Use-Case n°5: **Update a throttling configuration already deployed**

>[!NOTE]
>
>It is not required to undeploy the configuration before updating

1. list
1. get
1. update

## Configuration life-cycle at runtime level {#config}

When a configuration is undeployed, it is marked as inactive at runtime level and pending events continue to be processed during 24 hours. It is then deleted in the runtime service.

After a configuration has been undeployed, it is possible to update and redeploy the configuration. This will create a new runtime configuration that will be considered in the upcoming actions execution. 

When updating a configuration already deployed, the new values are taken into account immediately. The underlying system resources are automatically adapted. This is optimal compared to undeploy then redeploy the configuration.

## Responses examples {#responses}

**Creation - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Update - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Read (after update) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Read (after deployment) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
