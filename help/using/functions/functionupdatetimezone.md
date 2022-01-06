---
product: adobe campaign
title: updateTimeZone
description: Erfahren Sie mehr über die Funktion „updateTimeZone“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: ht
source-wordcount: '53'
ht-degree: 100%

---

# updateTimeZone {#updateTimeZone}

Gibt einen neuen Datum/Uhrzeit-Wert mit einer neuen Zeitzone zum selben Moment zurück.

## Kategorie

Datum

## Funktionssyntax

`updateTimeZone(<parameters>)`

## Parameter

* time zone id: string
* dateTime

## Signatur und zurückgegebener Typ

`updateTimeZone(<dateTime>,<timeZone id>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

## Beispiele

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Gibt 2019-08-28T17:15:30.123+02:00 zurück.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Wenn der Wert des Zeitstempelfelds `2021-11-16T16:55:12.939318+01:00` ist, gibt die Funktion `2021-11-17T02:55:12.942115+11:00` zurück.
