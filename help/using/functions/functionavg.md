---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: Erfahren Sie mehr über die Funktion „avg“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 94%

---


# avg {#avg}

Gibt den Durchschnittswert eines Satzes von Ausdrücken zurück, entweder als Liste oder in Form von zwei Ausdrücken. Nullwerte werden ignoriert.


## Kategorie

Aggregation

## Funktionssyntax

`avg(<parameter>)`

## Parameter

Unterstützte Typen:

* listInteger
* listDecimal
* decimal
* integer

## Signaturen und zurückgegebener Typ

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Gibt eine Dezimalzahl zurück.

## Beispiele

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Gibt 7,0 zurück.

`avg(10.2, 3)`

Gibt 6,6 zurück.
