---
title: About events activities
description: Learn about events activities
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# About events activities {#concept_rws_1rt_52b}

The events configured by the technical user (see [](../event/about-events.md)) are all displayed in the first category of the palette, on the left side of the screen.

 ![](../assets/journey43.png)

Always start your journey by drag and dropping an event activity. You can also double-click on it.

 ![](../assets/journey44.png)

When you click on the event activity in the canvas, the activity configuration pane is displayed. By default, when you use the same event several times, an incremented number is added to the event name in the canvas. In addition, you can use the **[!UICONTROL Label]** field to add a suffix to the event name that will appear under your activity in the canvas. This is useful to identify your events in the canvas, especially if you use the same event several times. It will also make debugging easier in case of errors and it will make reports easier to read.

 ![](../assets/journey33.png)

## Advanced usage: events with a wait in parallel{#section_vxv_h25_pgb}

**How can you listen to an event only during a certain time?**

An event activity positioned in the journey listens to events indefinitely. To listen to an event only during a certain time, you must add a wait activity parallel to the event path. The journey will then listen to the event during the time specified in the wait activity. If an event is received during that period, the person will flow in the event path. If not, the customer will flow into the wait path.

For example, you sent a welcome first push to a customer and you want to send a meal discount push only if the customer enters the restaurant within the next 6 hours. To do this, you will create a second path (parallel to the restaurant event one) with a 6-hour wait activity. If the restaurant event is received less than 6 hours after the welcome push, the meal discount push activity is sent. If no restaurant event is received within the next 6 hours, the person flows through the wait path.

 ![](../assets/journeyuc2_31.png)
