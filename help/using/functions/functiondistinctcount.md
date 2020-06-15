---
title: distinctCount
description: Erfahren Sie mehr über die Funktion „distinctCount“
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 100%

---


# distinctCount{#distinctCount}

Zählt die Anzahl verschiedener Werte, wobei Nullwerte ignoriert werden.

## Kategorie

Aggregation

## Funktionssyntax

`distinctCount(<listAny>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signatur und zurückgegebener Typ

`distinctCount(<listAny>)`

Gibt eine Ganzzahl zurück.

## Beispiel

`distinctCount([10,2,10,null])`

Gibt 2 zurück.
