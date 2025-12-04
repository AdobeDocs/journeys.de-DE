---
product: adobe campaign
title: inLastHours
description: Erfahren Sie mehr über die Funktion „inLastHours“
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---

# inLastHours {#inLastHours}

Gibt „true“ zurück, wenn der angegebene Datum/Uhrzeit-Wert zwischen jetzt und jetzt – delta Stunden liegt.

## Kategorie

Datum

## Funktionssyntax

`inLastHours(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inLastHours(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Gibt „true“ zurück.

`inLastHours(@{MyEvent.timestamp}, 4)`

Gibt „true“ zurück.
