---
title: Informationen zu Ereignissen
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 76%

---


# Informationen zu Ereignissen {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informationen zu Ereignissen"
>abstract="Ein Ereignis ist mit einer Person verbunden. Es bezieht sich auf das Verhalten einer Person (z. B. eine Person hat ein Produkt gekauft, einen Shop besucht, eine Website verlassen usw.) oder auf etwas, das mit einer Person in Verbindung steht (z. B. eine Person hat 10.000 Treuepunkte erreicht). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

Ein Ereignis ist mit einer Person verbunden. Es bezieht sich auf das Verhalten einer Person (z. B. eine Person hat ein Produkt gekauft, einen Shop besucht, eine Website verlassen usw.) oder auf etwas, das mit einer Person in Verbindung steht (z. B. eine Person hat 10.000 Treuepunkte erreicht). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

Diese Konfiguration wird immer von einem **technischen Anwender durchgeführt und ist** obligatorisch[!DNL Journey Orchestration]**, da dazu bestimmt ist, Ereignisse zu überwachen**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. Sie können mehrere Ereignisse (in verschiedenen Schritten der Journey) verwenden und mehrere Journeys können dasselbe Ereignis verwenden.

Wenn Sie ein Ereignis bearbeiten, das in einer Entwurfs- oder Live-Journey verwendet wird, können Sie nur den Namen oder die Beschreibung ändern oder Payload-Felder hinzufügen. Die Bearbeitungsmöglichkeiten von Entwurfs- oder Live-Journeys sind stark beschränkt, damit Unterbrechungen von Journeys vermieden werden.

## Allgemeine Funktionsweise {#section_r1f_xqt_pgb}

Ereignisse sind POST-API-Aufrufe. Ereignisse werden über Streaming-Aufnahme-APIs an die Adobe Experience Cloud-Datenplattform gesendet. Das URL-Ziel von Ereignissen, die über Transaktionsnachrichten-APIs gesendet werden, wird als „Inlet“ bezeichnet. Die Payload der Ereignisse verwendet die XDM-Formatierung.

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). Es gibt zwei Modi für die Streaming-Aufnahme: authentifiziert und nicht authentifiziert. Weitere Informationen zu Streaming-Aufnahme-APIs finden Sie unter [diesem Link](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/api/getting-started.html).

Nach dem Eingang über Streaming-Aufnahme-APIs fließen Ereignisse in einen internen Dienst, die sogenannte Pipeline, und dann in die Datenplattform. Wenn für das Ereignisschema die Markierung „Echtzeit-Kundenprofildienst“ aktiviert ist und es über eine Datensatz-ID verfügt, die ebenfalls die Markierung „Echtzeit-Kundenprofil“ hat, fließt das Ereignis in den Echtzeit-Kundenprofildienst.

The Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.

## Erstellen eines neuen Ereignisses {#section_tbk_5qt_pgb}

Im Folgenden finden Sie die wichtigsten Schritte zum Konfigurieren eines neuen Ereignisses:

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Ereignisse]**. Die Liste der Ereignisse wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie unter [](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um ein neues Ereignis zu erstellen. Der Bereich für die Ereigniskonfiguration wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey6.png)

1. Geben Sie einen Namen für Ihr Ereignis ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrem Ereignis eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. Anschließend können Sie diese Informationen in Ihrer Journey verwenden. Siehe [](../event/defining-the-payload-fields.md).
1. Die Anzahl der Journeys, die dieses Ereignis verwenden, wird im Feld **[!UICONTROL Verwendet in]** angezeigt. Sie können auf **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys mit diesem Ereignis anzuzeigen.
1. Fügen Sie einen Namespace hinzu. Dieser Schritt ist optional, wird jedoch empfohlen, da das Hinzufügen eines Namespace es Ihnen ermöglicht, die im Echtzeit-Kundenprofildienst gespeicherten Informationen zu nutzen. Er definiert den Typ des Schlüssels, den das Ereignis hat. Siehe [](../event/selecting-the-namespace.md).
1. Definieren Sie den Schlüssel: Wählen Sie ein Feld aus Ihren Payload-Feldern aus oder definieren Sie eine Formel, um die mit dem Ereignis verbundene Person zu identifizieren. Dieser Schlüssel wird automatisch eingerichtet (kann aber weiterhin bearbeitet werden), wenn Sie einen Namespace auswählen. Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). Siehe [](../event/defining-the-event-key.md).
1. Fügen Sie eine Bedingung hinzu. Dieser Schritt ist optional. Dadurch kann das System nur die Ereignisse verarbeiten, die die Bedingung erfüllen. Die Bedingung kann nur auf den im Ereignis enthaltenen Informationen basieren. Siehe [](../event/adding-a-condition.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](../assets/journey7.png)

   Das Ereignis ist jetzt konfiguriert und kann in einer Journey abgelegt werden. Für den Empfang von Ereignissen sind zusätzliche Konfigurationsschritte erforderlich. Siehe [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
