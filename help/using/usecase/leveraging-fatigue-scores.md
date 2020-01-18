---
title: Nutzen von Ermüdungswerten
description: Erfahren Sie, wie Sie Ermüdungswerte auf Reisen nutzen können
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


# Nutzen von Ermüdungswerten {#concept_dsh_1ry_wfb}

Dieser Anwendungsfall zeigt Ihnen, wie Sie Ermüdungswerte nutzen können, um zu vermeiden, dass Ihre Kunden bei Ihren Reisen übermäßig belohnen.

>[!CAUTION]
>
>Die Funktion zum Prädiktiven Ermüdungsergebnis steht nur Kunden zur Verfügung, die die Funktion Adobe Campaign Standard Data Service verwenden.

## Konfigurieren des Ereignisses {#section_ptb_ws1_ffb}

Befolgen Sie die unter [](../event/about-events.md).

## Datenquelle konfigurieren {#section_o3n_4yy_wfb}

Führen Sie die folgenden Schritte aus, um die Felder für das Ermüdungsergebnis in der integrierten Datenquelle auszuwählen:

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Datenquellen]**und wählen Sie die integrierte Experience Platform-Datenquelle.

   ![](../assets/journey23.png)

1. Vergewissern Sie sich, dass die für Ihre Anwendungsfälle erforderlichen Felder ausgewählt sind.
1. Klicken Sie auf Neue Feldgruppe ****hinzufügen, wählen Sie das**[!UICONTROL  Profilmodell]** aus und fügen Sie die Felder **[!UICONTROL Ermüdungsgrad]**und**[!UICONTROL  ErmüdungsgradErgebnis]** hinzu (unter _AI > emailScore > Ermüdung_).

   ![](../assets/journeyuc3_1.png)

1. Wählen Sie **[!UICONTROL Speichern]**aus.

## Aufbau der Reise {#section_uzm_pyy_wfb}

Gehen Sie wie unter [](../building-journeys/journey.md)beschrieben vor, um eine Reise zu erstellen, zu validieren und zu veröffentlichen.

In unserem Anwendungsfall nutzen wir das Feld **[!UICONTROL müdigkeitLevel]**. Sie können auch das Feld**[!UICONTROL  fatigueScore]** verwenden.

Führen Sie die folgenden Schritte aus, um die Ermüdungsebene Ihrer Reise zu nutzen:

1. Fügen Sie Ihrer Reise eine Veranstaltung und eine Bedingung hinzu.

   ![](../assets/journeyuc2_14.png)

1. Wählen Sie den **[!UICONTROL Datenquellenbedingungstyp]**aus und klicken Sie auf das Feld**[!UICONTROL  Ausdruck]** .

   ![](../assets/journeyuc3_2.png)

1. Suchen Sie mithilfe des einfachen Ausdrucks-Editors nach dem Feld **[!UICONTROL fatigueLevel]**(_ExperiencePlatformDataSource > JourneyAIScores > Profile >travelAI > emailScore > Müdigkeit_), legen Sie es nach rechts ab und erstellen Sie die folgende Bedingung: &quot;fatigueLevel&quot;ist gleich &quot;Low&quot;. Bestätigen Sie die Aktion mit der Schaltfläche**[!UICONTROL  OK]**.

   ![](../assets/journeyuc3_3.png)

   Der erweiterte Ausdruck lautet:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Erstellen Sie in der Bedingung zwei weitere Pfade für mittlere und hohe Ermüdungsgrade.

   ![](../assets/journeyuc3_4.png)

1. Sie können jetzt für jede Ermüdungsebene verschiedene Aktionen hinzufügen.

   ![](../assets/journeyuc3_5.png)
