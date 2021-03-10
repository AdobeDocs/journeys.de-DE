---
product: adobe campaign
solution: Journey Orchestration
title: Zeitzonen-Management
description: Erfahren Sie mehr über das Zeitzonen-Management
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 99%

---



# Zeitzonen-Management {#timezone_management}

Sie können eine Zeitzone in den [Eigenschaften](../building-journeys/changing-properties.md) Ihrer Journey festlegen.

Um die Eigenschaften aufzurufen, klicken Sie auf das Stiftsymbol oben rechts im Bildschirm.

Diese Zeitzone wird für jede Aktivität der Journey verwendet, die ein Zeitelement enthält, z. B.: 

* [Bedingung für die Uhrzeit](../building-journeys/condition-activity.md#time_condition)
* [Bedingung für das Datum](../building-journeys/condition-activity.md#date_condition)
* [Benutzerdefinierte Wartezeit](../building-journeys/wait-activity.md#custom)
* [Wartezeit mit festgelegtem Datum](../building-journeys/wait-activity.md#fixed_date)

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
