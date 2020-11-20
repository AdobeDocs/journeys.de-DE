---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: Erfahren Sie mehr über die Funktion „inLastYears“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---


# inLastYears {#inLastYears}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt - delta Jahren liegt.

## Kategorie

Datum

## Funktionssyntax

`inLastYears(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inLastYears(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Gibt „true“ zurück.
