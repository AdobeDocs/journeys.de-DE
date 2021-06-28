---
product: adobe campaign
title: setHours
description: Erfahren Sie mehr über die Funktion „setHours“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '77'
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
