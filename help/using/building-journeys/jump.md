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

The **Jump** action activity allows you to push individuals from one journey to another. This feature allows you to:

* simplify the design of very complex journeys by splitting it into several ones  
* build journeys based on common and reusable journey patterns

In the origin journey, simply add a **Jump** and select a target journey. When the individual enters the jump step, an internal event is sent to the target journey. The flow continues in the current journey.

In the target journey, the first event triggered internally by the jump will make the individual flow in the journey.

## Lifecycle

Let's say you have added a jump in a journey A to a journey B. Journey A is the **origin journey** and journey B, the **target journey**. 
Here are the different steps of the execution process:

**Journey A** is triggered from an external event:

1. Journey A receives an external event related to an individual.
1. The individual reaches the jump step. 
1. The individual is pushed to Journey B, and moves on to the next steps in Journey A, after the jump.

In **journey B**, the first event can be triggered externally (like a regular event) or internally, via a jump from journey A:

1. Journey B received an internal event from Journey A.
1. The first event of Journey B is triggered with the information coming from Journey A.
1. The individual starts flowing in Journey B.

## Important notes

* You can only jump to a journey that uses the same namespace as the origin journey.
* You cannot jump to a journey that starts with a **Segment qualification** event. 
* When the jump is executed, the latest version of the target journey is triggered.
* You can include as many jumps as you need in a journey. After a jump, you can add any activity needed.
* You can have as many jump levels as needed. For example, Journey A jumps to journey B, which jumps to journey C, and so on.
* The target journey can also include as many jumps as needed, except to the origin journey. Loop patterns are not supported. There is no way to link two or more journeys together which would create an infinite loop. The **Jump** activity configuration screen prevents you from doing this.
* As usual, a unique individual can only be present once in a same journey. As a result, if the individual pushed from the origin journey is already in the target journey, then the jump will not trigger the target journey. No error will be reported on the jump because this is a normal behavior.

## Configuring the jump

1. Design your origin journey.
1. At any step of the journey, add a **Jump** activity, from the **Action** category. 
1. Add a label and description.
1. Click inside the **Target journey** field. 
   The list displays all journey versions that are draft, live or in test mode. Journeys that use a different namespace or that start with a **Segment qualification** event are not available. Target journeys that would create a loop pattern are also filtered out.

   >[!NOTE]
   >
   >You can click the **Open target journey** icon, on the right side, to open the target journey in a new tab.

1. Select the target journey that you want to jump to.
   The **First event** field is prefilled with the name pf the target journey's first event. If your target journey includes multiple events, the jump is only allowed on the first event.
1. The **Action parameters** section displays all the fields of the target event. In the same way as for other types of actions, map each field with fields from the origin event or data source. This information will be passed to the target journey at runtime.

## Troubleshooting

The latest version of the target journey is always triggered at runtime. It might be different than the version you selected while defining your jump. 

At runtime or in test mode, errors will happen if:
* the target journey no longer exists
* the target journey in not in the correct status (Draft, Closed or Finished)
* if the first event of the target journey has changed and the mapping is broken