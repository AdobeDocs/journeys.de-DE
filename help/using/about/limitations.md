---
product: adobe campaign
title: Einschränkungen bei Journey Orchestration
description: Erfahren Sie mehr über die Einschränkungen bei Journey Orchestration.
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '609'
ht-degree: 100%

---

# Einschränkungen {#limitations}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._



Im Zusammenhang mit der Verwendung von Journey Orchestration gibt es Einschränkungen.

## Allgemeine Limits für Journey {#journeys-guardrails-journeys}

* Die Anzahl der Aktivitäten in einer Journey ist auf maximal 50 begrenzt. Die Anzahl der Aktivitäten wird im oberen linken Bereich der Journey-Arbeitsfläche angezeigt.
* Die Anzahl der **Live-Journeys** in einer Organisation ist auf maximal 100 pro Sandbox begrenzt. Wenn diese Grenze erreicht ist, können Sie keine neue Journey mehr veröffentlichen.

## Allgemeine Aktionseinschränkungen

* Im Falle eines Fehlers werden systematisch drei weitere Zustellversuche durchgeführt. Sie können die Anzahl der weiteren Zustellversuche nicht entsprechend der erhaltenen Fehlermeldung einstellen. 
* Mit dem integrierten **Reaktionsereignis** können Sie auf vordefinierte Aktionen reagieren (siehe diese [Seite](../building-journeys/reaction-events.md)). Wenn Sie auf eine Nachricht reagieren möchten, die über eine benutzerdefinierte Aktion gesendet wird, müssen Sie ein spezielles Ereignis konfigurieren. 

## Einschränkungen bei den Journey-Versionen {#journey-versions-limitations}

* Eine Journey, die in Version 1 mit einer Ereignisaktivität beginnt, kann in weiteren Versionen nicht mit etwas anderem als einem Ereignis beginnen. Sie können eine Journey nicht mit einem **Segmentqualifizierungsereignis** starten.
* Eine Journey, die in Version 1 mit einer **Segmentqualifizierungsaktivität** beginnt, muss in weiteren Versionen immer mit einer **Segmentqualifizierung** beginnen.
* Das Segment und der Namespace, die unter **Segmentqualifikation** (erster Knoten) ausgewählt wurden, können in neuen Versionen nicht geändert werden.
* Die Regel für den Wiedereintritt muss in allen Journey-Versionen gleich sein.

## Segmentqualifikation {#segment-qualification}

* Die **Segmentqualifikationsaktivität** kann aufgrund von Durchsatzbeschränkungen nicht zusammen mit Transaktionsnachrichten in Adobe Campaign Standard verwendet werden. Weitere Informationen finden Sie in der [Adobe Campaign Standard – Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 

 
## Einschränkungen bei benutzerdefinierten Aktionen

* Die URL einer benutzerdefinierten Aktion unterstützt keine dynamischen Parameter. 
* Es werden nur POST- und PUT-Aufrufmethoden unterstützt. 
* Der Name des Abfrageparameters oder der Kopfzeile darf nicht mit &quot;.&quot; beginnen oder &quot;$&quot;. 
* IP-Adressen sind nicht zulässig. 
* Interne Adobe-Adressen (.adobe.) sind nicht zulässig.
 
## Einschränkungen bei Adobe Campaign-Aktionen

* Transaktionsnachrichten in Adobe Campaign Standard sind für eine bestimmte Instanz auf maximal 50.000 Nachrichten pro Stunde über alle Kanäle hinweg begrenzt. Weitere Informationen finden Sie in der [Adobe Campaign Standard – Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 

 
## Einschränkungen bei Ereignissen

* Für systemgenerierte Ereignisse müssen Streaming-Daten, die zur Initiierung einer Customer Journey verwendet werden, zunächst innerhalb von Journey Orchestration konfiguriert werden, um eine eindeutige Orchestrierungs-ID zu erhalten. Diese Orchestrierungs-ID muss an die Streaming-Payload angehängt werden, die in Adobe Experience Platform eingeht. Diese Einschränkung gilt nicht für regelbasierte Ereignisse.
 
## Einschränkungen bei Datenquellen

* Externe Datenquellen können in einer Customer Journey genutzt werden, um externe Daten in Echtzeit zu suchen. Diese Quellen müssen über die REST-API nutzbar sein, JSON unterstützen und in der Lage sein, das Anfragevolumen zu verarbeiten.

## Journeys, die gleichzeitig mit der Erstellung eines Profils beginnen {#journeys-limitation-profile-creation}

In Adobe Experience Platform gibt es eine Verzögerung bei der API-basierten Profilerstellung/-aktualisierung. Das Service Level Target (SLT) in Bezug auf die Latenzzeit ist &lt; 1 Minute von der Aufnahme bis zum Unified Profile für das 95. Perzentil der Anfragen bei einem Volumen von 20.000 Anfragen pro Sekunde (RPS).

Wenn eine Journey gleichzeitig mit einer Profilerstellung ausgelöst wird und sofort Informationen vom Profil-Service prüft/abruft, funktioniert sie möglicherweise nicht richtig.

Sie können aus einer der beiden folgenden Lösungen wählen:

* Fügen Sie nach dem ersten Ereignis eine Warteaktivität hinzu, um Adobe Experience Platform ausreichend Zeit zu geben, um die Aufnahme in den Profil-Service durchzuführen.

* Richten Sie eine Journey ein, bei der das Profil nicht sofort genutzt wird. Wenn die Journey beispielsweise dazu dient, eine Kontoerstellung zu bestätigen, könnte das Erlebnisereignis Informationen enthalten, die zum Senden der ersten Bestätigungsnachricht benötigt werden (Vorname, Nachname, E-Mail-Adresse usw).
