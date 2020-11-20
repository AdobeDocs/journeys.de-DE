---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Erfahren Sie mehr über die Funktion „setDays“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
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
| Tage | Ganzzahl |

## Signaturen und zurückgegebener Typ

`setDays(<dateTime>,<days>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`setDays(<dateTimeOnly>,<days>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Gibt 2010-12-25T01:11:00Z zurück.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
