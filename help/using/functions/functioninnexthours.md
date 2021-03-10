---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: Erfahren Sie mehr über die Funktion „inNextHours“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 93%

---


# inNextHours {#inNextHours}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt + delta Stunden liegt.

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
