---
product: adobe campaign
title: listSize
description: Erfahren Sie mehr über die Funktion „listSize“
feature: Journeys
role: Developer
level: Experienced
exl-id: c0d34a8d-33e9-4c7b-9b7d-a1b21ed96d35
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# listSize {#listSize}

Zählt die Anzahl der Elemente in der Liste.

## Kategorie

Liste

## Funktionssyntax

`listSize(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |
| Liste | listDateOnly |

## Signaturen und zurückgegebener Typ

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`listSize([10,2,3])`

Gibt 3 zurück.
