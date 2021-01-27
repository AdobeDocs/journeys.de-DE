---
product: adobe campaign
solution: Journey Orchestration
title: Aktionsausführungsfelder für journeyStep-Ereignisse
description: Aktionsausführungsfelder für journeyStep-Ereignisse
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 100%

---


# Aktionsausführungsfelder für journeyStep-Ereignisse {#sharing-execution-fields}

Dieses Mixin wird von journeyStepEvent und journeyStepProfileEvent geteilt.

Wenn für den Schritt eine Aktion verarbeitet werden muss, werden diese Felder der Ereignis-Payload hinzugefügt.

## actionID

Kennung der ausgeführten Aktion.

Typ: Zeichenfolge

## actionName

Name der Aktion. Wenn kein Name festgelegt wurde, wird der stepName verwendet.

Typ: Zeichenfolge

## actionType

Art der Aktion.

Typ: Zeichenfolge

## actionParameterized

Gibt an, ob die Aktion parametrisiert wurde oder nicht.

Typ: boolesch

## actionExecutionTime

Dauer (in Millisekunden), die zum Ausführen einer aktuellen Aktion benötigt wird.

Typ: lang

## actionExecutionError

Fehlertyp, der beim Aufrufen der Aktion auftritt.

Typ: Zeichenfolge

Werte:
* http
* capping
* timeout
* error

## actionExecutionErrorCode

Code für Fehler bei der Ausführung der Aktion. Wird angezeigt, wenn der Fehler einen Code enthält, z. B. HTTP-Code.

Typ: Zeichenfolge

## actionExecutionOriginError

Eine Zeitüberschreitung kann in zwei Fällen auftreten:

* beim ersten Versuch der Ausführung einer Aktion; in diesem Fall ist die Ausführung noch nicht abgeschlossen, sodass kein zugrunde liegender Fehler vorliegt.
* bei einer Wiederholung; in diesem Fall beschreibt der ActionExecOrigError/actionExecOrigErrorCode den Fehler, der beim Versuch vor der Wiederholung aufgetreten ist.

Beispielsweise wird eine E-Mail gesendet und beim ersten Versuch ein HTTP 500-Fehler zurückgegeben. Der Abruf wird erneut versucht, aber die Dauer der zwei Versuche liegt über der Zeitüberschreitung. Dann wird die Aktionsausführung als Zeitüberschreitung markiert. Der Aktionsteil sieht wie folgt aus:

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

Typ: Zeichenfolge

## actionExecutionOriginCode

Fehler-Code von actionExecOrigError.

Typ: Zeichenfolge

## actionBusinessType

Gibt die Art der Aktion an.

Werte:

* builtin
* ACS Email
* ACS SMS
* ACS Push
* customer
* Epsilon
* ...

Typ: Zeichenfolge

## deliveryJobID

Beschreibt die Versand-Vorgangskennung für die Batch-Journey.

Typ: Zeichenfolge

## batchDeliveryID

Beschreibt die Versandkennung für die Batch-Journey.

Typ: Zeichenfolge

## fromSegmentTrigger

Beschreibt, ob die Batch-Journey im Zielgruppensegment ausgelöst wird.

Typ: boolesch

## actionSchedulerCount

Anzahl der Planungs-Benachrichtigungsanfragen, die bei der Schrittverarbeitung an den Planungsdienst gesendet werden.

Typ: lang
