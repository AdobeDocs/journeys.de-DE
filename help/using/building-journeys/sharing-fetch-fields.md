---
title: JourneyStep-Ereignisse - Datenabruf von Feldern
description: JourneyStep-Ereignisse - Datenabruf von Feldern
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---


# JourneyStep-Ereignisse - Datenabruf von Feldern {#sharing-fetch-fields}

Dieses Mixin wird von &quot;travelStepEvent&quot;und &quot;travelStepProfileEvent&quot;freigegeben.

Während einer Schrittverarbeitung können N-Daten für Feldgruppen abgerufen werden.

## fetchTotalTime

Gesamtdauer, die während der Schrittverarbeitung beim Abrufen von Daten verbracht wurde, in Millisekunden.

Typ: long

## fetchTypeInError

Definiert, ob sich der Fehler &quot;Abrufen in&quot;auf der Plattform oder in einer benutzerdefinierten Datenquelle befindet.

Typ: string

Werte:
* aep
* custom

## fetchError

Fehlertyp, der bei der Verarbeitung des Datenabrufs auftritt.

Typ: string

Werte:
* http
* capping
* timedout
* error

## fetchErrorCode

Code für den Abruf-Fehler. Wird angezeigt, wenn der Fehler einen Code enthält, z. B. einen HTTP-Code. Wenn beispielsweise actionExecError http lautet, stellt der Code 404 den HTTP 404-Fehler dar.

Typ: string

## fetchOriginError

Ein Timeout kann in zwei Fällen auftreten:

* beim ersten Versuch die Aktion ausgeführt wird. In diesem Fall ist die Ausführung noch nicht abgeschlossen, sodass kein zugrunde liegender Fehler vorliegt
* bei einer Wiederholung: In diesem Fall beschreibt der ActionExecOrigError/actionExecOrigErrorCode den Fehler, der beim Versuch vor dem Wiederholen aufgetreten ist.

Beispielsweise werden Daten vom Unified Profil Service abgerufen und beim ersten Versuch wird ein HTTP 500-Fehler zurückgegeben. Der Abruf wird erneut versucht, aber die Dauer der 2 Versuche überschreitet den Timeout. Dann wird die Aktionsausführung als Timeout getaggt. Der Aktionsbereich sieht wie folgt aus:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Typ: string

## fetchOriginErrorCode

Der vom System bereitgestellte Fehlercode [!DNL Journey Orchestration] fragt ab. Zum Beispiel kann es ein 404, 500 usw. sein.

Typ: string

## fetchCount

Wie oft die Daten abgerufen werden, unabhängig vom Typ der Quelle.

Typ: long

## fetchPlatformTotalTime

Die Gesamtdauer, die zum Abrufen der Daten von der Datenplattform in Millisekunden benötigt wird. Bemerkung: dieser Zeitraum wird berechnet, wenn die Engine das Ereignis der Anreicherung an den Anreicherung-Dienst sendet und die Antwort erhält.

Typ: long

## fetchPlatformCount

Wie oft die Daten von der Plattform abgerufen werden.

Typ: long

## fetchCustomTotalTime

Zeit zum Abrufen der benutzerspezifischen Daten in Millis. Bemerkung: diese Zeitdauer berechnet wird, ab dem die Engine das Ereignis der Anreicherung an den Anreicherung-Dienst sendet und die Antwort erhält

Typ: long

## fetchCustomCount

Wie oft die benutzerdefinierten Daten von externen Systemen abgerufen werden.

Typ: long
