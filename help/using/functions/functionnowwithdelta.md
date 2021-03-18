---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Erfahren Sie mehr über die Funktion „nowWithDelta“
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 100%

---


# nowWithDelta {#nowWithDelta}

Gibt den aktuellen Datum/Uhrzeit-Wert einschließlich Verschiebung zurück. Wenn eine Zeitzonen-ID angegeben wird, wird die Zeitzonenverschiebung angewendet. Weitere Informationen zu Datentypen finden Sie auf [dieser Seite](../expression/data-types.md).

## Kategorie

Datum

## Funktionssyntax

`nowWithDelta(<parameters>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| delta | positiver oder negativer Ganzzahlwert |
| date part | Jahre, Monate, Tage, Stunden, Minuten oder Sekunden als Zeichenfolge |
| time zone id | Zeichenfolgendarstellung des Zeitzonenwerts. Weitere Informationen finden Sie unter [Datentypen](../expression/data-types.md). Die Zeitzonen-ID muss eine Zeichenfolgenkonstante sein. Sie darf weder ein Feldverweis noch ein Ausdruck sein. |

## Signaturen und zurückgegebener Typ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Gibt einen Datum/Uhrzeit-Wert zurück.

## Beispiele

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Gibt einen Datum/Uhrzeit-Wert von vor genau 2 Stunden zurück.
