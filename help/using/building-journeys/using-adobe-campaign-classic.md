---
product: adobe campaign
solution: Journey Orchestration
title: Verwenden von Adobe Campaign-Aktionen
description: Erfahren Sie mehr über Adobe Campaign-Aktionen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 66%

---

# Verwenden von Adobe Campaign Classic {#using_campaign_classic}

Wenn Sie über Adobe Campaign Classic verfügen, ist eine Integration verfügbar. Sie ermöglicht den Versand von E-Mails, Push-Benachrichtigungen und SMS mit den Funktionen für Transaktionsnachrichten in Adobe Campaign Classic.

Die Verbindung zwischen der Journey Orchestration- und der Campaign Classic-Instanz wird bei der Bereitstellung von Adobe hergestellt. Adobe kontaktieren.

Dazu müssen Sie eine dedizierte Aktion konfigurieren. Siehe diesen [Abschnitt](../action/acc-action.md).

Ein durchgängiges Anwendungsbeispiel wird in diesem [Abschnitt](../usecase/campaign-classic-use-case.md) vorgestellt.

1. Beginnen Sie bei der Erstellung Ihrer Journey mit einem Ereignis. Siehe diesen [Abschnitt](../building-journeys/journey.md).
1. Wählen Sie im Abschnitt **Aktion** der Palette eine Campaign Classic-Aktion aus und fügen Sie sie zu Ihrer Journey hinzu.
1. Unter **Aktionsparameter** werden alle Felder angezeigt, die in der Nachrichten-Payload erwartet werden. Sie müssen jedes dieser Felder entweder im Ereignis oder der Datenquelle dem zu verwendenden Feld zuordnen. Dies ähnelt benutzerdefinierten Aktionen. Siehe diesen [Abschnitt](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
