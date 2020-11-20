---
product: adobe campaign
solution: Journey Orchestration
title: Funktionen
description: Erfahren Sie mehr über Funktionen
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 100%

---


# Funktionen {#concept_p1r_qj5_dgb}

Eine Funktion kann verschiedene Signaturen haben (einen jeweils anderen Satz geordneter Parameter). Eine Funktionssignatur kann 0-N Ausdrücke als geordnete Parameter haben.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Jede Funktion weist einen bestimmten Rückgabetyp auf.

Im Folgenden finden Sie eine Liste der unterstützten Funktionen.

## Hauptfunktionen

| Kategorie | Funktion |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Aggregation | [avg](../functions/functionavg.md) |
| Aggregation | [count](../functions/functioncount.md) |
| Aggregation | [countOnlyNull](../functions/functioncountonlynull.md) |
| Aggregation | [countWithNull](../functions/functioncountwithnull.md) |
| Aggregation | [distinctCount](../functions/functiondistinctcount.md) |
| Aggregation | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Aggregation | [max](../functions/functionmax.md) |
| Aggregation | [min](../functions/functionmin.md) |
| Aggregation | [sum](../functions/functionsum.md) |
| Konversion | [toBool](../functions/functiontobool.md) |
| Konversion | [toDateTime](../functions/functiontodatetime.md) |
| Konversion | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Konversion | [toDecimal](../functions/functiontodecimal.md) |
| Konversion | [toDuration](../functions/functiontoduration.md) |
| Konversion | [toInteger](../functions/functiontointeger.md) |
| Konversion | [toString](../functions/functiontostring.md) |
| Datum | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Datum | [inLastDays](../functions/functioninlastdays.md) |
| Datum | [inLastHours](../functions/functioninlasthours.md) |
| Datum | [inLastMonths](../functions/functioninlastmonths.md) |
| Datum | [inLastYears](../functions/functioninlastyears.md) |
| Datum | [inNextDays](../functions/functioninnextdays.md) |
| Datum | [inNextHours](../functions/functioninnexthours.md) |
| Datum | [inNextMonths](../functions/functioninnextmonths.md) |
| Datum | [inNextYears](../functions/functioninnextyears.md) |
| Datum | [now](../functions/functionnow.md) |
| Datum | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Datum | [setHours](../functions/functionsethours.md) |
| Datum | [setDays](../functions/functionsetdays.md) |
| Liste | [distinct](../functions/functiondistinct.md) |
| Liste | [distinctCount](../functions/functiondistinctcount.md) |
| Liste | [in](../functions/functionin.md) |
| Liste | [listSize](../functions/functionlistsize.md) |
| Liste | [serializeList](../functions/functionserializelist.md) |
| Liste | [sort](../functions/functionsort.md) |
| Mathematisch | [random](../functions/functionrandom.md) |
| Mathematisch | [round](../functions/functionround.md) |
| String    | [concat](../functions/functionconcat.md) |
| String    | [contain](../functions/functioncontain.md) |
| String    | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| String    | [endWith](../functions/functionendwith.md) |
| String    | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| String    | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| String    | [indexOf](../functions/functionindexof.md) |
| String    | [isEmpty](../functions/functionisempty.md) |
| String    | [isNotEmpty](../functions/functionisnotempty.md) |
| String    | [lastIndexOf](../functions/functionlastindexof.md) |
| String    | [length](../functions/functionlength.md) |
| String    | [lower](../functions/functionlower.md) |
| String    | [matchRegExp](../functions/functionmatchregexp.md) |
| String    | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| String    | [replace](../functions/functionreplace.md) |
| String    | [replaceAll](../functions/functionreplaceall.md) |
| String    | [startWith](../functions/functionstartwith.md) |
| String    | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| String    | [substr](../functions/functionsubstr.md) |
| String    | [trim](../functions/functiontrim.md) |
| String    | [upper](../functions/functionupper.md) |
| String    | [uuid](../functions/functionuuid.md) |