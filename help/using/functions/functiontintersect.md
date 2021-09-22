---
product: adobe campaign
title: intersect
description: Learn about the function intersect
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
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

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Returns ["sports,"news"]

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Returns common items between profile attributes and given list of categories.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{"myEvent.sport_interests"}
)
```

Returns common items between profile attributes and given event field.