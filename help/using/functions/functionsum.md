---
product: adobe campaign
title: sum
description: Erfahren Sie mehr über die Funktion „sum“
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 100%
---
# sum {#sum}

Gibt die Summe der Werte eines Satzes von Ausdrücken zurück. Nullwerte werden ignoriert.

## Kategorie

Aggregation

## Funktionssyntax

`sum(<parameters>)`

## Parameter

* listInteger
* listDecimal
* duration
* integer
* decimal

## Signaturen und zurückgegebene Typen

`sum(<listDecimal>)`

Gibt eine Dezimalzahl zurück.

`sum(<listInteger>)`

Gibt eine Ganzzahl zurück.

`sum(<integer>,<integer>)`

Gibt eine Ganzzahl zurück.

`sum(<decimal>,<decimal>)`

Gibt eine Dezimalzahl zurück.

## Beispiele

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Gibt 21 zurück.

`sum([10.5,null,8.1])`

Gibt 18.6 zurück.
