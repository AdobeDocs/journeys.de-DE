---
title: inNextYears
description: Erfahren Sie mehr über die Funktion „inNextYears“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---


# inNextYears {#inNextYears}

Gibt „true“ zurück, wenn der angegebene Datums- bzw. Datum/Uhrzeit-Wert zwischen jetzt und jetzt + delta Jahren liegt.

## Kategorie

Datum

## Funktionssyntax

`inNextYears(<dateTime>,<delta>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit | dateTime |
| delta | integer |

## Signaturen und zurückgegebener Typ

`inNextYears(<dateTime>,<integer>)`

Gibt einen booleschen Wert zurück.

## Beispiele

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Gibt „true“ zurück.
