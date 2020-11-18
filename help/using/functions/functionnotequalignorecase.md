---
title: notEqualWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „notEqualWithIgnoreCase“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '37'
ht-degree: 100%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Überprüft, ob sich die erste Argumentzeichenfolge von der zweiten Argumentzeichenfolge unterscheidet, wobei Groß-/Kleinschreibung ignoriert wird.

## Kategorie

Zeichenfolge

## Funktionssyntax

`notEqualWithIgnoreCase(<parameters>)`

## Parameter

* string

## Signatur und zurückgegebener Typ

`notEqualWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
