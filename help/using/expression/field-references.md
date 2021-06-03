---
product: adobe campaign
title: Field references
description: Learn about field references in advanced expressions
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
---
# Field references {#concept_fkj_ll5_dgb}

A field reference can be attached to an event or a field group. The only meaningful information is the name of the field and its path. 

If you're using special characters in a field, you need to use double quotes or simple quotes. Here are the cases when quotes are needed:

* the field starts with numerical characters
* the field starts with the "-" character
* the field contains anything other than: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

For example if your field is _3h_: _#{OpenWeather.weatherData.rain.'3h'} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

In the expression, event fields are referenced with "@" and data source fields are referenced with "#".

A syntax color is used to visually distinguish events fields (green) from field groups (blue).

**Default values for field references**

A default value can be associated to a field name. The syntax is as follows:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>The type of the field and the default value must be the same. For example, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} will be invalid because the default value is an integer whereas the expected value should be a string.

Examples:

```
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

**Reference of a field within collections**

The elements defined within collections are referenced using the specific functions all, first and last. For more information, refer to [this page](../expression/collection-management-functions.md).

Example :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Reference of a field defined in a map**

In order to retrieve an element in a map, we use the entry function with a given key. For example, it is used when defining the key of an event, according to the selected namespace. See Selecting the namespace. For more information, see [this page](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In this expression, we are getting the entry for ‘Email’ key of the ‘IdentityMap’ field of an event. The ‘Email’ entry is a collection, from which we take the ‘id’ in the first element using ‘first()’. For more information, see [this page](../expression/collection-management-functions.md).

**Parameter values of a data source (data source dynamic values)**

If you select a field from an external data source requiring a parameter to be called, a new tab appears on the right to let you specify this parameter. See [this page](../expression/expressionadvanced.md).

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. A parameter can be any valid expression even from another data source that also includes another parameter.

>[!NOTE]
>
>When you define the parameter values in the expression, the tab on the right disappears.

Use the following syntax:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: exact name of the first parameter from the data source.
* **`<params-1-value>`**: the value of the first parameter. It can be any valid expression.

Example:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
