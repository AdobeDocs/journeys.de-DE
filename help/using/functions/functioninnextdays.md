---
title: inNextDays
description: Informationen zur Funktion in NextDays
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
source-git-commit: 0e06abf518445ce145d2d042b16daaa2dfd9603e

---


# inNextDays {#inNextDays}

Gibt TRUE zurück, wenn ein bestimmtes Datum oder eine angegebene dateTime zwischen jetzt und jetzt liegt + Delta-Tage.

## Kategorie

Date

## Funktionssyntax

`inNextDays(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inNextDays(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Gibt TRUE zurück.
