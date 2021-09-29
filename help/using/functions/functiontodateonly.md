---
product: adobe campaign
title: toDateOnly
description: Erfahren Sie mehr über die Funktion toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 42%

---

# toDateOnly{#toDateOnly}

Konvertiert einen Argumentwert in einen Nur-Datum-Wert.

## Kategorie

Konversion

## Funktionssyntax

`toDateOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum im Format ISO-8601 oder &quot;JJJJ-MM-TT&quot;(XDM-Datumsformat) | string |
| Datum | date |

## Signaturen und zurückgegebene Typen

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateOnly("2016-08-18")`

gibt ein dateOnly -Objekt zurück, das 2016-08-18 darstellt.