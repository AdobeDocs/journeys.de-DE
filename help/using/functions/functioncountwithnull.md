---
product: adobe campaign
title: countWithNull
description: Erfahren Sie mehr über die Funktion „countWithNull“
feature: Journeys
role: Developer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 100%

---

# countWithNull {#countWithNull}

Zählt alle Elemente der Liste, einschließlich Nullwerten.

## Kategorie

Aggregation

## Funktionssyntax

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`countWithNull([10,2,10,null])`

Gibt 4 zurück.
