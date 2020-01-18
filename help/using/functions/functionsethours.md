---
title: setHours
description: Informationen zur Funktion setHours
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# setHours {#setHours}

Legt nur die Stunden einer Datums- oder Datumseingabe fest. Wenn Sie beispielsweise morgen bis zu einer bestimmten Stunde warten möchten, können Sie die Stunde erzwingen.

## Kategorie

Date

## Funktionssyntax

`setHours(<parameter>)`

## Parameter

| Parameter | Typ |
|--- |--- |
| Datum | dateTime |
| Zeitdauer ohne Berücksichtigung der Zeitzone | dateTimeOnly |
| Stunden | integer |

## Signaturen und zurückgegebener Typ

`setHours(<dateTime>,<hours>)`

Gibt eine Uhrzeit zurück.

`setHours(<dateTimeOnly>,<hours>)`

Gibt eine Uhrzeit ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Gibt 2010-12-12T04:11:00Z zurück.

`setHours(nowWithDelta(1, "days"), 20)`

Kehrt morgen um 20 Uhr zurück.
