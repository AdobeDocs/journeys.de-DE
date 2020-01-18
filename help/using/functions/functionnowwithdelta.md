---
title: nowWithDelta
description: Erfahren Sie mehr über die Funktion nowWithDelta
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# nowWithDelta {#nowWithDelta}

Gibt die aktuelle Uhrzeit einschließlich eines Offsets zurück. Wenn eine Zeitzone-ID angegeben wird, wird der Zeitzonenversatz angewendet. Weitere Informationen zu Datentypen finden Sie unter [](../expression/data-types.md).

## Kategorie

Date

## Funktionssyntax

`nowWithDelta(<parameters>)`

## Parameter

| Parameter | Description |
|--- |--- |
| delta | positive oder negative Ganzzahlwerte |
| Datumsteil | Jahre, Monate, Tage, Stunden, Minuten oder Sekunden als Zeichenfolge |
| Zeitzone-ID | Zeichenfolgendarstellung des Zeitzonenwerts. Weitere Informationen finden Sie unter [](../expression/data-types.md). Die Zeitzone-ID muss eine String-Konstante sein. Es kann weder ein Feldverweis noch ein Ausdruck sein. |

## Signaturen und zurückgegebener Typ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Gibt dateTime zurück.

## Beispiele

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Gibt dateTime genau vor 2 Stunden zurück.
