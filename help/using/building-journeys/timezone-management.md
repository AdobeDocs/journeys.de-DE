---
title: Zeitzonen-Management
description: Erfahren Sie mehr über das Zeitzonen-Management
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 100%

---



# Zeitzonen-Management {#timezone_management}

Sie können eine Zeitzone in den [Eigenschaften](../building-journeys/changing-properties.md) Ihrer Journey festlegen.

Um die Eigenschaften aufzurufen, klicken Sie auf das Stiftsymbol oben rechts im Bildschirm.

Diese Zeitzone wird für jede Aktivität der Journey verwendet, die ein Zeitelement enthält, z. B.: 

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Sie können eine Zeitzone auswählen oder die Zeitzone verwenden, die im Benutzerprofil definiert ist.

## Definieren einer festen Zeitzone {#fixed-timezone}

Die Zeitzone kann auch fest definiert werden. Löschen Sie die vordefinierte Zeitzone und wählen Sie eine aus der Dropdown-Liste aus. Wenn Sie eine feste Zeitzone verwenden, ist diese für alle Kontakte gleich, die die Journey beginnen.

Wählen Sie dazu in den **[!UICONTROL Eigenschaften]** eine Zeitzone aus.

![](../assets/journey73.png)

## Verwenden von Profilen zur Definition der Zeitzone einer Journey {#timezone-from-profiles}

Wenn das Eintrittsereignis der Journey einen Namespace hat, d. h. die Journey hat Zugriff auf den Echtzeit-Kundenprofildienst von Adobe Experience Platform, wird die Zeitzone mit jener im Profil des Kontakts vordefiniert, der sich in der Journey befindet.

Wenn eine Zeitzone im Adobe Experience Platform-Profil definiert ist, kann sie in der Journey abgerufen werden.

Wenn das Profil des Kontakts keine Zeitzone enthält, wird die im Zeitzonenfeld definierte Zeitzone abgerufen.

Aktivieren Sie dazu in den **[!UICONTROL Eigenschaften]** die Option **[!UICONTROL Zeitzone des Profils in Timern und Bedingungen verwenden]**.

![](../assets/journey72.png)

## Verwenden von Zeitzonen in Ausdrücken {#timezone-in-expressions}

Das Start- und Enddatum einer Journey kann nicht mit einer bestimmten Zeitzone verknüpft werden. Es wird automatisch mit der Zeitzone der Instanz verbunden.
