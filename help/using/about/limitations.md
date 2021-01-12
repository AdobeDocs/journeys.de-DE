---
product: adobe campaign
solution: Journey Orchestration
title: Einschränkungen bei Journey Orchestration
description: Erfahren Sie mehr über die Einschränkungen bei Journey Orchestration.
translation-type: tm+mt
source-git-commit: f562d4a967e6551d3b8a1bc4dbddbf01da9b3e70
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 70%

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

* Transaktionsnachrichten in Adobe Campaign Standard sind für eine bestimmte Instanz auf maximal 50.000 Nachrichten pro Stunde über alle Kanäle hinweg begrenzt. Weitere Informationen finden Sie in der [Adobe Campaign Standard – Produktbeschreibung](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 

 

## Einschränkungen bei Ereignissen

* Streaming-Daten, die zur Initiierung einer Customer Journey verwendet werden, müssen innerhalb von Journey Orchestration konfiguriert werden, bevor eine eindeutige Orchestrierungs-ID abgerufen werden kann. Diese Orchestrierungs-ID muss an die Streaming-Payload angehängt werden, die in Adobe Experience Platform eingehen.
 

## Einschränkungen bei Datenquellen

* Externe Datenquellen können innerhalb einer Customer Journey genutzt werden, um externe Daten in Echtzeit zu suchen. Diese Quellen müssen über die REST-API nutzbar sein, JSON unterstützen und in der Lage sein, das Anfragevolumen zu verarbeiten.

## Journey, die gleichzeitig mit der Erstellung eines Profils beginnen{#journeys-limitation-profile-creation}

Es gibt eine Verzögerung bei der Erstellung/Aktualisierung von API-basierten Profilen in Adobe Experience Platform. Die Service Level Zielgruppe (SLT) in Bezug auf die Latenzzeit beträgt &lt; 1 Min. von der Erfassung zu Unified Profil für 95. Perzentil der Anforderungen bei einem Volumen von 20 K Anforderungen pro Sekunde (RPS).

Wenn eine Journey gleichzeitig zur Erstellung eines Profils ausgelöst wird und sofort Informationen vom Profil-Dienst überprüft/abgerufen werden, funktioniert sie möglicherweise nicht ordnungsgemäß.

Sie können aus einer der beiden folgenden Lösungen wählen:

* hinzufügen eine Wartezeit-Aktivität nach dem ersten Ereignis, um Adobe Experience Platform die Zeit zu geben, die es benötigt, um die Erfassung an Profil Service durchzuführen.

* Richten Sie eine Journey ein, die das Profil nicht sofort nutzt. Wenn die Journey beispielsweise zur Bestätigung einer Kontoerstellung konzipiert ist, könnte das Erlebnis-Ereignis Informationen enthalten, die zum Senden der ersten Bestätigungsmeldung (Vorname, Nachname, E-Mail-Adresse usw.) erforderlich sind.