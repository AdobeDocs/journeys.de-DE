---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Erfahren Sie mehr über die Funktion „random“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
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
