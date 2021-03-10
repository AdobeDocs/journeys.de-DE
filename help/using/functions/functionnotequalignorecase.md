---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „notEqualWithIgnoreCase“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 92%

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
