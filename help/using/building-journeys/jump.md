---
title: Jumping from one journey to another
description: Jumping from one journey to another
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
---

# Jumping from one journey to another {#jump}

The **Jump** action activity allows you to push indivividuals from one journey to another. This is especially useful if your journey is complex and includes many paths and activities. Using a jump allows you to simplify your journey by splitting it into several ones. 

In the current journey, simply add a **Jump** and select a target journey. When the individual enters the jump step, an internal event is sent to trigger the destination journey. The flow continues in the current journey.

## Lifecycle

Let's say you have added a jump in a journey A to a journey B. Here are the different steps of the execution process:

Journey A:
1. Journey A receives an event related to an individual.
1. The individual reaches the jump step. 
1. The individual is pushed to Journey B, and moves on to the next steps in Journey A, after the jump.

Journey B:
Journey B can be triggered two way, via an exernal event, or via an internal event pushed from Journey A:
1. Journey B received an internal event from Journey A.
1. The first event of Journey B is triggered with the information coming from Journey A.
1. The individual starts flowing in Journey B.

## Important notes

* You can only jump to a journey has uses the same namespace as the origin journey.
* You cannot jump to a journey that starts with a **Segment qualification** event. 
* When the jump is executed, the latest version of the target journey is triggered.
* You can include as many jumps as you need in a journey. After a jump, you can add any activity needed.
* The target journey can also include as many jumps as needed, except to the origin journey. Loop patterns are not supported. There is no way to link two or more journeys together to create an infinite loop. The **Jump** activity configuration screen prevents you from doing this.  

## Configuring the jump

1. Design your orgin journey.
1. At any step of the journey, add a **Jump** activity, from the **Action** category. 
1. Add a label and description.
1. Click inside the **Target journey** field. 
   The list displays all journey versions that are draft, live or in test mode. Journeys that use a different namespace or that start with a **Segment qualification** event are not available. 

   >[!NOTE]
   >
   >You can click the **Open target journey** icon, on the right side, to open the target journey in a new tab.

1. Select the target journey that you want to jump to.
   The **First event** field is prefilled with the name pf the target journey's first event. If your target journey includes multiple events, the jump is only allowed on the first event.
1. The **Action parameters** section displays all the fields of the target event. In the same way as for other types of actions, map each field with fields from the origin event or data source. This information will be passed to the target journey at runtime.

## Troubeleshooting

The latest version of the target journey is always triggered at runtime. It might be different than the version you selected while defining your jump. 

target journey no ongers exsits, it is not in correct status, if we change the first event. 

At runtime or in test mode, target journey of latest version is in draft, and error will be displayed. 

