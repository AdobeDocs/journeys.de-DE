---
product: adobe campaign
title: Funktionen
description: Erfahren Sie mehr über Funktionen
feature: Journeys
role: Developer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 100%
---
# Funktionen {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Eine Funktion kann verschiedene Signaturen haben (einen jeweils anderen Satz geordneter Parameter). Eine Funktionssignatur kann 0-N Ausdrücke als geordnete Parameter haben.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, … ,`<expression as param N>`)

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
| Konversion | [toDateOnly](../functions/functiontodateonly.md) |
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
| Datum | [updateTimeZone](../functions/functionupdatetimezone.md) |
| Liste | [distinct](../functions/functiondistinct.md) |
| Liste | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| Liste | [filter](../functions/functionfilter.md) |
| Liste | [getListItem](../functions/functiongetlistitem.md) |
| Liste | [in](../functions/functionin.md) |
| Liste | [intersect](../functions/functionintersect.md) |
| Liste | [listSize](../functions/functionlistsize.md) |
| Liste | [serializeList](../functions/functionserializelist.md) |
| Liste | [sort](../functions/functionsort.md) |
| Math | [random](../functions/functionrandom.md) |
| Math | [round](../functions/functionround.md) |
| String | [concat](../functions/functionconcat.md) |
| String | [contain](../functions/functioncontain.md) |
| String | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| String | [endWith](../functions/functionendwith.md) |
| String | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| String | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| String | [indexOf](../functions/functionindexof.md) |
| String | [isEmpty](../functions/functionisempty.md) |
| String | [isNotEmpty](../functions/functionisnotempty.md) |
| String | [lastIndexOf](../functions/functionlastindexof.md) |
| String | [length](../functions/functionlength.md) |
| String | [lower](../functions/functionlower.md) |
| String | [matchRegExp](../functions/functionmatchregexp.md) |
| String | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| String | [replace](../functions/functionreplace.md) |
| String | [replaceAll](../functions/functionreplaceall.md) |
| String | [startWith](../functions/functionstartwith.md) |
| String | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| String | [substr](../functions/functionsubstr.md) |
| String | [trim](../functions/functiontrim.md) |
| String | [upper](../functions/functionupper.md) |
| String | [uuid](../functions/functionuuid.md) |
