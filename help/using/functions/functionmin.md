---
product: adobe campaign
title: min
description: Erfahren Sie mehr über die Funktion „min“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: ht
source-wordcount: '92'
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
* listDateOnly
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

`min(<listDateOnly>)`

Gibt ein Datum zurück.

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
