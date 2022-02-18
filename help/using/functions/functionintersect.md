---
product: adobe campaign
title: intersect
description: Erfahren Sie mehr über die Funktion „function“
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Schnittmenge{#intersect}

Gibt die gemeinsamen Werte in den beiden Eingabe-Listen zurück. Wenn eine der beiden Listen null ist, wird eine leere Liste zurückgegeben.

## Kategorie

Liste

## Funktionssyntax

`intersect(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste 1 | Liste |
| Liste 2 | Liste  |

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

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Gibt [&quot;sports&quot;, &quot;news&quot; zurück]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Gibt häufige Elemente zwischen Profil-Attributen und der angegebenen Liste von Kategorien zurück.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Gibt häufige Elemente zwischen Profil-Attributen und angegebenem Ereignis-Feld zurück.
