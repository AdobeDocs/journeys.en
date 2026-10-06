---
product: adobe campaign
title: Event data cycle
description: Learn about event data cycle
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Data cycle {#section_r1f_xqt_pgb}

Events are POST API calls. Events are sent to the Adobe Experience Platform through Streaming Ingestion APIs. The URL destination of events sent through transactional messaging APIs is called an “inlet”. The payload of events follows XDM formatting. 

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). There are two modes for the streaming ingestion, authenticated and unauthenticated. For details on Streaming Ingestion APIs, refer to [this link](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

After arriving through Streaming Ingestion APIs, events flow into an internal service called Pipeline and then in the Adobe Experience Platform. If the event schema has the Real-time Customer Profile Service flag enabled and a dataset ID that also has the Real-time Customer Profile flag, it flows into the Real-time Customer Profile Service.

For system-generated events, the Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. For rule-based events, the system identifies the event using the eventID condition. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.
