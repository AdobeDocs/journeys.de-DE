---
title: min
description: Erfahren Sie mehr über die Funktion min
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

---


# min {#min}

Gibt den Mindestwert aus einem Satz von Ausdrücken zurück, entweder als Liste oder als zwei Ausdrücke. Null-Werte werden ignoriert.

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

Gibt eine Uhrzeit ohne Berücksichtigung der Zeitzone zurück.

`min(<listDateTime>)`

Gibt eine Uhrzeit zurück.

`min(<listDecimal>)`

Gibt eine Dezimalstelle zurück.

`min(<decimal>,<decimal>)`

Gibt eine Dezimalstelle zurück.

`min(<duration>,<duration>)`

Gibt eine Dauer zurück.

`min(<dateTime>,<dateTime>)`

Gibt eine Uhrzeit zurück.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Gibt eine Uhrzeit ohne Berücksichtigung der Zeitzone zurück.

`min(<integer>,<integer>)`

Gibt eine Ganzzahl zurück.

## Beispiele

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Gibt 3 zurück.

`min([10,null,8])`

Gibt 8 zurück.
