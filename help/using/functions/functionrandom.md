---
product: adobe campaign
title: random
description: Erfahren Sie mehr über die Funktion „random“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '52'
ht-degree: 100%

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
