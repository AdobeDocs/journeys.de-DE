---
product: adobe campaign
title: inLastMonths
description: Erfahren Sie mehr über die Funktion „inLastMonths“
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# inLastMonths {#inLastMonths}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum-/Uhrzeit-Wert zwischen jetzt und jetzt – delta Monaten liegt.

## Kategorie

Datum

## Funktionssyntax

`inLastMonths(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inLastMonths(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Gibt „true“ zurück.
