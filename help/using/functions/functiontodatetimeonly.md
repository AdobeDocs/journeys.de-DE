---
product: adobe campaign
title: toDateTimeOnly
description: Erfahren Sie mehr über die Funktion „toDateTime“
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 100%

---

# toDateTimeOnly{#toDateTimeOnly}

Konvertiert einen Argumentwert in einen reinen Datum-/Uhrzeit-Wert.

## Kategorie

Konversion

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit im ISO-8601-Format oder im XDM-Datumsformat &quot;JJJJ-MM-TT&quot; | Zeichenfolge |
| Datum/Uhrzeit | dateTime |

## Signaturen und zurückgegebene Typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateTimeOnly ("2016-08-18")`

gibt einen Datum/Uhrzeit-Wert zurück, der 2016-08-18T00:00:00.000 entspricht.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
