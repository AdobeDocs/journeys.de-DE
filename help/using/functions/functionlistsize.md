---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: Erfahren Sie mehr über die Funktion „listSize“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---


# listSize {#listSize}

Zählt die Zahl der Elemente in der Liste.

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

## Signaturen und zurückgegebener Typ

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`listSize([10,2,3])`

Gibt 3 zurück.
