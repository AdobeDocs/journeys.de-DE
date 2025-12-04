---
product: adobe campaign
title: setDays
description: Erfahren Sie mehr über die Funktion „setDays“
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 100%

---

# setDays {#setDays}

Legt den Tag eines Datum/Uhrzeit-Werts oder Datum/Uhrzeit-Werts ohne Zeitzone fest. Wenn Sie beispielsweise bis zu einem bestimmten Tag des Monats warten möchten, können Sie den Tag erzwingen.

## Kategorie

Datum

## Funktionssyntax

`setDays(<parameter>)`

## Parameter

| Parameter | Typ |
|--- |--- |
| Datum/Uhrzeit | dateTime |
| Datum/Uhrzeit ohne Berücksichtigung der Zeitzone | dateTimeOnly |
| Tage | integer |

## Signaturen und zurückgegebener Typ

`setDays(<dateTime>,<days>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`setDays(<dateTimeOnly>,<days>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Gibt 2010-25-12T01:11:00Z zurück.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
