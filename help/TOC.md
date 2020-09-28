---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Guide
index: yes
---

# [!DNL Journey Orchestration] Guide {#using}

+ [Product documentation](journey-orchestration-home.md)
+ What's new {#release-notes}
  + [Release Notes](using/release-notes/release-notes.md)
  + [Documentation Updates](using/release-notes/documentation-updates.md)
+ Starting with [!DNL Journey Orchestration] {#starting-with-journeys}
  + [About [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
  + [Get started](using/about/get-started.md)
  + [User interface](using/about/user-interface.md)
  + [Access management](using/about/access-management.md)
  + [Troubleshooting](using/about/troubleshooting.md)
+ Configuring an event {#events-journeys}
  + [About events](using/event/about-events.md)
  + [About ExperienceEvent Schemas](using/event/experience-event-schema.md)
  + [Defining the payload fields](using/event/defining-the-payload-fields.md)
  + [Selecting the namespace](using/event/selecting-the-namespace.md)
  + [Defining the event key](using/event/defining-the-event-key.md)
  + [Adding a condition](using/event/adding-a-condition.md)
  + [Previewing the payload](using/event/previewing-the-payload.md)
  + [Additional steps to send events](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configuring a data source {#data-source-journeys}
  + [About data sources](using/datasource/about-data-sources.md)
  + [Field groups](using/datasource/field-groups.md)
  + [Adobe Experience Platform data source](using/datasource/adobe-experience-platform-data-source.md)
  + [External data sources](using/datasource/external-data-sources.md)
+ Configuring an action {#action-journeys}
  + [About actions](using/action/action.md)
  + [Working with Adobe Campaign](using/action/working-with-adobe-campaign.md)
  + Using a third-party system {#action-third-party}
    + [About custom action configuration](using/action/about-custom-action-configuration.md)
    + [Custom action limitations](using/action/custom-action-limitations.md)
    + [URL configuration](using/action/url-configuration.md)
    + [Defining the message parameters](using/action/defining-the-message-parameters.md)
+ Using Plaform segments {#configuring-segment}
  + [About Plaform segments](using/segment/about-segments.md)
  + [Creating a segment](using/segment/creating-a-segment.md)
  + [Using segments in conditions](using/segment/using-a-segment.md)
+ Building a journey {#building-journeys}
  + About journey building {#about-journey-building}
    + [Creating a journey](using/building-journeys/journey.md)
    + [Using the journey designer](using/building-journeys/using-the-journey-designer.md)
    + [Changing properties](using/building-journeys/changing-properties.md)
    + [Journey versions](using/building-journeys/journey-versions.md)
    + [Terminating a journey](using/building-journeys/terminating-a-journey.md)
    + [Time zone management](using/building-journeys/timezone-management.md)
  + Activities {#about-journey-building}
    + Events activities {#events-activities}
      + [About events activities](using/building-journeys/event-activities.md)
      + [General events](using/building-journeys/general-events.md)
      + [Reaction events](using/building-journeys/reaction-events.md)
      + [Segment qualification events](using/building-journeys/segment-qualification-events.md)
    + Orchestration activities {#orchestration-activities}
      + [About orchestration activities](using/building-journeys/about-orchestration-activities.md)
      + [Condition activity](using/building-journeys/condition-activity.md)
      + [End activity](using/building-journeys/end-activity.md)
      + [Wait activity](using/building-journeys/wait-activity.md)
    + Action activities {#action-activities}
      + [About action activities](using/building-journeys/about-action-activities.md)
      + [Using Adobe Campaign actions](using/building-journeys/using-adobe-campaign-actions.md)
      + [Using custom actions](using/building-journeys/using-custom-actions.md)
  + [Testing the journey](using/building-journeys/testing-the-journey.md)
  + [Publishing the journey](using/building-journeys/publishing-the-journey.md)
  + Sharing journey steps with Adobe Experience Platform {#sharing-journey-steps}
      + [Journey step sharing overview](using/building-journeys/sharing-overview.md)
      + [journeySteps events common fields](using/building-journeys/sharing-common-fields.md)
      + [journeyStep events action execution fields](using/building-journeys/sharing-execution-fields.md)
      + [journeyStep events data fetch fields](using/building-journeys/sharing-fetch-fields.md)
      + [journeyStep event identity fields](using/building-journeys/sharing-identity-fields.md)
      + [journey fields](using/building-journeys/sharing-journey-fields.md)
+ Using the advanced expression editor {#building-advanced-conditions-journeys}
  + [About the advanced expression editor](using/expression/expressionadvanced.md)
  + Syntax {#syntax}
      + [Generalities](using/expression/generalities.md)
      + [Conditional instruction](using/expression/conditional-instruction.md)
      + [Data types](using/expression/data-types.md)
      + [Field references](using/expression/field-references.md)
      + [Collection management functions](using/expression/collection-management-functions.md)
      + [Operators](using/expression/operators.md)
      + [Examples](using/expression/advanced-editor-use-cases.md)
  + Functions {#main-functions-journey}
    + [Main Functions](using/expression/functions.md)
    + Adobe Experience Platform {#adobe-experience-platform}
      + [inSegment](using/functions/functioninsegment.md)
    + Aggregation {#aggregation}
      + [avg](using/functions/functionavg.md)
      + [count](using/functions/functioncount.md)
      + [countOnlyNull](using/functions/functioncountonlynull.md)
      + [countWithNull](using/functions/functioncountwithnull.md)
      + [distinctCount](using/functions/functiondistinctcount.md)
      + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
      + [max](using/functions/functionmax.md)
      + [min](using/functions/functionmin.md)
      + [sum](using/functions/functionsum.md)
    + Conversion {#conversion}
      + [toBool](using/functions/functiontobool.md)
      + [toDateTime](using/functions/functiontodatetime.md)
      + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
      + [toDecimal](using/functions/functiontodecimal.md)
      + [toDuration](using/functions/functiontoduration.md)
      + [toInteger](using/functions/functiontointeger.md)
      + [toString](using/functions/functiontostring.md)
    + Date {#date}
      + [currentTime​InMillis](using/functions/functioncurrenttimeinmillis.md)
      + [inLastDays](using/functions/functioninlastdays.md)
      + [inLastHours](using/functions/functioninlasthours.md)
      + [inLastMonths](using/functions/functioninlastmonths.md)
      + [inLastYears](using/functions/functioninlastyears.md)
      + [inNextDays](using/functions/functioninnextdays.md)
      + [inNextHours](using/functions/functioninnexthours.md)
      + [inNextMonths](using/functions/functioninnextmonths.md)
      + [inNextYears](using/functions/functioninnextyears.md)
      + [now](using/functions/functionnow.md)
      + [nowWithDelta](using/functions/functionnowwithdelta.md)
      + [setHours](using/functions/functionsethours.md)
      + [setDays](using/functions/functionsetdays.md)
    + List {#list}
      + [distinct](using/functions/functiondistinct.md)
      + [distinctWithNull](using/functions/functiondistinctwithnull.md)
      + [in](using/functions/functionin.md)
      + [listSize](using/functions/functionlistsize.md)
      + [serializeList](using/functions/functionserializelist.md)
      + [sort](using/functions/functionsort.md)
    + Math {#math}
      + [random](using/functions/functionrandom.md)
      + [round](using/functions/functionround.md)
    + String {#string}
      + [concat](using/functions/functionconcat.md)
      + [contain](using/functions/functioncontain.md)
      + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
      + [endWith](using/functions/functionendwith.md)
      + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
      + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
      + [indexOf](using/functions/functionindexof.md)
      + [isEmpty](using/functions/functionisempty.md)
      + [isNotEmpty](using/functions/functionisnotempty.md)
      + [lastIndexOf](using/functions/functionlastindexof.md)
      + [length](using/functions/functionlength.md)
      + [lower](using/functions/functionlower.md)
      + [matchRegExp](using/functions/functionmatchregexp.md)
      + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
      + [replace](using/functions/functionreplace.md)
      + [replaceAll](using/functions/functionreplaceall.md)
      + [startWith](using/functions/functionstartwith.md)
      + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
      + [substr](using/functions/functionsubstr.md)
      + [trim](using/functions/functiontrim.md)
      + [upper](using/functions/functionupper.md)
      + [uuid](using/functions/functionuuid.md)
+ Building your reports{#journey-reports}
  + [About journey reports](using/reporting/about-journey-reports.md)
  + [Creating your journey reports](using/reporting/creating-your-journey-reports.md)
  + [Metrics and dimensions](using/reporting/metrics-and-dimensions.md)
+ Integrating with Intelligent Services{#use-case-advanced}
    + [About AI integration](using/ai-services/ai-services-overview.md)
    + [Leveraging Customer AI](using/ai-services/leveraging-customer-ai.md)
+ Use cases{#use-cases-journeys}
  + Simple use case{#use-case-simple}
    + [About the simple use case](using/usecase/about-the-simple-use-case.md)
    + [Configuring the event](using/usecase/configuring-the-event.md)
    + [Configuring the data source](using/usecase/configuring-the-data-source.md)
    + [Building the journey](using/usecase/simple-uc-building-the-journey.md)
  + Advanced use case{#use-case-advanced}
    + [About the advanced use case](using/usecase/about-the-advanced-use-case.md)
    + [Configuring the events](using/usecase/configuring-the-events.md)
    + [Configuring the data sources](using/usecase/configuring-the-data-sources.md)
    + [Building the journey](using/usecase/building-the-journey.md)
+ Working with APIs{#working-with-apis}
  + [Capping APIs](using/api/capping.md)
+ Alpha features {#alpha}
  + [Alpha features overview](using/alpha/alpha-overview.md)
  + [User interface](using/alpha/alpha-interface.md)
  + [Read Segment activity](using/alpha/alpha-segment-trigger.md)
  + [Rule-based events](using/alpha/alpha-events.md)
  