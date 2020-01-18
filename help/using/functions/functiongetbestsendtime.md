---
title: getBestSendTime
description: Erfahren Sie mehr über die Funktion getBestSendTime
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Bietet eine Prognosezeit für die beste Zeit, um eine E-Mail an eine Einzelperson zu senden.

Diese Funktion verwendet einen Wert, der in der Plattform berechnet wird. Das Ergebnis berechnet die Neigung, in Zukunft basierend auf dem bisherigen Verhalten auf eine E-Mail zu klicken oder sie zu öffnen. Beachten Sie, dass der Algorithmus, der das Ergebnis berechnet, eine bestimmte Datenmenge benötigt, um zu funktionieren. Wenn nicht genügend Daten vorhanden sind, gilt die Standardzeit. For more information, see [](../building-journeys/wait-activity.md).

Für die Verwendung dieser Funktion ist ein [Namespace](../event/selecting-the-namespace.md) erforderlich.

>[!NOTE]
>
>Beachten Sie, dass die beste Sende-Zeit-Bewertung nicht verfügbar sein kann, wenn nicht genügend Daten vorhanden sind, um die Berechnung durchzuführen. In diesem Fall werden Sie zum Zeitpunkt der Veröffentlichung darüber informiert, dass die Standardzeit gilt.

## Kategorie

Adobe Experience Platform

## Funktionssyntax

`getBestSendTime(<parameters>)`

## Parameter

| Parameter | Description | Typ |
|--- |--- |--- |
| Zeit | Anzahl der Stunden, die ab der aktuellen Zeit zu berücksichtigen sind (max: 168) zur Optimierung des E-Mail-Versands | `<integer>` |
| Optimierungstyp | &quot;open&quot;oder &quot;click&quot; | `<string>` |
| Standardzeit in Stunden | Für den Fall, dass keine Prognosewerte für die Sendezeit verfügbar sind | `<integer>` |

## Unterschrift und zurückgegebener Typ

`getBestSendTime(<integer>,<string>,<integer>)`

Gibt dateTime zurück.

## Beispiel

getBestSendTime(12,&quot;open&quot;,8)

Erklärung:

Die Funktion gibt die beste Zeit zurück, um eine Nachricht in den nächsten 12 Stunden zu senden, um die Wahrscheinlichkeit zu optimieren, mit der die Person in der Reiseinstanz sie öffnen kann. Wenn nicht genügend Daten vorhanden sind, um die Berechnung durchzuführen, beträgt die zurückgegebene Zeit 8 Stunden ab der aktuellen Zeit.
