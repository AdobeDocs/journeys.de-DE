---
title: Aktionsausführungsfelder für Ereignis von "travelStep"
description: Aktionsausführungsfelder für Ereignis von "travelStep"
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Aktionsausführungsfelder für Ereignis von &quot;travelStep&quot; {#sharing-execution-fields}

Dieses Mixin wird von &quot;travelStepEvent&quot;und &quot;travelStepProfileEvent&quot;freigegeben.

Wenn für den Schritt eine Aktion verarbeitet werden muss, werden diese Felder der Ereignis-Nutzlast hinzugefügt.

## actionID

ID der ausgeführten Aktion.

Typ: string

## actionName

Name der Aktion. Wenn kein Name festgelegt wurde, wird stepName verwendet.

Typ: string

## actionType

Typ der Aktion.

Typ: string

## actionParameterized

Gibt an, ob die Aktion parametrisiert wurde.

Typ: boolesch

## actionExecutionTime

Die Zeit (in Millisekunden), die zum Ausführen einer aktuellen Aktion benötigt wird.

Typ: long

## actionExecutionError

Fehlertyp, der beim Aufruf der Aktion auftritt.

Typ: string

Werte:
* http
* capping
* timeout
* error

## actionExecutionErrorCode

Code für Aktionsausführungsfehler. Wird angezeigt, wenn der Fehler einen Code enthält, z. B. einen HTTP-Code.

Typ: string

## actionExecutionOriginError

Ein Timeout kann in zwei Fällen auftreten:

* beim ersten Versuch wird eine Aktion ausgeführt. In diesem Fall ist die Ausführung noch nicht abgeschlossen, sodass kein zugrunde liegender Fehler vorliegt
* bei einer Wiederholung: In diesem Fall beschreibt der ActionExecOrigError/actionExecOrigErrorCode den Fehler, der beim Versuch vor dem Wiederholen aufgetreten ist.

Beispielsweise wird beim ersten Versuch eine E-Mail gesendet und ein HTTP 500-Fehler zurückgegeben. Der Abruf wird erneut versucht, aber die Dauer der 2 Versuche überschreitet den Timeout. Dann wird die Aktionsausführung als Timeout getaggt. Der Aktionsbereich sieht wie folgt aus:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Typ: string

## actionExecutionOriginCode

Fehlercode des actionExecOrigError.

Typ: string

## actionBusinessType

Gibt die Art der Aktion an.

Werte:

* builtin
* ACS-E-Mail
* ACS SMS
* ACS Push
* Kunde
* Epsilon
* ...

Typ: string

## deliveryJobID

Hier wird die Versand-Job-ID für die Batch-Reise beschrieben.

Typ: string

## batchDeliveryID

Hier wird die Versand-ID für die Batch-Reise beschrieben.

Typ: string

## fromSegmentTrigger

Dies beschreibt, ob die Batch-Reise aus dem Audience-Segment ausgelöst wird.

Typ: boolesch

## actionSchedulerCount

Anzahl der Planungen-Benachrichtigungsanforderungen, die während der Schrittverarbeitung an den Planung-Dienst gesendet werden.

Typ: long
