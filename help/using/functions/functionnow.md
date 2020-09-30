---
title: now
description: Erfahren Sie mehr über die Funktion „now“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 70bc6653a8cdd552a0441f4b661341d3f095b112
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 100%

---


# now {#now}

Gibt das aktuelle Datum im Datum/Uhrzeit-Format zurück. Weiterführende Informationen finden Sie im Abschnitt [](../expression/data-types.md).

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