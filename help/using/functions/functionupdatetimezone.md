---
title: updateTimeZone
description: Erfahren Sie mehr über die Funktion „updateTimeZone“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
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
