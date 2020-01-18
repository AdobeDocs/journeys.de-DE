---
title: updateTimeZone
description: Informationen zur Funktion updateTimeZone
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


# updateTimeZone {#updateTimeZone}

Gibt eine neue Datumseingabe mit einer neuen Zeitzone am selben Zeitpunkt zurück.

## Kategorie

Date

## Funktionssyntax

`updateTimeZone(<parameters>)`

## Parameter

* Zeitzone-ID: string
* dateTime

## Unterschrift und zurückgegebener Typ

`updateTimeZone(<dateTime>,<timeZone id>)`

Gibt eine Uhrzeit zurück.

## Beispiel

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Gibt 2019-08-28T17:15:30.123+02:00 zurück.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
