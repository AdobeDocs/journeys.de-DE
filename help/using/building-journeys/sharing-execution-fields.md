---
product: adobe campaign
title: Aktionsausführungsfelder für journeyStep-Ereignisse
description: Aktionsausführungsfelder für journeyStep-Ereignisse
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '367'
ht-degree: 100%

---

# Aktionsausführungsfelder für journeyStep-Ereignisse {#sharing-execution-fields}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


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

Beispielsweise wird eine E-Mail gesendet und beim ersten Versuch ein HTTP 500-Fehler zurückgegeben. Der Abruf wird erneut versucht, aber die Dauer der zwei Versuche liegt über der maximalen Wartezeit. Dann wird die Aktionsausführung als Zeitüberschreitung markiert. Der Aktionsteil sieht wie folgt aus:

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
* Kundin bzw. Kunde
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
