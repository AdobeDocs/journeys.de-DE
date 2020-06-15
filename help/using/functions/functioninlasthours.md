---
title: inLastHours
description: Erfahren Sie mehr über die Funktion „inLastHours“
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 100%

---


# inLastHours {#inLastHours}

Gibt „true“ zurück, wenn der angegebene Datum/Uhrzeit-Wert zwischen jetzt und jetzt - delta Stunden liegt.

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

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Gibt „true“ zurück.

`inLastHours(@{MyEvent.timestamp}, 4)`

Gibt „true“ zurück.
