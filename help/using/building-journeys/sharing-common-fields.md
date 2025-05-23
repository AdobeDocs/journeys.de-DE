---
product: adobe campaign
title: Gemeinsame Felder für journeySteps-Ereignisse
description: Gemeinsame Felder für journeySteps-Ereignisse
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '627'
ht-degree: 100%

---

# Gemeinsame Felder für journeySteps-Ereignisse {#sharing-common-fields}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Dieses Mixin wird von journeyStepEvent und journeyStepProfileEvent geteilt.

Dies sind die gängigen XDM-Felder, die [!DNL Journey Orchestration] an Adobe Experience Platform sendet. Gemeinsame Felder werden für jeden Schritt gesendet, der während einer Journey verarbeitet wird. Für benutzerdefinierte Aktionen und Anreicherungen werden spezifischere Felder verwendet.

Einige dieser Felder sind nur in bestimmten Verarbeitungsmustern (Aktionsausführung, Datenabruf usw.) verfügbar, um die Größe von Ereignissen zu begrenzen.

## entrance

Gibt an, ob der Benutzer in die Journey eingetreten ist. Wenn nicht vorhanden, wird angenommen, dass der Wert „false“ lautet.

Typ: boolesch

Werte: wahr/falsch

## reentrance

Gibt an, ob der Benutzer in die Journey mit derselben Instanz erneut eingetreten ist. Wenn nicht vorhanden, wird angenommen, dass der Wert „false“ lautet.

Typ: boolesch

Werte: wahr/falsch

## instanceEnded

Gibt an, ob die Instanz beendet wurde (erfolgreich oder nicht).

Typ: boolesch

## eventID

Ereigniskennung in der Verarbeitung für die Schrittverarbeitung. Wenn es sich bei dem Ereignis um ein externes Ereignis handelt, ist der Wert dessen Ereignis-ID eventId. Wenn es sich bei dem Ereignis um ein internes Ereignis handelt, ist der Wert die interne eventId (wie z. B. scheduledNotificationReceived, executedAction).

Typ: Zeichenfolge

## nodeID

Kennung des Client-Knotens (von der Arbeitsfläche).

Typ: Zeichenfolge

## stepID

Eindeutige Kennung des Schritts, der gerade verarbeitet wird.

Typ: Zeichenfolge

## stepName

Name des Schritts, der gerade verarbeitet wird.

Typ: Zeichenfolge

## stepType

Art des Schritts.

Typ: Zeichenfolge

Mögliche Werte:

* Bedingung
* Aktion
* Planung
* Timer

## stepStatus

Status des Schritts, der den Status des Schritts darstellt, nachdem die Verarbeitung abgeschlossen (und das Schrittereignis ausgelöst) wurde.

Typ: Zeichenfolge

Der Status kann wie folgt lauten:

* ended: Der Schritt weist keine Transition auf und seine Verarbeitung wurde erfolgreich beendet.
* error: Bei der Schrittverarbeitung ist ein Fehler aufgetreten.
* transitions: Der Schritt wartet darauf, bis ein Ereignis durch Transition in einen anderen Schritt gelangt.
* capped: Der Schritt ist aufgrund eines Begrenzungsfehlers fehlgeschlagen, der während einer Aktion oder Anreicherung ausgelöst wurde.
* timedout: Der Schritt ist aufgrund eines Zeitüberschreitungsfehlers fehlgeschlagen, der während einer Aktion oder Anreicherung ausgelöst wurde.
* instanceTimedout: Der Schritt hat die Verarbeitung beendet, da die Instanz ihren Zeitüberschreitungswert erreicht hat.

## journeyID

Kennung der Journey.

Typ: Zeichenfolge

## journeyVersionID

Kennung der Journey-Version. Diese Kennung stellt bei journeyStepEvent den Identitätsverweis auf die Journey dar.

Typ: Zeichenfolge

## journeyVersionName

Name der Journey-Version.

Typ: Zeichenfolge

## journeyVersion

Version der Journey-Version.

Typ: Zeichenfolge

## instanceID

Interne Kennung der Journey-Instanz.

Typ: Zeichenfolge

## externalKey

Externer Schlüssel, der aus dem Ereignis zur Verarbeitung extrahiert wurde.

Typ: Zeichenfolge

## parentStepID

Kennung des übergeordneten Schritts des in der Instanz gerade verarbeiteten Schritts.

Typ: Zeichenfolge

## parentStepName

Name des übergeordneten Schritts des aktuellen Schritts.

Typ: Zeichenfolge

## parentTransitionID

Kennung der Transition, die die Instanz zum verarbeiteten Schritt geführt hat.

Typ: Zeichenfolge

## parentTransitionName

Name der Transition, die die Instanz zum verarbeiteten Schritt geführt hat.

Typ: Zeichenfolge

## inTest

Gibt an, ob sich die Journey im Testmodus befindet oder nicht.

Typ: boolesch

## processingTime

Gesamtdauer vom Eintritt des Instanzschritts bis zum Ende der Verarbeitung (in Millisekunden).

Typ: lang

## instanceType

Gibt den Instanztyp an (Batch oder unitär).

Typ: Zeichenfolge

Werte: batch/unitary

## recurrenceIndex

Index des Intervalls, wenn es sich bei der Journey um einen wiederkehrenden Batch-Vorgang handelt (erste Ausführung führt zu recurrenceIndex = 1).

Typ: lang

## isBatchToUnitary

Gibt an, ob diese unitäre Instanz von einer Batch-Instanz ausgelöst wurde.

Typ: boolesch

## batchExternalKey

Externer Schlüssel für das Batch-Ereignis.

Typ: Zeichenfolge

## batchInstanceID

Dies ist die Kennung der Batch-Instanz.

Typ: Zeichenfolge

## batchUnitaryBranchID

Wenn die Instanz von einer Batch-Instanz ausgelöst wurde, unitäre Verzweigungs-ID.

Typ: Zeichenfolge
