---
product: adobe campaign
solution: Journey Orchestration
title: Datenabruffelder für journeyStep-Ereignisse
description: Datenabruffelder für journeyStep-Ereignisse
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---


# Datenabruffelder für journeyStep-Ereignisse {#sharing-fetch-fields}

Dieses Mixin wird von journeyStepEvent und journeyStepProfileEvent geteilt.

Bei einer Schrittverarbeitung kann es N Datenabrufe für Feldergruppen geben.

## fetchTotalTime

Gesamtdauer, die bei der Schrittverarbeitung für das Abrufen von Daten gebraucht wurde (in Millisekunden).

Typ: lang

## fetchTypeInError

Definiert, ob sich der Abruffehler in Adobe Experience Plattform oder einer benutzerdefinierten Datenquelle befindet.

Typ: Zeichenfolge

Werte:
* aep
* custom

## fetchError

Fehlertyp, der bei der Verarbeitung des Datenabrufs auftritt.

Typ: Zeichenfolge

Werte:
* http
* capping
* timedout
* error

## fetchErrorCode

Code für den Fehler beim Abrufen. Wird angezeigt, wenn der Fehler einen Code enthält, z. B. HTTP-Code. Wenn der actionExecError beispielsweise http lautet, stellt der Code 404 den HTTP 404-Fehler dar.

Typ: Zeichenfolge

## fetchOriginError

Eine Zeitüberschreitung kann in zwei Fällen auftreten:

* beim ersten Versuch der Ausführung der Aktion; in diesem Fall ist die Ausführung noch nicht abgeschlossen, sodass kein zugrunde liegender Fehler vorliegt.
* bei einer Wiederholung; in diesem Fall beschreibt der ActionExecOrigError/actionExecOrigErrorCode den Fehler, der beim Versuch vor der Wiederholung aufgetreten ist.

Beispielsweise werden Daten vom Unified Profil Service abgerufen und wird beim ersten Versuch ein HTTP 500-Fehler zurückgegeben. Der Abruf wird erneut versucht, aber die Dauer der zwei Versuche liegt über der Zeitüberschreitung. Dann wird die Aktionsausführung als Zeitüberschreitung markiert. Der Aktionsteil sieht wie folgt aus:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Typ: Zeichenfolge

## fetchOriginErrorCode

Der vom System, das von [!DNL Journey Orchestration] abgefragt wird, bereitgestellte Fehler-Code. Dieser kann zum Beispiel 404, 500 usw. lauten.

Typ: Zeichenfolge

## fetchCount

Wie oft die Daten abgerufen werden, unabhängig vom Typ der Quelle.

Typ: lang

## fetchPlatformTotalTime

Gesamtdauer, die zum Abrufen der Daten von Adobe Experience Platform benötigt wird (in Millisekunden). Hinweis: Diese Dauer berechnet sich vom Zeitpunkt, an dem die Engine das Anreicherungsereignis an den Anreicherungsdienst sendet, bis zu dem Zeitpunkt, an dem die Engine die Antwort erhält.

Typ: lang

## fetchPlatformCount

Wie oft die Daten von Adobe Experience Platform abgerufen werden.

Typ: lang

## fetchCustomTotalTime

Dauer des Abrufs der benutzerspezifischen Daten (in Millisekunden). Hinweis: Diese Dauer berechnet sich vom Zeitpunkt, an dem die Engine das Anreicherungsereignis an den Anreicherungsdienst sendet, bis zu dem Zeitpunkt, an dem die Engine die Antwort erhält

Typ: lang

## fetchCustomCount

Wie oft die benutzerdefinierten Daten von externen Systemen abgerufen werden.

Typ: lang
