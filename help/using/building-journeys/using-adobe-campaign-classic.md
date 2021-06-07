---
product: adobe campaign
solution: Journey Orchestration
title: Verwenden von Adobe Campaign v7/v8-Aktionen
description: Erfahren Sie mehr über Adobe Campaign v7/v8-Aktionen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: f4344697c24d8436f7c474e828f820e7f3f9a48e
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 38%

---

# Verwenden von Adobe Campaign v7/v8 {#using_campaign_classic}

Eine Integration ist verfügbar, wenn Sie über Adobe Campaign v7 oder v8 verfügen. Sie ermöglicht den Versand von E-Mails, Push-Benachrichtigungen und SMS mit den Funktionen für Transaktionsnachrichten in Adobe Campaign.

Die Verbindung zwischen der Journey Orchestration- und der Campaign-Instanz wird von Adobe zum Zeitpunkt der Bereitstellung eingerichtet. Adobe kontaktieren.

Dazu müssen Sie eine dedizierte Aktion konfigurieren. Siehe diesen [Abschnitt](../action/acc-action.md).

Ein durchgängiges Anwendungsbeispiel wird in diesem [Abschnitt](../usecase/campaign-classic-use-case.md) vorgestellt.

1. Beginnen Sie bei der Erstellung Ihrer Journey mit einem Ereignis. Siehe diesen [Abschnitt](../building-journeys/journey.md).
1. Wählen Sie im Bereich **Aktion** der Palette eine Kampagnenaktion aus und fügen Sie sie Ihrer Journey hinzu.
1. Unter **Aktionsparameter** werden alle Felder angezeigt, die in der Nachrichten-Payload erwartet werden. Sie müssen jedes dieser Felder entweder im Ereignis oder der Datenquelle dem zu verwendenden Feld zuordnen. Dies ähnelt benutzerdefinierten Aktionen. Siehe diesen [Abschnitt](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
