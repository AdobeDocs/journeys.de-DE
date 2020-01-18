---
title: unterscheide
description: Erfahren Sie mehr über die Funktionsmerkmale
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


# unterscheide {#distinct}

Gibt die eindeutigen Werte der Liste ohne Null-Werte zurück.

## Kategorie

Liste

## Funktionssyntax

`distinct(<parameter>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signaturen und zurückgegebene Typen

`distinct(<listInteger>)`

Gibt eine Liste mit Ganzzahlen zurück.

`distinct(<listDecimal>)`

Gibt eine Liste mit Dezimalstellen zurück.

`distinct(<listString>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`distinct(<listDateTimeOnly>)`

Gibt eine Liste der Datenzeiten ohne Berücksichtigung der Zeitzone zurück.

`distinct(<listDateTime>)`

Gibt eine Liste der Datenzeiten zurück.

`distinct(<listBoolean>)`

Gibt eine Liste der Booleschen Elemente zurück.

`distinct(<listDuration>)`

Gibt eine Liste der Dauer zurück.

## Beispiele

`distinct([10,2,10,null])`

Gibt zurück `[10, 2]`.
