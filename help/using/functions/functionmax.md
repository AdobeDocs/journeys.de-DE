---
title: max
description: Erfahren Sie mehr über die Funktion „max“
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
source-wordcount: '88'
ht-degree: 100%

---

# max{#max}

Gibt den Maximalwert aus einem Satz von Ausdrücken zurück, entweder als Liste oder in Form von zwei Ausdrücken. Nullwerte werden ignoriert.

## Kategorie

Aggregation

## Funktionssyntax

`max(<parameter>)`

## Parameter

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duration
* integer
* decimal
* dateTime
* dateTimeOnly

## Signaturen und zurückgegebene Typen

`max(<listDuration>)`

Gibt eine Dauer zurück.

`max(<listInteger>)`

Gibt eine Dauer zurück.

`max(<listDateTimeOnly>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

`max(<listDateTime>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`max(<listDecimal>)`

Gibt eine Dezimalzahl zurück.

`max(<decimal>,<decimal>)`

Gibt eine Dezimalzahl zurück.

`max(<duration>,<duration>)`

Gibt eine Dauer zurück.

`max(<dateTime>,<dateTime>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

`max(<integer>,<integer>)`

Gibt eine Ganzzahl zurück.

## Beispiele

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Gibt 10 zurück.

`max([10,null,8])`

Gibt 10 zurück.
