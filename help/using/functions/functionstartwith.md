---
title: startWith
description: Erfahren Sie mehr über die Funktion startWith
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


# startWith {#startWith}

Gibt TRUE zurück, wenn der zweite Parameter ein Präfix des ersten Parameters ist.

## Kategorie

String

## Funktionssyntax

`startWith(<parameters>)`

## Parameter

| Parameter | Typ |
|-------------|--------|
| string | string |
| Präfix | string |

## Unterschrift und zurückgegebener Typ

`startWith(<string>,<string>)`

Gib einen Booleschen zurück.

## Beispiel

`startWith("Hello World", "Hello")`

Gibt TRUE zurück.

`startWith("Hello World", "World")`

Gibt false zurück.
