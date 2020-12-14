---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: Erfahren Sie mehr über die Funktion „updateTimeZone“
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '41'
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

## Beispiel

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Gibt 2019-08-28T17:15:30.123+02:00 zurück.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
