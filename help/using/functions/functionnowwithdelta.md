---
product: adobe campaign
title: nowWithDelta
description: Erfahren Sie mehr über die Funktion „nowWithDelta“
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '110'
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
| Zeitzonen-ID | Zeichenfolgendarstellung des Zeitzonenwerts. Weitere Informationen finden Sie unter [Datentypen](../expression/data-types.md). Die Zeitzonen-ID muss eine Zeichenfolgenkonstante sein. Er darf weder ein Feldverweis noch ein Ausdruck sein. |

## Signaturen und zurückgegebener Typ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Gibt einen Datum/Uhrzeit-Wert zurück.

## Beispiele

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Gibt einen Datum/Uhrzeit-Wert von vor genau 2 Stunden zurück.
