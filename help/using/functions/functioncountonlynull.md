---
product: adobe campaign
title: countOnlyNull
description: Erfahren Sie mehr über die Funktion „countOnlyNull“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

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
| Liste | listDateOnly |

## Signatur und zurückgegebener Typ

`countOnlyNull(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`countOnlyNull([10,2,10,null])`

Gibt 1 zurück.
