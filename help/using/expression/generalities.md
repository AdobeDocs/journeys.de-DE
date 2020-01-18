---
title: Allgemein
description: Erfahren Sie mehr über die erweiterten Ausdrucksgenerationen
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


# Allgemein {#concept_rcy_qj5_dgb}

## Klammern und Ausdruckspriorität{#section_edf_fks_bgb}

Klammern können verwendet werden, um einen komplexen Ausdruck lesbarer zu machen. _(&lt;Ausdruck>)_ entspricht _&lt;Ausdruck>_. Mit Klammern können auch die Bewertungsreihenfolge und die Assoziativität definiert werden.

Die Ausdrücke werden von links nach rechts ausgewertet. Die Assoziativität bei arithmetischen Operatoren muss angewendet werden: Multiplikationen und Divisionen haben Vorrang vor Additionen und Subtraktionen. Um eine bestimmte Reihenfolge durchzusetzen, müssen Klammern hinzugefügt werden, um die Vorgänge abzugrenzen. Beispiel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Ausdruck | Bewertung |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; hat Vorrang vor &#39;+&#39;: 2 * 10 wird bewertet → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Die Klammern ändern die Priorität: (4 + 2) wird bewertet → 6</li><li> 6 * 10 → 60</li></ul> |

## Groß-/Kleinschreibung{#section_lrb_xh5_dgb}

Im Folgenden finden Sie die verschiedenen Regeln zur Beachtung von Groß- und Kleinschreibung:

* Alle Operatoren (und, oder, usw.) sollte in Kleinbuchstaben geschrieben werden. Beispiel: _`<expression1>`und`<expression2>`_ist ein gültiger Ausdruck, der Ausdruck_`<expression1>` AND nicht `<expression2>`_ .
* Bei allen Funktionsnamen wird die Groß-/Kleinschreibung beachtet. Beispielsweise ist _getBestSendTime()_ gültig, die Funktion _GETBESTSENDTIME()_ dagegen nicht.
* Bei Feldverweisen und Konstantenwerten wird zwischen Groß- und Kleinschreibung unterschieden: sie sind keine integrierten Elemente der Sprache (im Gegensatz zu Operatoren und Funktionen), werden sie vom Endbenutzer verfasst.

## Rückgegebener Ausdruckstyp{#section_gyc_435_53b}

Je nach Verwendungskontext kann der Ausdruckseditor verschiedene Werte zurückgeben.

| Erweiterte Verwendung des Ausdruckseditors | Erwarteter zurückgegebener Ausdruckstyp |
|--- |--- |
| Bedingung (Datenquellenbedingung, Datumsbedingung) | boolean |
| Benutzerdefinierter Timer | dateTimeOnly |
| Benutzerdefinierte Zeitzone | timeZone oder Zeichenfolge (z. B. Europa/Paris) |
| Zuordnung von Aktionsparametern | Beliebige |
