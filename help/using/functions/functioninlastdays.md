---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: Erfahren Sie mehr über die Funktion „inLastDays“
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---


# inLastDays {#inLastDays}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt - delta Tagen liegt.

## Kategorie

Datum

## Funktionssyntax

`inLastDays(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inLastDays(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Gibt „true“ zurück.
