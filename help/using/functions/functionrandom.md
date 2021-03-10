---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Erfahren Sie mehr über die Funktion „random“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 94%

---


# random {#random}

Generiert eine zufällige Zahl zwischen 0 und 1.

## Kategorie

Mathematisch

## Funktionssyntax

`random(<parameters>)`

## Signatur und zurückgegebener Typ

`random()`

Gibt eine Dezimalzahl zurück.

## Beispiel

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Erklärung: Wenn das Erfolgsverhältnis keinen Wert hat/null lautet, wird der Standardwert angewendet und ist eine zufällige Zahl zwischen 0 und 1 * 100 (d. h. zwischen 0 und 100).
