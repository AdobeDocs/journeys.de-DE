---
product: adobe campaign
title: inNextMonths
description: Erfahren Sie mehr über die Funktion „inNextMonths“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---

# inNextMonths {#inNextMonths}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt + delta Monaten liegt.

## Kategorie

Datum

## Funktionssyntax

`inNextMonths(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | Ganzzahl |

## Signaturen und zurückgegebener Typ

`inNextMonths(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Gibt „true“ zurück.
