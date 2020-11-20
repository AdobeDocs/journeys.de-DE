---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „notEqualWithIgnoreCase“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
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
