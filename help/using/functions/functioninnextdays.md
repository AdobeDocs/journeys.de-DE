---
product: adobe campaign
title: inNextDays
description: Erfahren Sie mehr über die Funktion „inNextDays“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---

# inNextDays {#inNextDays}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt + delta Tagen liegt.

## Kategorie

Datum

## Funktionssyntax

`inNextDays(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inNextDays(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Gibt „true“ zurück.
