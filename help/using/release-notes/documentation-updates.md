---
product: adobe campaign
title: Documentation Updates
description: Learn about documentation updates
feature: Journeys
role: User
level: Beginner
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
---
# Documentation Updates

This page lists all the documentation updates for [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## July 2022 {#july-2022}

* In the journey properties, the **Profile Time zone** option is now disabled by default. [Read more](../building-journeys/timezone-management.md#timezone-from-profiles)
* In the **Wait** activity, the **Fixed date** option is no longer available. [Read more](../building-journeys/wait-activity.md)

## June 2022 {#june-2022}

* New query examples have been added to this [page](../building-journeys/query-examples.md)

## March 2022 {#march-2022}

* Added an example on how to add an expression as a default value in the expression editor. [Read more](../expression/field-references.md#default-value)

## February 2022 {#feb-2022}

* The [replace](../functions/functionreplace.md#example_2) and [replaceAll](../functions/functionreplaceall.md#example) function documentation pages have been updated with additional information and examples regarding the target parameter.
* Best practices have been added to the [Operators](../expression/operators.md#important-notes) page.

## September 2021

* The following function pages have been updated: [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* The following functions have been added: [filter](../functions/functionfilter.md), [intersect](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* The dateOnly date type has been added in the expression editor documentation. [Read more](../expression/data-types.md)

* Added details on custom action cache duration. [Read more](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Added information on custom action default ports. [Read more](../action/url-configuration.md)

* Added commonly used examples to query Journey Step Events in Data Lake. [Read more](../building-journeys/query-examples.md)

## August 2021

* Updated the configuration procedure for custom actions with dynamic URL paths and dynamic headers. [Read more](../action/url-configuration.md)
* Added a section about accessibility features. [Read more](../about/user-interface.md#accessibility)
* Added a section about segment evaluation methods. [Read more](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## March 2021 {#march-2021}

* We have detailed the full procedure to create test profiles in Adobe Experience Platform. [Read more](../building-journeys/creating-test-profiles.md).

## January 2021 {#january-2021}

* Added best practices when triggering a journey at the same time as a profile creation. [Read more](../about/limitations.md#journeys-limitation-profile-creation).

## October 2020 {#october-2020}

* Information has been added on how to configure a timeout for an event. [Read more](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## September 2020 {#september-2020}

* The interface description section has been updated to reflect the new **All selector** menu. [Read more](../about/user-interface.md)
* Added a note on segment-based journeys' new versions that are not recurrent. 

## August 2020 {#august-2020}

* Added information on how to sort and choose the columns to display in the segments list. [Read more](../building-journeys/segment-qualification-events.md)
* Added information on how to copy a segment's name and ID after it has been selected. [Read more](../building-journeys/segment-qualification-events.md)
* Occurrences of Experience Platform have been harmonized across the different pages.

## July 2020 {#july-2020}

* Added a link to a new tutorial video on step events reporting to Adobe Experience Platform. [Read more](../building-journeys/sharing-overview.md)
* The events activities section has been reorganized into dedicated sub-sections for each type of events. [Read more](../building-journeys/event-activities.md)
* Added best practices to avoid overload with segment qualification. [Read more](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Added a note to explain how to make a journey continue after an error in an action or a condition. [Read more](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Added a new section on the Alpha features that are tested among a limited set of customers. 
* Added a new section on the integration with Intelligent Services. [Read more](../ai-services/ai-services-overview.md)
* Added a new section on the test profile creation. [Read more](../building-journeys/testing-the-journey.md)
* Added information on how to use the **[!UICONTROL SegmentQualification]** node in a journey condition or action. [Read more](../building-journeys/segment-qualification-events.md)
* A note has been added on Campaign transactional message and event publication. See [Working with Adobe Campaign](../action/working-with-adobe-campaign.md) and [Using Adobe Campaign actions](../building-journeys/using-adobe-campaign-actions.md).
* Information has been added on the checks that are performed when testing the Campaign Standard instance URL. [Read more](../action/working-with-adobe-campaign.md)
* Information has been added on reaction events compatibility with Campaign Standard instances hosted on AWS or Azure servers. [Read more](../building-journeys/reaction-events.md)
* A note has been added on the need to setup a capping rule when working with Campaign Standard transactional messaging. [Read more](../action/working-with-adobe-campaign.md)
* A note has been added on the generation of real events when triggering events using the test mode. [Read more](../building-journeys/testing-the-journey.md#firing_events)

## June 2020 {#june-2020}

* Added information on how to change the cache duration of the token for a custom authentication data source. [Read more](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Updated screenshots and text to reflect the renaming of the **[!UICONTROL Finished]** journey state which has been changed to **[!UICONTROL Closed (no entrance)]**.
* Added information on how the language is defined for the interface. [Read more](../about/user-interface.md)
* The list of statuses of an individual's journey has been moved to the [Test mode logs](../building-journeys/testing-the-journey.md#viewing_logs) section. 

## April 2020 {#april-2020}

* Added a new section on experience event schema definition to help users configure their first event. [Read more](../event/experience-event-schema.md)
* The home page for [!DNL Journey Orchestration] documentation has been updated with additional useful links. [Read more](../../journey-orchestration-home.md)

## March 2020 {#march-2020}

* Added parameter descriptions for _actionExecutionErrors_ and _fetchErrors_ in test logs section. [Read more](../building-journeys/testing-the-journey.md#viewing_logs)
* The limitations on custom actions used in a journey have been updated. You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [Read more](../action/about-custom-action-configuration.md)
* New contextual help entries have been added. The custom authentication payload pane (in actions and data sources) now includes a help icon that links to this [section](../datasource/external-data-sources.md#section_wjp_nl5_nhb). 
* Closed journeys can now be stopped. [Read more](../building-journeys/using-the-journey-designer.md)
* The interface description section has been reorganized. [Read more](../about/user-interface.md)
* The triggering of multiple events has been added to the Test mode section [Read more](../building-journeys/testing-the-journey.md#firing_events)
* The Test mode section has been updated regarding the new **[!UICONTROL Wait time in test]** parameter. [Read more](../building-journeys/testing-the-journey.md)
* The Test log section has been updated with external call error codes and responses. [Read more](../building-journeys/testing-the-journey.md#viewing_logs)
* Timezone management is now centralized in the journey properties panel. Read more [here](../building-journeys/changing-properties.md#timezone) and [here](../building-journeys/timezone-management.md)
* The Journey designer section has been updated to reflect recent enhancements. [Read more](../building-journeys/using-the-journey-designer.md)
* The interface description has been updated with information on contextual help. [Read more](../about/user-interface.md#section_ksq_zr1_ffb)
* When browsing **XDM fields**, the friendly name is now displayed. Related sections have been updated. [Read more](../about/user-interface.md#friendly-names-display)

## February 2020 {#february-2020}

* The shortcut section has been updated. The **C** keyboard shortcut allows you to create a new item in all list screens. [Read more](../about/user-interface.md#section_ksq_zr1_ffb)
* The [data source](../datasource/about-data-sources.md) and [action](../action/action.md) overview pages have been improved.

## January 2020 {#january-2020}

* Fetching limitations have been added for [experience events](../datasource/adobe-experience-platform-data-source.md) and [segments](../functions/functioninsegment.md).
<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## December 2019 {#december-2019}

* All screenshots have been updated to reflect interface changes.
* The test mode section has been updated. [Read more](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* Stopped journeys can now be deleted. Related documentation pages have been updated.
* Two colors are now displayed when issues are detected in a journey. Red for errors and orange for warnings. [Read more](../about/troubleshooting.md)
* The advanced expression editor section has been updated. [Read more](../expression/expressionadvanced.md).
* [Conditional instruction](../expression/conditional-instruction.md) and [Collection management](../expression/collection-management-functions.md) sections have been moved and updated.
* The [functions](../expression/functions.md) section has been updated with new examples.
* The [toDateTime function](../functions/functiontodatetime.md) documentation has been updated to reflect timezone syntax changes.
