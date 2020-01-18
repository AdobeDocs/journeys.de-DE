---
title: serializeList
description: Informationen zur Funktion serializeList
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


# serializeList {#serializeList}

Konvertiert die im ersten Parameter angegebene Liste (jeden Typ) in eine Zeichenfolge. Der zweite Parameter stellt das zu verwendende Trennzeichen dar. Der dritte Parameter ist ein boolescher Wert, der angibt, ob jedes Element des Ausdrucks Anführungszeichen enthalten soll.

## Kategorie

Liste

## Funktionssyntax

`serializeList(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| String | String |
| Boolesch | Boolesch |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listPoint |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Unterschrift und zurückgegebener Typ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`serializeList(["Hello","World"], " ", false)`

Gibt &quot;Hello World&quot;zurück.

`serializeList(["Hello", "World"], ",", true)`

Gibt &quot;Hello&quot;,&quot;World&quot;zurück.
