---
product: adobe campaign
solution: Journey Orchestration
title: now
description: Erfahren Sie mehr über die Funktion „now“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 79%

---


# now {#now}

Gibt das aktuelle Datum im Datum/Uhrzeit-Format zurück. For more information on data types, refer to [this page](../expression/data-types.md).

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

Gibt „2019-06-03T06:30Z“ zurück

`now("Europe/Paris")`

Gibt 2019-06-03T08:30+02:00 zurück.