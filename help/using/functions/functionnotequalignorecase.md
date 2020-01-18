---
title: notEqualWithIgnoreCase
description: Informationen zur Funktion notEqualWithIgnoreCase
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


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Überprüfen Sie, ob sich die erste Argumentzeichenfolge mit der zweiten Argumentzeichenfolge unterscheidet, wobei die Groß-/Kleinschreibung ignoriert wird.

## Kategorie

String

## Funktionssyntax

`notEqualWithIgnoreCase(<parameters>)`

## Parameter

* string

## Unterschrift und zurückgegebener Typ

`notEqualWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
