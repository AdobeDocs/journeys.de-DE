---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Erfahren Sie mehr über die Funktion „max“
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
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
