---
title: toDateTimeOnly
description: Informationen zur Funktion toDateTime
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


# toDateTimeOnly{#toDateTimeOnly}

Konvertiert einen Argumentwert in einen Nur-Datum-Zeitwert.

## Kategorie

Konversion

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum ohne Zeitzone im ISO-8601-Format | string |
| dateTime | dateTime |

## Signaturen und zurückgegebene Typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Geben Sie eine Uhrzeit ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateTimeOnly ("2016-08-18T23:17:59.123")`

Gibt 2016-08-18T23:17:59.123 zurück.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
