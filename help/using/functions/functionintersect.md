---
product: adobe campaign
title: intersect
description: Learn about the function intersect
feature: Journeys
role: Developer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# intersect{#intersect}

Returns the common values in the two input lists. If one of the two lists is null, returns an empty list.

## Category

List

## Function syntax

`intersect(<parameters>)`

## Parameters

| Parameter | Type             |
|-----------|------------------|
| list 1 | list |
| list 2 | list |

## Signatures and returned types

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Returns a list.

## Examples

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Returns ["sports", "news"]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Returns common items between profile attributes and given list of categories.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Returns common items between profile attributes and given event field.
