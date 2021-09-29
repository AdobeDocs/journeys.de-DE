---
product: adobe campaign
title: Schnittmenge
description: Erfahren Sie mehr über die Funktionsüberschneidung
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 17%

---

# Schnittmenge{#intersect}

Gibt die gebräuchlichen Werte in den beiden Eingabelisten zurück. Wenn eine der beiden Listen null ist, wird eine leere Liste zurückgegeben.

## Kategorie

Liste

## Funktionssyntax

`intersect(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste 1 | Liste |
| Liste 2 | Liste |

## Signaturen und zurückgegebene Typen

`intersect(listString,listString)`: listString 
`intersect(listDecimal,listDecimal)`: listDecimal 
`intersect(listInteger,listInteger)`: listInteger 
`intersect(listDateTime,listDateTime)`: listDateTime 
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly 
`intersect(listDateOnly,listDateOnly)`: listDateOnly 
`intersect(listDuration,listDuration)`: listDuration 
`intersect(listBoolean,listBoolean)`: listBoolean

Gibt eine Liste zurück.

## Beispiele

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Gibt [&quot;sports&quot;, &quot;news&quot;] zurück

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Gibt allgemeine Elemente zwischen Profilattributen und der angegebenen Liste von Kategorien zurück.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

Gibt allgemeine Elemente zwischen Profilattributen und dem angegebenen Ereignisfeld zurück.