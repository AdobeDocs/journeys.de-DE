---
product: adobe campaign
solution: Journey Orchestration
title: Einschränkungen der Journey Orchestration
description: Weitere Informationen zu Einschränkungen bei der Journey Orchestration
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 27%

---


# Einschränkungen {#limitations}

Hier sind Einschränkungen im Zusammenhang mit der Verwendung von Journey Orchestration.

## Allgemeine Aktionseinschränkungen

* Es gibt keinen sendenden Einschränken. 
* Im Falle eines Fehlers werden systematisch zwei weitere Zustellversuche durchgeführt. Sie können die Anzahl der weiteren Zustellversuche nicht entsprechend der erhaltenen Fehlermeldung anpassen. 
* The built-in **Reaction** event allows you to react to out-of-the-box actions (see this [page](../building-journeys/reaction-events.md)). Wenn Sie auf eine Nachricht reagieren möchten, die über eine benutzerdefinierte Aktion gesendet wird, müssen Sie ein spezielles Ereignis konfigurieren. 
* Es gibt keine Adobe Campaign Classic-produktisierte Integration.

## Einschränkungen für Reiseversionen {#journey-versions-limitations}

* eine Reise, die mit einer Ereignis-Aktivität in v1 beginnt, kann nicht mit etwas anderem als einem Ereignis in weiteren Versionen Beginn werden. Eine Reise mit einem Ereignis für die **Segmentqualifikation** kann nicht Beginn werden.
* eine Reise, die mit einer **Segmentqualifizierungs** -Aktivität in v1 beginnt, muss immer mit einer **Segmentqualifikation** in weiteren Versionen Beginn haben.
* Das in der **Segmentqualifikation** (erster Knoten) ausgewählte Segment und Namensraum können in neuen Versionen nicht geändert werden.
* Die Regel für den Wiedereintritt muss in allen Reiseversionen gleich sein.

## Segmentqualifikation {#segment-qualification}

* Die Aktivität für die **Segmentqualifizierung** kann aufgrund von Durchsatzbeschränkungen nicht zusammen mit Adobe Campaign Standard Transactional Messaging verwendet werden. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 
 

## Einschränkungen für benutzerdefinierte Aktionen

* Die URL der benutzerdefinierten Aktion unterstützt keine dynamischen Parameter. 
* Es werden nur POST- und PUT-Aufrufmethoden unterstützt. 
* Der Name des Abfrageparameters oder der Kopfzeile darf nicht mit „.“ oder „$“ beginnen. 
* IP-Adressen sind nicht zulässig. 
* Interne Adobe-Adressen (.adobe.) sind nicht zulässig.
 

## Einschränkungen bei Adobe Campaign-Aktionen

* Adobe Campaign Standard Transactional Messaging verfügt über eine maximale Anzahl von 50 000 Nachrichten pro Stunde über Kanal für eine bestimmte Instanz. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 
 

## Einschränkungen bei Ereignissen

* Streaming-Daten, die zur Initiierung einer Kundenreise verwendet werden, müssen innerhalb der Journey Orchestration konfiguriert werden, bevor eine eindeutige Orchester-ID abgerufen werden kann. Diese Organisations-ID muss an die Streaming-Nutzlast angehängt werden, die nach Adobe Experience Platform kommt.
 

## Einschränkungen bei Datenquellen

* Externe Datenquellen können innerhalb einer Customer Journey genutzt werden, um externe Daten in Echtzeit zu suchen. Diese Quellen müssen über die REST-API nutzbar sein, JSON unterstützen und in der Lage sein, das Anforderungsvolumen zu verarbeiten.