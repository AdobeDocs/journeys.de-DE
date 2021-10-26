---
product: adobe campaign
title: toDateOnly
description: Erfahren Sie mehr über die Funktion „toDateOnly“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: ht
source-wordcount: '52'
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