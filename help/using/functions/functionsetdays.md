---
title: setDays
description: Erfahren Sie mehr über die Funktion setDays
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


# setDays {#setDays}

Legt nur den Tag einer Datums- oder Datumseingabe fest. Wenn Sie beispielsweise bis zu einem bestimmten Tag des Monats warten möchten, können Sie den Tag erzwingen.

## Kategorie

Date

## Funktionssyntax

`setDays(<parameter>)`

## Parameter

| Parameter | Typ |
|--- |--- |
| Datum | dateTime |
| Zeitdauer ohne Berücksichtigung der Zeitzone | dateTimeOnly |
| Tage | integer |

## Signaturen und zurückgegebener Typ

`setDays(<dateTime>,<days>)`

Gibt eine Uhrzeit zurück.

`setDays(<dateTimeOnly>,<days>)`

Gibt eine Uhrzeit ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Gibt 2010-12-25T01:11:00Z zurück.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
