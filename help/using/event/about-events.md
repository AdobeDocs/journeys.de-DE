---
title: Ereignisse
description: Erfahren Sie, wie Sie ein Ereignis konfigurieren
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Ereignisse {#concept_gfj_fqt_52b}

Eine Veranstaltung ist mit einer Person verbunden. Es bezieht sich auf das Verhalten einer Person (zum Beispiel kaufte eine Person ein Produkt, besuchte einen Laden, verließ eine Website usw.) oder etwas, das mit einer Person verbunden ist (z. B. eine Person erreichte 10 000 Treuepunkte). Das wird das Journey Orchestration auf Reisen hören, um die besten nächsten Aktionen zu organisieren.

Diese Konfiguration ist **obligatorisch**, da die Journey Orchestration dazu bestimmt ist, Ereignisse zu hören, und immer von einem **technischen Benutzer** durchgeführt wird.

Mit der Ereigniskonfiguration können Sie festlegen, welche Informationen die Journey Orchestration als Veranstaltungen erhält. Sie können mehrere Veranstaltungen (in verschiedenen Reiseabschnitten) und mehrere Reisen dasselbe Ereignis verwenden.

Wenn Sie ein Ereignis bearbeiten, das in einem Entwurf oder einer Live-Reise verwendet wird, können Sie nur den Namen, die Beschreibung oder die Payload-Felder ändern. Wir beschränken die Auflage von Reisen, die als Entwurf oder als Livesuche gelten, strikt, um Reisen zu vermeiden.

## Allgemeiner Grundsatz {#section_r1f_xqt_pgb}

Ereignisse sind POST-API-Aufrufe. Ereignisse werden über Streaming Ingestion APIs an die Adobe Experience Cloud-Datenplattform gesendet. Das URL-Ziel von Ereignissen, die über Transaktionsnachrichten-APIs gesendet werden, wird als &quot;Einlass&quot;bezeichnet. Die Nutzlast von Ereignissen erfolgt nach der XDM-Formatierung.

Die Nutzlast enthält Informationen, die von Streaming Ingestion APIs benötigt werden, um zu funktionieren (in der Kopfzeile), die Informationen, die das Journey Orchestration benötigt, um zu funktionieren (die Ereignis-ID, Teil des Nutzlastkörpers), und die Informationen, die für Fahrten verwendet werden (im Körper, z. B. die Menge eines aufgegebenen Einkaufswagens). Es gibt zwei Modi für die Streaming-Erfassung, authentifiziert und nicht authentifiziert. Weitere Informationen zu Streaming Ingestion APIs finden Sie unter [diesem Link](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md).

Nach der Durchquerung der Streaming-Ingestion-APIs fließen Ereignisse in einen internen Dienst namens Pipeline und dann in die Datenplattform. Wenn im Ereignisschema das Flag &quot;Echtzeit-Kundenprofildienst&quot;aktiviert ist und eine Dataset-ID, die auch das Flag &quot;Echtzeit-Kundenprofil&quot;besitzt, in den Echtzeit-Kundenprofildienst fließt.

Die Pipeline filtert Ereignisse mit einer Nutzlast, die &quot;Journey Orchestration eventIDs&quot;(siehe Erstellungsprozess unten) enthalten, die von der Journey Orchestration bereitgestellt werden und in der Ereignisauslastung enthalten sind. Diese Ereignisse werden von der Journey Orchestration verfolgt und die entsprechende Reise wird ausgelöst.

## Creating a new event {#section_tbk_5qt_pgb}

Im Folgenden finden Sie die wichtigsten Schritte zum Konfigurieren eines neuen Ereignisses:

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Ereignisse]**. Die Liste der Ereignisse wird angezeigt. Weitere Informationen[](../about/user-interface.md)zur Benutzeroberfläche finden Sie unter .

   ![](../assets/journey5.png)

1. Click **[!UICONTROL Add]**to create a new event. Der Ereigniskonfigurationsbereich wird rechts im Bildschirm angezeigt.

   ![](../assets/journey6.png)

1. Geben Sie einen Namen für Ihre Veranstaltung ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Veranstaltung eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Definieren Sie das Schema und die Payload-Felder: Hier wählen Sie die Veranstaltungsinformationen aus (meist als Payload bezeichnet), die die Journey Orchestration erwartet. Sie können diese Informationen dann auf Ihrer Reise nutzen. Näheres wird im Abschnitt [](../event/defining-the-payload-fields.md) beschrieben.
1. Die Anzahl der Reisen, die dieses Ereignis verwenden, wird im Feld **[!UICONTROL Verwendet in]**angezeigt. Sie können auf das Symbol &quot;Reisen**[!UICONTROL  anzeigen]** &quot;klicken, um die Liste der Reisen mit diesem Ereignis anzuzeigen.
1. Namensraum hinzufügen. Dieser Schritt ist optional, wird jedoch empfohlen, da das Hinzufügen eines Namespace es Ihnen ermöglicht, die im Kundenprofildienst in Echtzeit gespeicherten Informationen zu nutzen. Er definiert den Typ des Schlüssels, den das Ereignis hat. Näheres wird im Abschnitt [](../event/selecting-the-namespace.md) beschrieben.
1. Definieren Sie den Schlüssel: Wählen Sie ein Feld aus Ihren Nutzlastfeldern oder definieren Sie eine Formel, um die mit dem Ereignis verbundene Person zu identifizieren. Dieser Schlüssel wird automatisch eingerichtet (kann aber dennoch bearbeitet werden), wenn Sie einen Namespace auswählen. Tatsächlich wählt das Journey Orchestration den Schlüssel aus, der dem Namespace entsprechen sollte (wenn Sie beispielsweise einen E-Mail-Namespace auswählen, wird der E-Mail-Schlüssel ausgewählt). Näheres wird im Abschnitt [](../event/defining-the-event-key.md) beschrieben.
1. Bedingung hinzufügen. Dieser Schritt ist optional. Dadurch kann das System nur die Ereignisse verarbeiten, die die Bedingung erfüllen. Die Bedingung kann nur auf den im Ereignis enthaltenen Informationen basieren. Näheres wird im Abschnitt [](../event/adding-a-condition.md) beschrieben.
1. Wählen Sie **[!UICONTROL Speichern]**aus.

   ![](../assets/journey7.png)

   Das Ereignis ist jetzt konfiguriert und kann auf eine Reise abgelegt werden. Für den Empfang von Ereignissen sind zusätzliche Konfigurationsschritte erforderlich. Näheres wird im Abschnitt [](../event/additional-steps-to-send-events-to-journey-orchestration.md) beschrieben.
