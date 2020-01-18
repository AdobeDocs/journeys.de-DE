---
title: Informationen zur Reiseorganisation
description: Mehr über die Reiseorganisation
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Informationen zur Reiseorganisation{#concept_nd3_mqt_52b}

Erstellen Sie in Echtzeit-Orchesteringanwendungsfällen mithilfe von Kontextdaten, die in Ereignissen oder Datenquellen gespeichert werden.

Journey Orchestration ist ein in die Experience Platform integrierter Applikationsservice.

![](../assets/journeydiagram.png)

Mit dem Journey Orchestration können Sie Echtzeit-Orchester auf Basis von Kontextdaten zu Ereignissen, Informationen aus der Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern organisieren. Sie können eine benutzerdefinierte Aktion konfigurieren, wenn Sie zum Senden Ihrer Nachrichten ein Drittanbietersystem verwenden. Wenn Sie über Adobe Campaign Standard verfügen, können Sie E-Mails, Push-Benachrichtigungen und SMS mit den [Transaktionsnachrichten](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)von Adobe Campaign Standard senden.

Auf der Registerkarte &quot;Ereigniskonfiguration&quot;konfiguriert ein **technischer Benutzer** die Ereignisse, die während der Fahrten erwartet werden. Die Daten der eingehenden Ereignisse werden nach dem Adobe Experience Data Model (XDM) normalisiert. Ereignisse stammen von Streaming Ingestion APIs für authentifizierte und nicht authentifizierte Ereignisse (z. B. Adobe Mobile SDK-Ereignisse).

Auf der Registerkarte &quot;Konfiguration der Datenquelle&quot;konfiguriert ein **technischer Benutzer** Folgendes:

* Die verschiedenen Felder, die im Reisedesigner von der Adobe Experience Platform zur Erstellung von Bedingungen und zur Personalisierung offen gelegt werden.
* Die zusätzlichen benutzerspezifischen Datenquellen, die Sie im Reisedesigner nutzen. Benutzerspezifische Datenquellen sind Verbindungen zwischen dem Journey Orchestration und Drittanbietersystemen oder -diensten über API. Sie können ein Drittanbietersystem, z. B. ein Treuesystem, verbinden. Dienste von Drittanbietern können beispielsweise eine Wetter-API sein.

Mit dem Reisedesigner kann ein **Geschäftsbenutzer** ein Einstiegsereignis einfach per Drag &amp; Drop verschieben, Bedingungen hinzufügen und die auszuführende Aktion festlegen.

Anschließend erstellen Sie Bedingungen basierend auf:

* time
* Daten aus der Ereignisnutzlast
* Informationen aus Datenquellen: Echtzeit-Kundenprofildatenquelle oder benutzerdefinierte Datenquellen

Sie können die geteilte Bedingung verwenden, um Personen auf der Reise in verschiedene Richtungen zu senden.

Mithilfe von Aktionsaktivitäten können Sie dann eine Nachricht über ein Drittanbietersystem senden. Wenn Sie über Adobe Campaign Standard verfügen, senden Sie personalisierte SMS, Push-Benachrichtigungen oder E-Mails in Echtzeit.

Da das Journey Orchestration mehrteilig ist, können Sie erweiterte Szenarien erstellen. Beispielsweise können Sie nach einem ersten Ereignis und einer ersten Aktion andere Ereignisse ziehen. Anschließend können Sie eine zweite Aktion hinzufügen, eine Warteaktivität platzieren, die auf einige Zeit wartet, eine geteilte Bedingung hinzufügen, um Benutzer auf zwei verschiedene Pfade zu verschieben und dann verschiedene Nachrichten zu senden.

>[!NOTE]
>
>Diese Dokumentation wird häufig aktualisiert, um die jüngsten Änderungen am Produkt widerzuspiegeln. Einige Screenshots unterscheiden sich jedoch geringfügig von der Benutzeroberfläche des Produkts.

