---
product: adobe campaign
solution: Journey Orchestration
title: Funktionen
description: Erfahren Sie mehr über Funktionen
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 98%

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
| Liste | [differentCount](../functions/functiondistinctcount.md) |
| Liste | [in](../functions/functionin.md) |
| Liste | [listSize](../functions/functionlistsize.md) |
| Liste | [serializeList](../functions/functionserializelist.md) |
| Liste | [sort](../functions/functionsort.md) |
| Mathematisch | [random](../functions/functionrandom.md) |
| Mathematisch | [round](../functions/functionround.md) |
| Zeichenfolge | [concat](../functions/functionconcat.md) |
| Zeichenfolge | [contain](../functions/functioncontain.md) |
| Zeichenfolge | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Zeichenfolge | [endWith](../functions/functionendwith.md) |
| Zeichenfolge | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Zeichenfolge | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Zeichenfolge | [indexOf](../functions/functionindexof.md) |
| Zeichenfolge | [isEmpty](../functions/functionisempty.md) |
| Zeichenfolge | [isNotEmpty](../functions/functionisnotempty.md) |
| Zeichenfolge | [lastIndexOf](../functions/functionlastindexof.md) |
| Zeichenfolge | [length](../functions/functionlength.md) |
| Zeichenfolge | [lower](../functions/functionlower.md) |
| Zeichenfolge | [matchRegExp](../functions/functionmatchregexp.md) |
| Zeichenfolge | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Zeichenfolge | [replace](../functions/functionreplace.md) |
| Zeichenfolge | [replaceAll](../functions/functionreplaceall.md) |
| Zeichenfolge | [startWith](../functions/functionstartwith.md) |
| Zeichenfolge | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Zeichenfolge | [substr](../functions/functionsubstr.md) |
| Zeichenfolge | [trim](../functions/functiontrim.md) |
| Zeichenfolge | [upper](../functions/functionupper.md) |
| Zeichenfolge | [uuid](../functions/functionuuid.md) |