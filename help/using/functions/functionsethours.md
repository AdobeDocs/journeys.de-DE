---
title: setHours
description: Erfahren Sie mehr über die Funktion „setHours“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: ht
source-wordcount: '76'
ht-degree: 100%

---


# setHours {#setHours}

Legt die Stunden eines Datum/Uhrzeit-Werts oder Datum/Uhrzeit-Werts ohne Zeitzone fest. Wenn Sie beispielsweise morgen bis zu einer bestimmten Stunde warten möchten, können Sie die Stunde erzwingen.

## Kategorie

Datum

## Funktionssyntax

`setHours(<parameter>)`

## Parameter

| Parameter | Typ |
|--- |--- |
| Datum/Uhrzeit | dateTime |
| Datum/Uhrzeit ohne Berücksichtigung der Zeitzone | dateTimeOnly |
| Stunden | Ganzzahl |

## Signaturen und zurückgegebener Typ

`setHours(<dateTime>,<hours>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`setHours(<dateTimeOnly>,<hours>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Gibt 2010-12-12T04:11:00Z zurück.

`setHours(nowWithDelta(1, "days"), 20)`

Gibt morgen um 20 Uhr zurück.
