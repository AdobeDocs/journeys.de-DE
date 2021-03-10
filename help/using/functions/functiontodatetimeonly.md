---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: Erfahren Sie mehr über die Funktion „toDateTimeOnly“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 94%

---


# toDateTimeOnly{#toDateTimeOnly}

Konvertiert einen Argumentwert in einen Datum/Uhrzeit-Wert ohne Zeitzone.

## Kategorie

Konversion

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit im ISO 8601-Format | Zeichenfolge |
| Datum/Uhrzeit | dateTime |

## Signaturen und zurückgegebene Typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Gibt 2016-08-18T23:17:59.123 zurück.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
