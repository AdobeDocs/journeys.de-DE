---
product: adobe campaign
title: serializeList
description: Erfahren Sie mehr über die Funktion „serializeList“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 100%

---

# serializeList {#serializeList}

Konvertiert die im ersten Parameter angegebene Liste (beliebiger Typ) in eine Zeichenfolge. Der zweite Parameter stellt das zu verwendende Trennzeichen dar. Der dritte Parameter ist ein boolescher Wert, der angibt, ob die einzelnen Elemente des Ausdrucks Anführungszeichen umfassen sollen.

## Kategorie

Liste

## Funktionssyntax

`serializeList(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Zeichenfolge | Zeichenfolge |
| Boolesch | Boolesch |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listPoint |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |
| Liste | listDateOnly |

## Signatur und zurückgegebener Typ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`serializeList(["Hello","World"], " ", false)`

Gibt „Hello World“ zurück.

`serializeList(["Hello", "World"], ",", true)`

Gibt „&quot;Hello&quot;,&quot;World&quot;“ zurück.
