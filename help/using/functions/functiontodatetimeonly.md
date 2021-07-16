---
product: adobe campaign
title: toDateTimeOnly
description: Erfahren Sie mehr über die Funktion „toDateTime“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 0c55ece133639ec001b58f73afcbc69787b98c0e
workflow-type: ht
source-wordcount: '56'
ht-degree: 100%

---

# toDateTimeOnly{#toDateTimeOnly}

Konvertiert einen Argumentwert in einen Datum/Uhrzeit-Wert ohne Zeitzone.

## Kategorie

Konversion

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit im ISO-8601-Format oder im XDM-Datumsformat &quot;JJJJ-MM-TT&quot; | Zeichenfolge |
| Datum/Uhrzeit | dateTime |

## Signaturen und zurückgegebene Typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

## Beispiele

`toDateTimeOnly ("2016-08-18")`

gibt einen Datum/Uhrzeit-Wert zurück, der 2016-08-18T00:00:00.000 entspricht.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
