---
title: avg
description: Erfahren Sie mehr über die Funktion avg
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# avg {#avg}

Gibt den Durchschnittswert aus einem Satz von Ausdrücken zurück, entweder als Liste oder als zwei Ausdrücke. Null-Werte werden ignoriert.


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

Gibt eine Dezimalstelle zurück.

## Beispiele

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Gibt 7.0 zurück.

`avg(10.2, 3)`

Gibt 6.6 zurück.
