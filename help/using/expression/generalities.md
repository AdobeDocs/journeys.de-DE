---
title: Allgemeines
description: Allgemeine Informationen zu erweiterten Ausdrücken
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---


# Allgemeines {#concept_rcy_qj5_dgb}

## Klammern und Priorität von Ausdrücken{#section_edf_fks_bgb}

Klammern können verwendet werden, um einen komplexen Ausdruck lesbarer zu machen. _(&lt;Ausdruck>)_ entspricht _&lt;Ausdruck>_. Außerdem können mit Klammern die Auswertungsreihenfolge und die Assoziativität definiert werden.

Ausdrücke werden von links nach rechts ausgewertet. Die Assoziativität bei arithmetischen Operatoren muss angewendet werden: Multiplikationen und Divisionen haben Vorrang vor Additionen und Subtraktionen. Um eine bestimmte Reihenfolge durchzusetzen und die Operationen voneinander abzugrenzen, müssen Klammern hinzugefügt werden. Beispiel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Ausdruck | Auswertung |
|--- |--- |
| `4 + 2 * 10` | <ul><li>„*“ hat Vorrang vor „+“: 2 * 10 wird ausgewertet als → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Klammern ändern die Priorität: (4 + 2) wird ausgewertet als → 6</li><li> 6 * 10 → 60</li></ul> |

## Groß-/Kleinschreibung{#section_lrb_xh5_dgb}

Im Folgenden finden Sie die verschiedenen Regeln zur Groß- und Kleinschreibung:

* Alle Operatoren (and, or usw.) müssen in Kleinbuchstaben geschrieben werden. Beispiel: _`<expression1>`and`<expression2>`_ ist ein gültiger Ausdruck, _`<expression1>`AND`<expression2>`_ hingegen nicht.
* Bei allen Funktionsnamen ist die Groß-/Kleinschreibung zu berücksichtigen. Beispielsweise ist _inSegment()_ gültig, die Funktion _INSEGMENT()_ dagegen nicht.
* Bei Feldverweisen und konstanten Werten wird zwischen Groß- und Kleinschreibung unterschieden: Sie sind keine integrierten Elemente der Sprache (im Gegensatz zu Operatoren und Funktionen), sondern werden vom Endbenutzer verfasst.

## Zurückgegebener Ausdruckstyp{#section_gyc_435_53b}

Je nach Verwendungskontext kann der Ausdruckseditor verschiedene Werte zurückgeben.

| Verwendung des erweiterten Ausdruckseditors | Erwarteter zurückgegebener Ausdruckstyp |
|--- |--- |
| Bedingung (Bedingung der Datenquelle, Bedingung für das Datum) | Boolesch |
| Benutzerdefinierter Timer | dateTimeOnly |
| Zuordnung von Aktionsparametern | Beliebig |
