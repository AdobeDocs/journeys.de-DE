---
product: adobe campaign
title: Nutzen von Ermüdungswerten
description: Erfahren Sie, wie Sie in Journeys Ermüdungswerte nutzen
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---


# Verwenden von Journey-KI {#concept_dsh_1ry_wfb}

Dieser Anwendungsfall zeigt, wie Sie Ermüdungswerte verwenden können, um zu verhindern, dass Sie Kunden bei Journeys überfordern.

>[!NOTE]
>
>Die Funktion für prädiktive Ermüdungswerte steht nur Kunden zur Verfügung, die [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html?lang=de) verwenden.

## Konfigurieren des Ereignisses {#section_ptb_ws1_ffb}

Führen Sie die auf [dieser Seite](../event/about-events.md) beschriebenen Schritte aus.

## Konfigurieren der Datenquelle  {#section_o3n_4yy_wfb}

Führen Sie folgende Schritte aus, um die Ermüdungswertfelder in der integrierten Datenquelle auszuwählen:

1. Wählen Sie im Menübereich **[!UICONTROL Admin]** aus. Klicken Sie im Abschnitt **[!UICONTROL Datenquellen]** auf **[!UICONTROL Verwalten]**.
1. Wählen Sie die integrierte Adobe Experience Platform-Datenquelle aus.

   ![](../assets/journey23.png)

1. Vergewissern Sie sich, dass die für Ihre Anwendungsfälle erforderlichen Felder ausgewählt sind.
1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, wählen Sie das Modell **[!UICONTROL Profil]** und fügen Sie die Felder **[!UICONTROL fatigueLevel]** und **[!UICONTROL fatigueScore]** hinzu (unter _journeyAI > emailScore > fatigue_).

   ![](../assets/journeyuc3_1.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Erstellen der Journey {#section_uzm_pyy_wfb}

Gehen Sie wie auf [dieser Seite](../building-journeys/journey.md) beschrieben vor, um eine Journey zu erstellen, zu validieren und zu veröffentlichen.

In unserem Anwendungsfall nutzen wir das Feld **[!UICONTROL fatigueLevel]**. Sie können auch das Feld **[!UICONTROL fatigueScore]** verwenden.

Führen Sie folgende Schritte aus, um den Ermüdungsgrad Ihrer Journey zu nutzen:

1. Fügen Sie Ihrer Journey ein Ereignis und eine Bedingung hinzu.

   ![](../assets/journeyuc2_14.png)

1. Wählen Sie den Typ **[!UICONTROL Bedingung der Datenquelle]** und klicken Sie auf das Feld **[!UICONTROL Ausdruck]**.

   ![](../assets/journeyuc3_2.png)

1. Suchen Sie mithilfe des einfachen Ausdruckseditors nach dem Feld **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fatigue_), legen Sie es rechts ab und erstellen Sie folgende Bedingung: „fatigueLevel ist gleich &quot;Gering&quot;“. Klicken Sie auf **[!UICONTROL OK]**.

   ![](../assets/journeyuc3_3.png)

   Der erweiterte Ausdruck lautet:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Erstellen Sie in der Bedingung zwei weitere Pfade für einen mittleren und hohen Ermüdungsgrad.

   ![](../assets/journeyuc3_4.png)

1. Jetzt können Sie für jeden Ermüdungsgrad andere Aktionen hinzufügen.

   ![](../assets/journeyuc3_5.png)
