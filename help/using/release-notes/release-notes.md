---
title: Release Notes
description: Learn about release notes
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
---

# Release Notes {#release-notes}

This page lists all the new features and improvements for Journey Orchestration.
You can also consult the [Documentation Updates](../release-notes/documentation-updates.md). 

## August 2020 Release {#august-release}

### GA updates{#august-ga-update}

The payload of Segment Qualification events now contains the following context information, which you can use in conditions and actions: the behavior (entrance, exit), the timestamp of qualification and the segment id. [Read more](../building-journeys/segment-qualification-events.md)

### Alpha updates{#august-alpha-update}

To discover the scope of the Alpha, refer to this [section](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Segment Trigger activity</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following improvements have been made to the Segment Trigger activity:
</p>
<ul>
<li><p>The activity's name has been changed to "Read Segment". </p>
</li>
<li><p>The configuration of the journey scheduler has been removed from the activity’s properties. It is now accessible directly from the Journey's properties, in a dedicated section that will display if a Read Segment activity has been dropped into the canvas. </p>
</li>
<li><p>You can now test the journey on a unitary profile and track its progress in the journey using the visual flow.</p>
</li>
</ul>
<p>For more information, refer to the <a href="../alpha/alpha-segment-trigger.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Rule-based events</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following improvements have been made to rule-based events:
</p>
<ul>
<li><p>You can now leverage all of the Adobe Analytics behavioral event data that you are already capturing and streaming into the Platform in order to trigger journeys and automate experiences for your customers. <a href="../alpha/alpha-events.md#analytics-data">Read more</a></p>
</li>
<li><p>When triggering a rule-based event in test mode, you can now directly view the event ID condition. Also, a tooltip has been added next to each field that is part of the rule evaluation. <a href="../alpha/alpha-events.md#configuring-rule-based">Read more</a></p>
</li>
<li><p>The rule-based event definition screen has been reorganized for an improved experience. <a href="../alpha/alpha-events.md#test-rule-based">Read more</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha Release - July 2020 {#alpha-release---july-2020}

The Alpha program offers features that are currently tested among a limited set of customers. This allows us to improve our product based on the feedback received. These features are not available to all Journey Orchestration customers.

These features are described in a dedicated [section](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Enhanced user interface</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Navigation within Journey Orchestration menus has been enhanced, in order to provide a consistent interface with Adobe Experience Platform:
</p>
<ul>
<li><p>Menus moved from the top to the left-hand side of the interface. </p>
</li>
<li><p>Grouping of admin functionalities into a single dashboard.</p>
</li>
</ul>
<p>For more information, refer to the <a href="../alpha/alpha-interface.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Segment Trigger activity</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Segment Trigger activity allows you to make all individuals belonging to an Adobe Experience Platform segment enter a journey. Entrance into a journey can be executed either once, or on a regular basis. <a href="../alpha/alpha-segment-trigger.md">Read more</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Rule-based events</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>We have simplified the way you set up Experience events. We're introducing a new method that does not require the use of an eventID. When you set up your event in Journey Orchestration, you can now define a rule-based event. <a href="../alpha/alpha-events.md">Read more</a>
</p>
</td>
</tr>
</tbody>
</table>


## Q2 Release - June 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform integration enhancements</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following Adobe Experience Platform integration enhancements have been made:</p>
<ul>
<li><p>A new activity allows the listening of Adobe Experience Platform segment entrances/exits to make people enter or move forward in a journey. <a href="../building-journeys/segment-qualification-events.md">Read more</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Adobe Experience Platform segments can now be created and edited without leaving the Journey Orchestration interface, thanks to a new <strong>Segments</strong> tab.<a href="../segment/about-segments.md">Read more</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>In the simple expression editor, Adobe Experience Platform segments are now directly listed in the navigation tree to allow easy setup of conditions such as "does this person belong to segment A?".<a href="../segment/using-a-segment.md">Read more</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration is now automatically passing, to the Adobe Experience Platform, the steps executed in journeys. This includes potential errors encountered. This information can be used for achieving reporting and troubleshooting by executing queries on the Journey Step events for a particular journey or for all journeys. <a href="../building-journeys/sharing-overview.md">Read more</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration can now be connected to production and non-production Adobe Experience Platform sandboxes. Note that sandboxes is a beta feature. <a href="../about/access-management.md#sandboxes">Read more</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey designer and test mode enhancements</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following enhancements have been made to the journey designer and the test mode:</p>
<ul>
<li><p>You can now copy paste activities from one journey to another, selecting 1 or N journey activities. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Read more</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>After firing an event to make a test profile enter a journey, you can now see its progress along the journey thanks to a colored visual flow. In case of error in the journey, details of errors are also displayed. <a href="../building-journeys/testing-the-journey.md#firing_events">Read more</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>The <strong>Finished</strong> journey state has been renamed <strong>Closed (no entrance)</strong> to better reflect what this state means.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Other improvements**

To avoid sending too many API calls to third-party systems, we're introducing a new public API to setup "capping" rules. Capping rules allow the definition of a maximum number of calls to an API endpoint per milliseconds. [Read more](../api/capping.md)

Access control now allows more granularity in user access management. Effective availability: June, 30 2020. [Read more](../about/access-management.md#create-product-profile)

Journey Orchestration is now available in APAC (Australian data center). Effective availability: June, 30 2020

The Journey Orchestration interface is available in Japanese.

## Q1 Release - March 2020 {#q1-release---march-2020}

**What's new?**

<table>
<thead>
<tr>
<th><strong>Test mode enhancements</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following enhancements have been made to the test mode:</p>
<ul>
<li>When a journey uses several events, you can now trigger each of them individually from a drop-down list, in the <strong>Event configuration</strong> screen of the test mode. <a href="../building-journeys/testing-the-journey.md#firing_events">Read more</a></p></li>
<li><p>When one or more <strong>Wait</strong> activities are used in a journey, you can now define the time that each of these activities will last in test mode. The default time is 10 seconds. You can change this using the <strong>Wait time in test</strong> parameter, in the bottom left corner. <a href="../building-journeys/testing-the-journey.md">Read more</a></p><img src="../assets/rn-test.png"/>
</li>
<li>In the <strong>test logs</strong>, in case of an error when calling a third-party system (data source or action), the error code and error response are now displayed. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Read more</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Centralized timezone management</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Timezone management is now centralized in the journey properties panel. Two parameters have been added in the journey properties:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>The <strong>Timezone</strong> drop-down list allows you to select a specific timezone. By default, the browser's timezone is used. </li>
<li>The <strong>Profile Timezone</strong> checkbox allows you to use the Adobe Experience Platform Profile timezone of the person entering the journey, if available. If not, the timezone defined in the drop-down list is used. This feature is not compatible with journeys using events that do not have a namespace.</li>
</ul>
<p>For more information, refer to the <a href="../building-journeys/changing-properties.md#timezone">Changing properties</a> and <a href="../building-journeys/timezone-management.md">Timezone management</a> sections.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey designer enhancements</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>The journey <strong>palette</strong>, on the left side of the journey designer has been enhanced:</p>
<ul>
<li>A new icon, next to the <strong>Search</strong>  bar, allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. By default, unavailable items are hidden.</li>
<li>When using the <strong>Search</strong> field, the number of results for each canvas activity category is now displayed.</li>
<li>The navigation between the different activity categories has been improved.</li>
</ul>
<p>In the journey designer, you can now check you are accessing the latest version of the journey. This information is displayed next to the version number.</p>
<p>In the journey <strong>canvas</strong>, when two activities are disconnected, a warning message is now displayed.</p>
<img src="../assets/rn-canvas.png"/>
<p>For more information, refer to the <a href="../building-journeys/using-the-journey-designer.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Contextual Help</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A contextual help is now available across the different Journey Orchestration list screens (journeys, events, actions and data sources). This allows you to view a quick description of the current functionality and access related articles and videos.</p>
<p>To display the contextual help, click the <img src="../assets/icon-context.png"/> icon in the upper-right corner of the screen. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Other improvements**

* In addition to US, Journey Orchestration is now available in **EMEA**. The application and documentation are available in French and German.

* Experience League is now integrated into the product. This simplifies the access to related content and helps you get the most out of Experience Cloud. Direct access to Journey Orchestration documentation is available at the bottom of the Help tab. Additionally, click Help > Feedback to report issues or share your ideas with Adobe.

* The **C** keyboard shortcut, which allows you to create a new item, is now available in all list screens: journeys, data sources, actions and events. [Read more](../about/user-interface.md#section_ksq_zr1_ffb)

* You can now **delete** stopped journeys. Reports associated to these deleted journeys will not be available.

* When browsing through **Adobe Experience Platform fields** (XDM format), you will now see the display name in addition to the field name. This information is retrieved from the schema definition in the Experience Data Model. When available, the alternate display name appears. This user-friendly description, especially useful in the case of eVar fields, allows you identify your fields more easily. [Read more](../about/user-interface.md#friendly-names-display)

## GA Release - December 2019 {#ga-release---december-2019}

Journey Orchestration is now GA. 

Build real-time orchestration use cases leveraging contextual data stored in events or data sources.

Journey Orchestration allows real-time orchestration powered by contextual data from events, information from the Adobe Experience Platform, or data from third-party API services. The application determines in multistep flows called journeys the next best actions specific to the consumer, based on their profile and behaviors. This comprises both the optimal timing, as well as the type of action, such as sending the consumer a push notification via Adobe Campaign Standard transactional messaging capabilities (requires Adobe Campaign Standard) or the notification of a third-party system. These decisions are made based on rules and Sensei scores.

[Learn more](../action/working-with-adobe-campaign.md) on Journey Orchestration.

Additional resources:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
