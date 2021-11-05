---
product: adobe campaign
title: notEqualIgnoreCase
description: Erfahren Sie mehr über die Funktion notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 81%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Überprüft, ob sich die erste Argumentzeichenfolge von der zweiten Argumentzeichenfolge unterscheidet, wobei Groß-/Kleinschreibung ignoriert wird.

## Kategorie

Zeichenfolge

## Funktionssyntax

`notEqualIgnoreCase(<parameters>)`

## Parameter

* Zeichenfolge

## Signatur und zurückgegebener Typ

`notEqualIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
