---
title: getBestSendTime
description: Erfahren Sie mehr über die Funktion „getBestSendTime“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Liefert eine Vorhersage zur besten Versandzeit für eine E-Mail an einen Kontakt.

Diese Funktion nutzt einen Wert, der in der Plattform berechnet wird. Der Wert berechnet basierend auf dem bisherigen Verhalten die Neigung, in Zukunft auf eine E-Mail zu klicken oder diese zu öffnen. Beachten Sie, dass der Algorithmus zur Berechnung des Werts eine bestimmte Datenmenge benötigt, um zu funktionieren. Wenn nicht genügend Daten vorhanden sind, gilt die Standardzeit. Lesen Sie für weiterführende Informationen den Abschnitt [](../building-journeys/wait-activity.md).

Zur Verwendung dieser Funktion ist ein [Namespace](../event/selecting-the-namespace.md) erforderlich.

>[!NOTE]
>
>Beachten Sie, dass der Wert für die beste Versandzeit möglicherweise nicht verfügbar ist, wenn nicht genügend Daten zur Durchführung der Berechnung vorhanden sind. In diesem Fall werden Sie zum Zeitpunkt der Veröffentlichung darüber informiert, dass die Standardzeit gilt.

## Kategorie

Adobe Experience Platform

## Funktionssyntax

`getBestSendTime(<parameters>)`

## Parameter

| Parameter | Beschreibung | Typ |
|--- |--- |--- |
| Dauer | Zahl der Stunden, die zur Optimierung des E-Mail-Versands ab der aktuellen Zeit berücksichtigt werden sollen (max: 168) | `<integer>` |
| Optimierungstyp | &quot;open&quot; oder &quot;click&quot; | `<string>` |
| Standardwartezeit in Stunden | Für den Fall, dass keine prädiktiven Werte zur Versandzeit verfügbar sind | `<integer>` |

## Signatur und zurückgegebener Typ

`getBestSendTime(<integer>,<string>,<integer>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

## Beispiel

getBestSendTime(12,&quot;open&quot;,8)

Erklärung:

Die Funktion gibt die beste Zeit zum Senden einer Nachricht in den nächsten 12 Stunden zurück, um die Wahrscheinlichkeit zu erhöhen, dass sie der Kontakt in der Journey-Instanz öffnet. Wenn für die Durchführung der Berechnung nicht genügend Daten vorhanden sind, beträgt die zurückgegebene Zeit 8 Stunden ab der aktuellen Zeit.
