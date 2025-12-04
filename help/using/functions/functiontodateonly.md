---
product: adobe campaign
title: toDateOnly
description: Erfahren Sie mehr über die Funktion „toDateOnly“
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 100%

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
