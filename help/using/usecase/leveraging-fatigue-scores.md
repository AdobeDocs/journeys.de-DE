---
title: Nutzen von Ermüdungswerten
description: Erfahren Sie, wie Sie in Journeys Ermüdungswerte nutzen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 92%

---


# Verwenden von Journey AI {#concept_dsh_1ry_wfb}

Dieser Anwendungsfall zeigt, wie Sie Ermüdungswerte verwenden können, um zu verhindern, dass Sie Kunden bei Journeys überfordern.

>[!NOTE]
>
>Die Funktion für prädiktive Ermüdungswerte steht nur Kunden zur Verfügung, die [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/de-DE/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html) verwenden.

## Konfigurieren des Ereignisses {#section_ptb_ws1_ffb}

Führen Sie die auf [dieser Seite](../event/about-events.md)beschriebenen Schritte aus.

## Konfigurieren der Datenquelle {#section_o3n_4yy_wfb}

Führen Sie folgende Schritte aus, um die Ermüdungswertfelder in der integrierten Datenquelle auszuwählen:

1. Klicken Sie im oberen Menü auf den Tab **[!UICONTROL Datenquellen]** und wählen Sie die integrierte Adobe Experience Platform-Datenquelle.

   ![](../assets/journey23.png)

1. Vergewissern Sie sich, dass die für Ihre Anwendungsfälle erforderlichen Felder ausgewählt sind.
1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, wählen Sie das Modell **[!UICONTROL Profil]** und fügen Sie die Felder **[!UICONTROL fatigueLevel]** und **[!UICONTROL fatigueScore]** hinzu (unter _journeyAI > emailScore > fatigue_).

   ![](../assets/journeyuc3_1.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Erstellen der Journey {#section_uzm_pyy_wfb}

To create, validate and publish the journey, follow the steps described in [this page](../building-journeys/journey.md).

In unserem Anwendungsfall nutzen wir das Feld **[!UICONTROL fatigueLevel]**. Sie können auch das Feld **[!UICONTROL fatigueScore]** verwenden.

Führen Sie folgende Schritte aus, um den Ermüdungsgrad Ihrer Journey zu nutzen:

1. Fügen Sie Ihrer Journey ein Ereignis und eine Bedingung hinzu.

   ![](../assets/journeyuc2_14.png)

1. Wählen Sie den Typ **[!UICONTROL Bedingung der Datenquelle]** und klicken Sie auf das Feld **[!UICONTROL Ausdruck]**.

   ![](../assets/journeyuc3_2.png)

1. Suchen Sie mithilfe des einfachen Ausdruckseditors nach dem Feld **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fatigue_), legen Sie es rechts ab und erstellen Sie folgende Bedingung: „fatigueLevel ist gleich &quot;Gering&quot;“. Bestätigen Sie die Aktion mit der Schaltfläche **[!UICONTROL OK]**.

   ![](../assets/journeyuc3_3.png)

   Der erweiterte Ausdruck lautet:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Erstellen Sie in der Bedingung zwei weitere Pfade für einen mittleren und hohen Ermüdungsgrad.

   ![](../assets/journeyuc3_4.png)

1. Jetzt können Sie für jeden Ermüdungsgrad andere Aktionen hinzufügen.

   ![](../assets/journeyuc3_5.png)
