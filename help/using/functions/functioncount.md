---
product: adobe campaign
title: count
description: Erfahren Sie mehr über die Funktion „count“
feature: Journeys
role: Developer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 100%

---

# count {#count}

Zählt die Elemente der Liste, wobei Nullwerte nicht berücksichtigt werden.

## Kategorie

Aggregation

## Funktionssyntax

`count(<listAny>)`

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

`count(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`count([10,2,10,null])`

Gibt 3 zurück.
