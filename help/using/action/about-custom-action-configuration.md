---
title: Informationen zur Konfiguration einer benutzerdefinierten Aktion
description: Erfahren Sie, wie Sie eine benutzerdefinierte Aktion konfigurieren können
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
source-git-commit: 0c34ce9723168db3a35e3c5de122eae3462b83c0

---


# Informationen zur Konfiguration einer benutzerdefinierten Aktion {#concept_sxy_bzs_dgb}

Wenn Sie zum Senden von Nachrichten ein Drittanbietersystem verwenden oder möchten, dass Journey Orchestration API-Aufrufe an ein Drittanbietersystem sendet, konfigurieren Sie hier die Verbindung zu Journey Orchestration. The custom action defined by technical users will then be available in the left palette of your journey, in the **[!UICONTROL Action]** category (see [](../building-journeys/about-action-activities.md). Im Folgenden finden Sie Beispiele für Systeme, mit denen Sie über benutzerdefinierte Aktionen eine Verbindung herstellen können: Epsilon, Facebook, Adobe.io, Firebase usw.
Einschränkungen sind hier aufgeführt: [](../action/custom-action-limitations.md).

Im Folgenden werden die wichtigsten Schritte beschrieben, die zum Konfigurieren einer benutzerdefinierten Aktion ausgeführt werden müssen:

1. From the **[!UICONTROL Actions]** list, click **[!UICONTROL Add]** to create a new action. Der Bereich für die Konfiguration der Aktion wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/custom2.png)

1. Geben Sie einen Namen für die Aktion ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Aktion eine Beschreibung hinzu. Dieser Schritt ist optional.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Definieren Sie die verschiedenen **[!UICONTROL URL Configuration]** Parameter. Siehe [](../action/url-configuration.md).
1. Konfigurieren Sie den **[!UICONTROL Authentication]** Abschnitt. Diese Konfiguration ist mit der für Datenquellen identisch.  Siehe [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definieren Sie die **[!UICONTROL Message parameters]**. Siehe [](../action/defining-the-message-parameters.md).
1. Klicks **[!UICONTROL Save]**.

   Die benutzerdefinierte Aktion ist nun konfiguriert und kann in Ihren Journeys verwendet werden. Siehe [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wird eine benutzerdefinierte Aktion in einer Journey-Version verwendet, sind die meisten Parameter schreibgeschützt. Sie können nur die **[!UICONTROL Name]**-, **[!UICONTROL Description]**-, **[!UICONTROL URL]** - und den **[!UICONTROL Authentication]** -Abschnitt ändern.
