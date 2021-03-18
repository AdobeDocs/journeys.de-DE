---
product: adobe campaign
solution: Journey Orchestration
title: count
description: Erfahren Sie mehr über die Funktion „count“
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '54'
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

## Signaturen und zurückgegebener Typ

`count(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`count([10,2,10,null])`

Gibt 3 zurück.
