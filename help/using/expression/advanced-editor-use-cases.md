---
product: adobe campaign
title: Using the advanced expression editor
description: Learn how to build advanced expressions
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
---
# Advanced expression examples

The Advanced expression editor can be used to create conditions to allow you to filter users in your journeys. These conditions enable you to target users on time, date, location, duration, or actions such as purchase or abandonment of carts so that they can be retargeted in the journey.

>[!NOTE]
>
>Events starts with @, data sources with #.

## Building conditions on Experience Events

The advanced expression editor is mandatory to perform queries on time series such as a list of purchases or past clicks on messages. Such queries cannot be performed using the simple editor.

The experience events are retrieved from the Adobe Experience Platform as a collection in reverse chronological order, hence:

* first function will return the most recent event
* last function will return the oldest one.

For example, let's say you want to target customers with a cart abandonment in the last 7 days to send a message when the customer is getting near a store, with an offer on items he wanted that are in store.

**You need to build the following conditions:**

First of all, target customers who browsed the online store but did not finalize order in the last 7 days.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**This expression looks for all events for this user specified in the last 7 days:**

Then it selects all the addtocart events that did not transform into a completePurchase.

>[!NOTE]
>
>To insert fields in the expression quickly, double-click the field in the left panel of the editor.

The specified timestamp is acting as the date time value, the second is number of days.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

This expression returns a boolean.

**Now let's build an expression checking that the product is in stock**

* In Inventory, this expression looks for quantity field of a product and specify that it should be greater than 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* At the right, the necessary values are specified, here, we need to retrieve the location of the store, that is mapped from the location of the event "ArriveLumaStudio":

 `#{ArriveLumaStudio._acpevangelists1.location.location}`

* And specify SKU, using the function `first` to retrieve the most recent "addToCart" interaction:  

    ```json
        #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .first(
                        currentDataPackField
                        .productData
                        .productInteraction == "addToCart"
                        )
                        .SKU}
    ```

From there you can add another path in your journey for when the product is not in store and send notification with engagement offer. Configure messages accordingly and use personalization data to enhance the message target.

## Examples of string manipulations with the advanced expression editor

**In conditions**

This condition retrieve only the geofence events triggered in "Arlington":

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explanation: This is a strict string comparison (case sensitive), equivalent to a query in simple mode that uses `equal to` with `Is sensitive` checked.

The same query with `Is sensitive` unchecked will generate the following expression in advanced mode:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In actions**

The following expression allows you to define the CRM ID in an action personalization field:

```json
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         ))
```

Explanation: This example uses `substr` and `lastIndexOf` functions to remove curly braces that enclose the CRM ID passed with a mobile app launch event.

For more on how to use the advanced expression editor, watch [this video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
