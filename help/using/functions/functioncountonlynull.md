---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Erfahren Sie mehr über die Funktion „countOnlyNull“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 94%

---


# countOnlyNull {#countOnlyNull}

Zählt die Zahl der Nullwerte in der Liste.

## Kategorie

Aggregation

## Funktionssyntax

`countOnlyNull(<listAny>)`

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

## Signatur und zurückgegebener Typ

`countOnlyNull(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`count([10,2,10,null])`

Gibt 1 zurück.
