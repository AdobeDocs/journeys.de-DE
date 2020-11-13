---
title: Einschränkungen der Journey Orchestration
description: Weitere Informationen zu Einschränkungen bei der Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: f45069225b284fe47e2acaccb4aa5d34fe171f35
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 33%

---


# Einschränkungen {#limitations}

Hier sind Einschränkungen im Zusammenhang mit der Verwendung von Journey Orchestration.

## Allgemeine Aktionseinschränkungen

* Es gibt keinen sendenden Einschränken. 
* Im Falle eines Fehlers werden systematisch zwei weitere Zustellversuche durchgeführt. Sie können die Anzahl der weiteren Zustellversuche nicht entsprechend der erhaltenen Fehlermeldung anpassen. 
* The built-in **Reaction** event allows you to react to out-of-the-box actions (see this [page](../building-journeys/reaction-events.md)). Wenn Sie auf eine Nachricht reagieren möchten, die über eine benutzerdefinierte Aktion gesendet wird, müssen Sie ein spezielles Ereignis konfigurieren. 
* Es gibt keine Adobe Campaign Classic-produktisierte Integration.
 
## Einschränkungen für benutzerdefinierte Aktionen

* Die URL der benutzerdefinierten Aktion unterstützt keine dynamischen Parameter. 
* Es werden nur POST- und PUT-Aufrufmethoden unterstützt. 
* Der Name des Abfrageparameters oder der Kopfzeile darf nicht mit „.“ oder „$“ beginnen. 
* IP-Adressen sind nicht zulässig. 
* Interne Adobe-Adressen (.adobe.) sind nicht zulässig.
 

## Einschränkungen bei Adobe Campaign-Aktionen

* Adobe Campaign Standard Transactional Messaging verfügt über eine maximale Anzahl von 50 000 Nachrichten pro Stunde über Kanal für eine bestimmte Instanz. See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html). 
* Die Aktivität für die **Segmentqualifizierung** sollte aufgrund von Durchsatzbeschränkungen nicht in Verbindung mit Adobe Campaign Standard Transactional Messaging verwendet werden.
 
## Einschränkungen bei Ereignissen

* Streaming-Daten, die zur Initiierung einer Kundenreise verwendet werden, müssen innerhalb der Journey Orchestration konfiguriert werden, bevor eine eindeutige Orchester-ID abgerufen werden kann. Diese Organisations-ID muss an die Streaming-Nutzlast angehängt werden, die nach Adobe Experience Platform kommt.
 

## Einschränkungen bei Datenquellen

* Externe Datenquellen können innerhalb einer Customer Journey genutzt werden, um externe Daten in Echtzeit zu suchen. Diese Quellen müssen über die REST-API nutzbar sein, JSON unterstützen und in der Lage sein, das Anforderungsvolumen zu verarbeiten.