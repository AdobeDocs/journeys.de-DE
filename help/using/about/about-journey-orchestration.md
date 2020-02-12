---
title: Informationen zur Orchestrierung der Customer Journey
description: Erfahren Sie mehr über die Orchestrierung der Customer Journey
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Informationen zur Orchestrierung der Customer Journey{#concept_nd3_mqt_52b}

Erstellen Sie Anwendungsfälle für Echtzeit-Orchestrierung mithilfe von Kontextdaten, die in Ereignissen oder Datenquellen gespeichert sind.

Die Orchestrierung der Customer Journey ist ein mit Experience Platform integrierter Anwendungs-Service.

![](../assets/journeydiagram.png)

Die Orchestrierung der Customer Journey erlaubt eine Echtzeit-Orchestrierung auf Basis von Kontextdaten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Wenn Sie zum Senden Ihrer Nachrichten ein Drittanbietersystem verwenden, können Sie eine benutzerdefinierte Aktion einrichten. Wenn Sie über Adobe Campaign Standard verfügen, können Sie mit den [Funktionen für Transaktionsnachrichten](https://docs.adobe.com/content/help/de-DE/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) von Adobe Campaign Standard E-Mails, Push-Benachrichtigungen und SMS versenden.

Auf dem Tab „Ereigniskonfiguration“ richtet ein **technischer Anwender** die Ereignisse ein, die bei einer Journey erwartet werden. Die Daten eingehender Ereignisse werden mit dem Adobe Experience Data Model (XDM) normalisiert. Ereignisse kommen aus Streaming-Erfassungs-APIs für authentifizierte und nicht authentifizierte Ereignisse (z. B. Adobe Mobile SDK-Ereignisse).

Auf dem Tab „Datenquellenkonfiguration“ richtet ein **technischer Anwender** Folgendes ein:

* die verschiedenen Felder, die im Journey-Designer von Adobe Experience Platform zur Erstellung von Bedingungen und Personalisierung offen gelegt werden
* die zusätzlichen benutzerdefinierten Datenquellen, die Sie im Journey-Designer nutzen Benutzerdefinierte Datenquellen sind Verbindungen zwischen der Orchestrierung der Customer Journey und Drittanbietersystemen oder -diensten via API. So können Sie z. B. Drittanbietersysteme wie ein Treueprogramm anbinden. Dienste von Drittanbietern können beispielsweise aus einer Wetter-API bestehen.

Mit dem Journey-Designer kann ein **Business-Anwender** ein Einstiegsereignis ganz einfach per Drag-and-Drop verschieben, Bedingungen hinzufügen und die auszuführende Aktion festlegen.

Anschließend erstellen Sie Bedingungen basierend auf:

* Zeit
* Daten aus der Ereignis-Payload
* Informationen aus Datenquellen: Echtzeit-Kundenprofildatenquelle oder benutzerdefinierte Datenquellen

Sie können die Split-Bedingung verwenden, um Personen in der Journey in verschiedene Richtungen zu senden.

Mithilfe von Aktionsaktivitäten können Sie dann eine Nachricht über ein Drittanbietersystem senden. Wenn Sie über Adobe Campaign Standard verfügen, können Sie in Echtzeit personalisierte SMS, Push-Benachrichtigungen oder E-Mails senden.

Da die Orchestrierung der Customer Journey mehrere Schritte umfasst, lassen sich erweiterte Szenarien erstellen. Beispielsweise können Sie nach einem ersten Ereignis und einer ersten Aktion weitere Ereignisse ablegen. Anschließend können Sie eine zweite Aktion hinzufügen, eine Warteaktivität zum Warten platzieren, eine Split-Bedingung hinzufügen, um Benutzer auf zwei verschiedene Pfade zu senden, und anschließend verschiedene Nachrichten senden.

>[!NOTE]
>
>Die vorliegende Dokumentation wird regelmäßig aktualisiert, um aktuelle Änderungen am Produkt widerzuspiegeln. Manche Screenshots können sich jedoch geringfügig von der Benutzeroberfläche des Produkts unterscheiden.

