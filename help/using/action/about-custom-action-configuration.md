---
title: Konfiguration benutzerdefinierter Aktionen
description: Erfahren Sie, wie Sie eine benutzerdefinierte Aktion konfigurieren
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Konfiguration benutzerdefinierter Aktionen {#concept_sxy_bzs_dgb}

Wenn Sie ein Drittanbietersystem zum Senden von Nachrichten verwenden oder wenn Sie möchten, dass die Journey Orchestrierung API-Aufrufe an ein Drittanbietersystem sendet, konfigurieren Sie hier die Verbindung zum Journey Orchestration. Die von technischen Benutzern definierte Aktion steht dann in der linken Palette Ihrer Reise in der Kategorie **[!UICONTROL Aktion]**zur Verfügung (siehe[](../building-journeys/about-action-activities.md). Im Folgenden finden Sie einige Beispiele für Systeme, mit denen Sie eine Verbindung mit benutzerdefinierten Aktionen herstellen können: Epsilon, Facebook, Adobe.io, Firebase usw.
Einschränkungen sind hier aufgeführt:[](../action/custom-action-limitations.md).

Im Folgenden werden die wichtigsten Schritte beschrieben, die zum Konfigurieren einer benutzerdefinierten Aktion erforderlich sind:

1. Klicken Sie in der Liste **[!UICONTROL Aktionen]**auf**[!UICONTROL  Hinzufügen]** , um eine neue Aktion zu erstellen. Der Aktionskonfigurationsbereich wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/custom2.png)

1. Geben Sie einen Namen für die Aktion ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Aktion eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Die Anzahl der Reisen, die diese Aktion verwenden, wird im Feld **[!UICONTROL Verwendet in]**angezeigt. Sie können auf die Schaltfläche &quot;Fahrten**[!UICONTROL  anzeigen]** &quot;klicken, um die Liste der Fahrten mit dieser Aktion anzuzeigen.
1. Definieren Sie die verschiedenen **[!UICONTROL URL-Konfigurationsparameter]**. Näheres wird im Abschnitt[](../action/url-configuration.md)beschrieben.
1. Konfigurieren Sie den Abschnitt **[!UICONTROL Authentifizierung]**. Diese Konfiguration ist mit der für Datenquellen identisch.  Näheres wird im Abschnitt[](../datasource/external-data-sources.md#section_wjp_nl5_nhb)beschrieben.
1. Definieren Sie die **[!UICONTROL Nachrichtenparameter]**. Näheres wird im Abschnitt[](../action/defining-the-message-parameters.md)beschrieben.
1. Wählen Sie **[!UICONTROL Speichern]**aus.

   Die benutzerdefinierte Aktion ist jetzt konfiguriert und kann auf Ihren Reisen verwendet werden. Näheres wird im Abschnitt [](../building-journeys/about-action-activities.md) beschrieben.

   >[!NOTE]
   >
   >Wenn eine benutzerdefinierte Aktion in einer Reiseversion verwendet wird, sind die meisten Parameter schreibgeschützt. Sie können nur die Felder Name und Beschreibung ändern.
