---
title: Collection management functions
description: Learn about data types in collection management functions
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Collection management functions {#collection-management-functions}

The expression language also introduces a set of functions to query collections.

These functions are explained below. In the following examples, let’s use the event payload containing a collection:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**The function "all(`<condition>`)"**

The **[!UICONTROL all]** function enables the definition of a filter on a given collection by using a boolean expression.

   ```
   <listExpression>.all(<condition>)
   ```

For example, among all the app users, you can get the ones using IOS 13 (boolean expression “app used == IOS 13"). The result of this function is the filtered list containing items matching the boolean expression (example: app user 1, app user 34, app user 432).

In a Data Source Condition activity you can check if the result of the **[!UICONTROL all]** function is null or not. You can also combine this **[!UICONTROL all]** function with other functions such as **[!UICONTROL count]**. For more information, see [Data Source Condition activity](../building-journeys/condition-activity.md#data_source_condition).

**Example 1:**

We want to check if a user has installed a specific version of an application. For this we get all the push notification tokens associated to mobile applications for which the version is 1.0. Then, we perform a condition with the **[!UICONTROL count]** function to check that the returned list of tokens contains at least one element.

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
   ```

The result is true.

**Example 2:**

Here we use the **[!UICONTROL count]** function to check if there are push notification tokens in the collection.

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
   ```

The result will be true.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

   >[!NOTE]
   >
   >When the filtering condition in the **all()** function is empty, the filter will return all the elements in the list. **However, in order to count the number of elements of a collection, the all function is not required.**


   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
   ```

   The result of the expression is **3**.

**Example 3:**

Here we check if an individual has not received any communication within the last 24 hours. We filter the collection of experience events retrieved from the ExperiencePlatform datasource, using two expressions based on two elements of the collection. In particular, the timestamp of the event is compared to the dateTime returned by the **[!UICONTROL nowWithDelta]** function.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

The result will be true if there is no experience event matching the two conditions.

**Example 4:**

Here we want to check if an individual has launched at least once an application in the last 7 days, in order for instance to trigger a push notification inviting him to start a tutorial.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** is only available when manipulating event collections and **currentDataPackField** 
>when manipulating data source collections. When processing collections with **[!UICONTROL all]**, **[!UICONTROL first]** and **[!UICONTROL last]**, we
>loop on each element of the collection one by one. **[!UICONTROL currentEventField]** and **currentDataPackField**
>correspond to the element being looped.

**The functions "first(`<condition>`)" and "last(`<condition>`)"**

The **[!UICONTROL first]** and **[!UICONTROL last]** functions also enable the definition of a filter on the collection while returning the first/last element of the list that meets the filter.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Example 1:** 

This expression returns the first push notification token associated to mobile applications for which the version is 1.0.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
   ```

The result is "token_1".

**Example 2:** 

This expression returns the last push notification token associated to mobile applications for which the version is 1.0.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
   ```

   The result is "token_2".

   >[!NOTE]
   >
   >The experience events are retrieved from the Adobe Experience Platform as a collection in reverse chronological order, hence :
   >* **[!UICONTROL first]** function will return the most recent event
   >* **[!UICONTROL last]** function will return the oldest one.

**Example 3:**

We check whether the first (most recent) Adobe Analytics event with a non-zero value for DMA ID has a value equal to 602.

   ```
   #{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
   currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
   ```

**The function "at(`<index>`)"**

The **[!UICONTROL at]** function allows you to reference a specific element in a collection according to an index.
Index 0 is the first index of the collection. 

_`<listExpression>`.at(`<index>`)_

**Example:** 

This expression returns the second push notification token of the list.

   ```
   @{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
   ```

The result is "token_2".