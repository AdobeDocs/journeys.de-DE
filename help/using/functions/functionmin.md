---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Erfahren Sie mehr über die Funktion „min“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 100%

---


# min {#min}

Gibt den Minimalwert aus einem Satz von Ausdrücken zurück, entweder als Liste oder in Form von zwei Ausdrücken. Nullwerte werden ignoriert.

## Kategorie

Aggregation

## Funktionssyntax

`min(<parameters>)`

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

`min(<listDuration>)`

Gibt eine Dauer zurück.

`min(<listInteger>)`

Gibt eine Dauer zurück.

`min(<listDateTimeOnly>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

`min(<listDateTime>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`min(<listDecimal>)`

Gibt eine Dezimalzahl zurück.

`min(<decimal>,<decimal>)`

Gibt eine Dezimalzahl zurück.

`min(<duration>,<duration>)`

Gibt eine Dauer zurück.

`min(<dateTime>,<dateTime>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

`min(<integer>,<integer>)`

Gibt eine Ganzzahl zurück.

## Beispiele

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Gibt 3 zurück.

`min([10,null,8])`

Gibt 8 zurück.
