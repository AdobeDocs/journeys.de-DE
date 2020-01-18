---
title: inLastDays
description: Informationen zur Funktion in LastDays
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

---


# inLastDays {#inLastDays}

Gibt &quot;true&quot;zurück, wenn ein bestimmtes Datum oder dateTime zwischen jetzt und jetzt liegt - Delta-Tage.

## Kategorie

Date

## Funktionssyntax

`inLastDays(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inLastDays(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Gibt TRUE zurück.
