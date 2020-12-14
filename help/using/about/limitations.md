---
product: adobe campaign
solution: Journey Orchestration
title: Einschränkungen bei Journey Orchestration
description: Erfahren Sie mehr über die Einschränkungen bei Journey Orchestration.
translation-type: ht
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: ht
source-wordcount: '361'
ht-degree: 100%

---


# Einschränkungen {#limitations}

Im Zusammenhang mit der Verwendung von Journey Orchestration gibt es Einschränkungen.

## Allgemeine Aktionseinschränkungen

* Es gibt keine Einschränkung beim Versand. 
* Im Falle eines Fehlers werden systematisch zwei weitere Zustellversuche durchgeführt. Sie können die Anzahl der weiteren Zustellversuche nicht entsprechend der erhaltenen Fehlermeldung anpassen. 
* Mit dem integrierten **Reaktionsereignis** können Sie auf vordefinierte Aktionen reagieren (siehe diese [Seite](../building-journeys/reaction-events.md)). Wenn Sie auf eine Nachricht reagieren möchten, die über eine benutzerdefinierte Aktion gesendet wird, müssen Sie ein spezielles Ereignis konfigurieren. 
* Die Integration von Adobe Campaign Classic ist nicht als Produkt verfügbar.

## Einschränkungen bei den Journey-Versionen {#journey-versions-limitations}

* eine Journey, die in Version 1 mit einer Ereignisaktivität beginnt, kann in weiteren Versionen nicht mit etwas anderem als einem Ereignis beginnen. Sie können eine Journey nicht mit einem **Segmentqualifikationsereignis** starten.
* Eine Journey, die in Version 1 mit einer **Segmentqualifikationsaktivität** beginnt, muss in weiteren Versionen immer mit einer **Segmentqualifikation** beginnen.
* Das Segment und der Namespace, die unter **Segmentqualifikation** (erster Knoten) ausgewählt wurden, können in neuen Versionen nicht geändert werden.
* Die Regel für den Wiedereintritt muss in allen Journey-Versionen gleich sein.

## Segmentqualifikation {#segment-qualification}

* Die **Segmentqualifikationsaktivität** kann aufgrund von Durchsatzbeschränkungen nicht zusammen mit Transaktionsnachrichten in Adobe Campaign Standard verwendet werden. Weitere Informationen finden Sie in der [Adobe Campaign Standard – Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 

 

## Einschränkungen bei benutzerdefinierten Aktionen

* Die URL einer benutzerdefinierten Aktion unterstützt keine dynamischen Parameter. 
* Es werden nur POST- und PUT-Aufrufmethoden unterstützt. 
* Der Name des Abfrageparameters oder der Kopfzeile darf nicht mit „.“ oder „$“ beginnen. 
* IP-Adressen sind nicht zulässig. 
* Interne Adobe-Adressen (.adobe.) sind nicht zulässig.
 

## Einschränkungen bei Adobe Campaign-Aktionen

* Transaktionsnachrichten in Adobe Campaign Standard sind für eine bestimmte Instanz auf maximal 50.000 Nachrichten pro Stunde über alle Kanäle hinweg begrenzt. Weitere Informationen finden Sie in der [Adobe Campaign Standard – Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 

 

## Einschränkungen bei Ereignissen

* Streaming-Daten, die zur Initiierung einer Customer Journey verwendet werden, müssen innerhalb von Journey Orchestration konfiguriert werden, bevor eine eindeutige Orchestrierungs-ID abgerufen werden kann. Diese Orchestrierungs-ID muss an die Streaming-Payload angehängt werden, die in Adobe Experience Platform eingehen.
 

## Einschränkungen bei Datenquellen

* Externe Datenquellen können innerhalb einer Customer Journey genutzt werden, um externe Daten in Echtzeit zu suchen. Diese Quellen müssen über die REST-API nutzbar sein, JSON unterstützen und in der Lage sein, das Anfragevolumen zu verarbeiten.