---
product: adobe campaign
title: Capping API description
description: Learn more about the Capping API.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
---

# Work with the Capping API {#work}

The Capping API helps you to create, configure and monitor your capping configurations.

## Capping API description

| Method  | Path   | Description   |
|---|---|---|
| [!DNL POST] | list/endpointConfigs  | Get a list of the endpoint capping configurations |
| [!DNL POST] | /endpointConfigs  | Create an endpoint capping configuration |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy  | Deploy an endpoint capping configuration |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy  | Undeploy an endpoint capping configuration |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy  | Check if an endpoint capping configuration can be deployed or not |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Update an endpoint capping configuration |
| [!DNL GET] | /endpointConfigs/`{uid}` | Retrieve an endpoint capping configuration |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Delete an enpoint capping configuration |

When a configuration is created or updated, a check is automatically performed to guarantee the syntax and the integrity of the payload.
If some problems occur, the operation returns warning or errors to help you correct the configuration.

## Endpoint configuration

Here is the basic structure of an endpoint configuration:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Example:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Warning and errors 

When a **canDeploy** method is called, the process validates the configuration and returns the validation status identified by its Unique ID, either:

```

"ok" or "error"

```

The potential errors are:

* **ERR_ENDPOINTCONFIG_100**: capping config: missing or invalid url
* **ERR_ENDPOINTCONFIG_101**: capping config: malformed url
* **ERR_ENDPOINTCONFIG_102**: capping config: malformed url: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: missing HTTP methods
* **ERR_ENDPOINTCONFIG_104**: capping config: no call rating defined
* **ERR_ENDPOINTCONFIG_107**: capping config: invalid max calls count (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: invalid max calls count (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: can't create endpoint config: invalid payload
* **ERR_ENDPOINTCONFIG_112**: capping config: can't create endpoint config: expecting a JSON payload
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: invalid service name `<!--<given value>-->`: must be 'dataSource' or 'action'

The potential warning is:

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation by default

## Use-cases

In this section, you will find the five main use-cases that you can perform to manage your capping configuration in [!DNL Journey Orchestration].

To help you in your testing and configuration, a Postman collection is available [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

This Postman Collection has been set up to share the Postman Variable collection generated via __[Adobe I/O Console's Integrations](https://console.adobe.io/integrations) > Try it out > Download for Postman__, which generates a Postman Environment file with the selected integrations values.

Once downloaded and uploaded into Postman, you need to add three variables: `{JO_HOST}`,`{Base_Path}` and `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway URL
* `{BASE_PATH}` : entry point for the API. The value is '/authoring'
* `{SANDBOX_NAME}` : the header **x-sandbox-name** (for example, 'prod') corresponding to the sandbox name where the API operations will take place. See the [sandboxes overview](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) for more information. 

In the following section, you will find the Rest API calls ordered list to perform the use-case.

Use-Case n°1: **Creation and deployment of a new capping configuration**

1. list
1. create
1. candeploy
1. deploy

Use-Case n°2: **Update and deploy a capping configuration not deployed yet**

1. list
1. get
1. update
1. candeploy
1. deploy

Use-Case n°3: **Undeploy and delete a deployed capping configuration**

1. list
1. undeploy
1. delete

Use-Case n°4: **Delete a deployed capping configuration.**

In only one API call, you can undeploy and delete the configuration with the use of the forceDelete parameter.
1. list
1. delete, with forceDelete param

Use-Case n°5: **Update a capping configuration already deployed**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
