---
product: adobe campaign
title: toDateOnly
description: Erfahren Sie mehr über die Funktion „toDateOnly“
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# toDateOnly{#toDateOnly}

Konvertiert einen Argumentwert in einen reinen Datumswert.

## Kategorie

Konversion

## Funktionssyntax

`toDateOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum im ISO-8601-Format oder im XDM-Datumsformat „JJJJ-MM-TT“  | string |
| Datum | date |

## Signaturen und zurückgegebene Typen

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateOnly("2016-08-18")`

gibt ein dateOnly-Objekt zurück, das 2016-08-18 darstellt.
