---
product: adobe campaign
title: inNextHours
description: Erfahren Sie mehr über die Funktion „inNextHours“
feature: Journeys
role: Developer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# inNextHours {#inNextHours}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum-/Uhrzeit-Wert zwischen jetzt und jetzt + delta Stunden liegt.

## Kategorie

Datum

## Funktionssyntax

`inNextHours(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inNextHours(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Gibt „true“ zurück.
