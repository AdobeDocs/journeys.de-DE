---
title: Wegeysteps Ereignisse gemeinsame Felder
description: Wegeysteps Ereignisse gemeinsame Felder
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
source-wordcount: '583'
ht-degree: 0%

---


# Wegeysteps Ereignisse gemeinsame Felder {#sharing-common-fields}

Dieses Mixin wird von &quot;travelStepEvent&quot;und &quot;travelStepProfileEvent&quot;freigegeben.

Dies sind die gängigen XDM-Felder, die Journey Orchestration an die Adobe-Datenplattform sendet. Gemeinsame Felder werden für jeden Schritt gesendet, der während einer Reise verarbeitet wird. Für benutzerdefinierte Aktionen und Anreicherungen werden spezifischere Felder verwendet.

Einige dieser Felder sind nur in bestimmten Verarbeitungsmustern verfügbar (Aktionsausführung, Datenabruf usw.) um die Größe der Ereignis zu begrenzen.

## Eingang

Gibt an, ob der Benutzer die Reise aufgerufen hat. Ist der Wert nicht vorhanden, wird angenommen, dass er &quot;false&quot;ist.

Typ: boolesch

Werte: true/false

## reaktivieren

Gibt an, ob der Benutzer die Reise mit derselben Instanz erneut aufgerufen hat. Ist der Wert nicht vorhanden, wird angenommen, dass er &quot;false&quot;ist.

Typ: boolesch

Werte: true/false

## instanceEnded

Gibt an, ob die Instanz beendet wurde (erfolgreich oder nicht).

Typ: boolesch

## eventID

Ereignis-ID in der Verarbeitung für die Schrittverarbeitung. Wenn es sich bei dem Ereignis um ein externes Element handelt, ist der Wert eventId. Wenn es sich bei dem Ereignis um ein internes handelt, ist der Wert die interne eventId (wie z. B. geplanteNotificationReceived, executeAction usw.).

Typ: string

## nodeID

Client-Knoten-ID (aus der Arbeitsfläche).

Typ: string

## stepID

Eindeutige ID des Schritts, der derzeit verarbeitet wird.

Typ: string

## stepName

Name des Schritts, der derzeit verarbeitet wird.

Typ: string

## stepType

Typ des Schritts.

Typ: string

Mögliche Werte:

* Bedingung
* Aktion
* Planung
* Timer

## stepStatus

Status des Schritts, der den Status des Schritts darstellt, wenn die Verarbeitung abgeschlossen ist (und das step-Ereignis ausgelöst wird).

Typ: string

Der Status kann sein:

* ended: der Schritt hat keine Transition und seine Verarbeitung wurde erfolgreich beendet.
* error: bei der Schrittverarbeitung ist ein Fehler aufgetreten.
* Transitionen: der Schritt wartet, bis ein Ereignis zur Transition zu einem anderen Schritt führt.
* begrenzt: der Schritt bei einem Capping-Fehler fehlgeschlagen ist, der während einer Aktion oder Anreicherung ausgelöst wurde.
* timedout: der Schritt bei einem Timeout-Fehler, der während einer Aktion oder Anreicherung ausgelöst wurde, fehlgeschlagen ist.
* instanceTimeout: der Schritt die Verarbeitung beendet hat, da die Instanz ihren Timeout erreicht hat.

## travelID

ID der Reise.

Typ: string

## travelVersionID

ID der Reiseversion. Diese ID stellt den Identitätsverweis auf die Reise dar, im Fall des &quot;travelStepEvent&quot;.

Typ: string

## travelVersionName

Name der Reiseversion.

Typ: string

## travelVersion

Version der Reiseversion.

Typ: string

## instanceID

Interne ID der Reiseinstanz.

Typ: string

## externalKey

Externer Schlüssel, der aus dem Ereignis extrahiert wurde, um es zu verarbeiten.

Typ: string

## parentStepID

Schritt-ID des übergeordneten Elements des aktuellen verarbeiteten Schritts in der Instanz.

Typ: string

## parentStepName

Schrittname des übergeordneten Elements des aktuellen Schritts.

Typ: string

## parentTransitionID

ID der Transition, die die Instanz zum verarbeiteten Schritt gebracht hat.

Typ: string

## parentTransitionName

Name der Transition, die die Instanz zum verarbeiteten Schritt gebracht hat.

Typ: string

## inTest

Angabe, ob sich diese Reise im Prüfmodus befindet oder nicht.

Typ: boolesch

## processingTime

Gesamtdauer in Millisekunden vom Instanzschritteingang bis zum Ende der Verarbeitung.

Typ: long

## instanceType

Gibt den Instanztyp an, wenn es sich um einen Stapel oder eine Einheit handelt.

Typ: string

Werte: Batch/Einheit

## referrenceIndex

Index der Wiederholung, wenn es sich bei der Reise um einen Stapel und einen wiederkehrenden Vorgang handelt (erste Ausführung hat returnIndex = 1).

Typ: long

## isBatchToUnitary

Gibt an, ob diese einmalige Instanz von einer Stapelinstanz ausgelöst wurde.

Typ: boolesch

## batchExternalKey

Externer Schlüssel zum Batch-Ereignis.

Typ: string

## batchInstanceID

dies ist die ID der Stapelinstanz.

Typ: string

## batchUnitaryBranchID

wenn die Instanz von einer Stapelinstanz ausgelöst wurde, eine einheitliche Zweig-ID.

Typ: string
