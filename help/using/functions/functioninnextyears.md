---
title: inNextYears
description: Informationen zur Funktion in den nächsten Jahren
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
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49

---


# inNextYears {#inNextYears}

Gibt &quot;true&quot;zurück, wenn ein bestimmtes Datum oder eine angegebene dateTime zwischen jetzt und jetzt liegt + Delta-Jahre.

## Kategorie

Date

## Funktionssyntax

`inNextYears(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inNextYears(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Gibt TRUE zurück.
