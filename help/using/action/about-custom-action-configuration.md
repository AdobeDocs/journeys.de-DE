---
product: adobe campaign
solution: Journey Orchestration
title: Informationen zur Konfiguration einer benutzerdefinierten Aktion
description: Erfahren Sie, wie Sie eine benutzerdefinierte Aktion konfigurieren können
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 100%

---


# Informationen zur Konfiguration einer benutzerdefinierten Aktion {#concept_sxy_bzs_dgb}

Wenn Sie zum Senden von Nachrichten ein Drittanbietersystem verwenden oder möchten, dass [!DNL Journey Orchestration] API-Aufrufe an ein Drittanbietersystem sendet, konfigurieren Sie hier die Verbindung zu [!DNL Journey Orchestration]. Die von technischen Anwendern definierte Aktion steht dann in der linken Palette Ihrer Journey in der Kategorie **[!UICONTROL Aktion]** zur Verfügung (siehe [diese Seite](../building-journeys/about-action-activities.md). Im Folgenden finden Sie Beispiele für Systeme, mit denen Sie über benutzerdefinierte Aktionen eine Verbindung herstellen können: Epsilon, Facebook, Adobe.io, Firebase usw.
Einschränkungen sind auf [dieser Seite](../about/limitations.md) aufgeführt.

Im Folgenden werden die wichtigsten Schritte beschrieben, die zum Konfigurieren einer benutzerdefinierten Aktion ausgeführt werden müssen:

1. Klicken Sie in der Liste **[!UICONTROL Aktionen]** auf **[!UICONTROL Hinzufügen]**, um eine neue Aktion zu erstellen. Der Bereich für die Konfiguration der Aktion wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/custom2.png)

1. Geben Sie einen Namen für die Aktion ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Aktion eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Die Zahl der Journeys, die diese Aktion verwenden, wird im Feld **[!UICONTROL Verwendet in]** angezeigt. Sie können auf die Schaltfläche **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys anzuzeigen.
1. Definieren Sie die verschiedenen Parameter der **[!UICONTROL URL-Konfiguration]**. Weitere Informationen finden Sie auf [dieser Seite](../action/url-configuration.md).
1. Konfigurieren Sie den Bereich **[!UICONTROL Authentifizierung]**. Diese Konfiguration ist mit der für Datenquellen identisch.  Siehe [diesen Abschnitt](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definieren Sie die **[!UICONTROL Nachrichtenparameter]**. Weitere Informationen finden Sie auf [dieser Seite](../action/defining-the-message-parameters.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Die benutzerdefinierte Aktion ist nun konfiguriert und kann in Ihren Journeys verwendet werden. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wird eine benutzerdefinierte Aktion in einer Journey verwendet, sind die meisten Parameter schreibgeschützt. Sie können nur die Felder **[!UICONTROL Name]**, **[!UICONTROL Beschreibung]**, **[!UICONTROL URL]** und den Abschnitt **[!UICONTROL Authentifizierung]** ändern.
