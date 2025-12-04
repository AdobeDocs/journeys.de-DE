---
product: adobe campaign
title: now
description: Erfahren Sie mehr über die Funktion „now“
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 75%

---

# now {#now}

Gibt das aktuelle Datum im Datum/Uhrzeit-Format zurück. Weitere Informationen zu Datentypen finden Sie auf [dieser Seite](../expression/data-types.md).

## Kategorie

Datum

## Funktionssyntax

`now(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| string |  |

## Signaturen und zurückgegebener Typ

`now()`

`now("<timeZone id>")`

Gibt einen Datum/Uhrzeit-Wert zurück.

## Beispiele

`now()`

Gibt 2019-06-03T06:30Z zurück.

`toString(now())`

Gibt „2019-06-03T06“ :30Z

`now("Europe/Paris")`

Gibt 2019-06-03T08+:30 zurück:00.
