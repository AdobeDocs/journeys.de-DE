---
product: adobe campaign
title: distinctCountWithNull
description: Erfahren Sie mehr über die Funktion „distinctCountWithNull“
feature: Journeys
role: Developer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 100%

---

# distinctCountWithNull {#distinctCountWithNull}

Zählt die Anzahl verschiedener Werte einschließlich der Nullwerte.

## Kategorie

Aggregation

## Funktionssyntax

`distinctCountWithNull(<listAny>)`

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

## Signatur und zurückgegebener Typ

`distinctCountWithNull(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`distinctCountWithNull([10,2,10,null])`

Gibt 3 zurück.
