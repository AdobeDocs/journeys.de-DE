---
title: jetzt
description: Erfahren Sie mehr über die Funktion
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# jetzt {#now}

Gibt das aktuelle Datum im Datumszeitformat zurück. Weitere Informationen zu Datentypen finden Sie unter [](../expression/data-types.md).

## Kategorie

Date

## Funktionssyntax

`now(<parameter>)`

## Parameter

| Parameter | Description |
|--- |--- |
| string |  |

## Signaturen und zurückgegebener Typ

`now()`

`"now(<timeZone id>")`

Gibt dateTime zurück.

## Beispiele

`now()`

Gibt 2019-06-03T06:30Z zurück.

`toString(now())`

Gibt &quot;2019-06-03T06:30Z&quot;zurück

`now("Europe/Paris")`

Gibt 2019-06-03T08:30+02:00 zurück.