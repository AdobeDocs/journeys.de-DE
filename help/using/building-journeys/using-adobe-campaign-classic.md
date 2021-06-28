---
product: adobe campaign
solution: Journey Orchestration
title: Verwenden von Adobe Campaign v7/v8-Aktionen
description: Informationen zu Adobe Campaign v7/v8-Aktionen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b2439788ef547b401dea64faf46d4398b9a1a0c7
workflow-type: ht
source-wordcount: '165'
ht-degree: 100%

---

# Verwenden von Adobe Campaign v7/v8 {#using_campaign_classic}

Eine Integration ist verfügbar, wenn Sie über Adobe Campaign v7 oder v8 verfügen. Diese Integration ermöglicht Ihnen das Senden von E-Mails, Push-Benachrichtigungen und SMS mit der Transaktionsnachrichten-Funktion von Adobe Campaign.

Die Verbindung zwischen der Journey Orchestration- und der Campaign-Instanz wird bei der Bereitstellung durch Adobe eingerichtet. Nehmen Sie Kontakt zu Adobe auf.

Sie müssen zu diesem Zweck eine spezielle Aktion konfigurieren. Näheres dazu finden Sie in diesem [Abschnitt](../action/acc-action.md).

In diesem [Abschnitt](../usecase/campaign-classic-use-case.md) wird ein Anwendungsfall vollständig beschrieben.

1. Beginnen Sie bei der Erstellung Ihrer Journey mit einem Ereignis. Siehe diesen [Abschnitt](../building-journeys/journey.md).
1. Wählen Sie im Abschnitt **Aktion** der Palette eine Campaign-Aktion aus und fügen Sie sie zu Ihrer Journey hinzu.
1. Unter **Aktionsparameter** werden alle Felder angezeigt, die in der Nachrichten-Payload erwartet werden. Sie müssen jedes dieser Felder entweder im Ereignis oder der Datenquelle dem zu verwendenden Feld zuordnen. Dies ähnelt benutzerdefinierten Aktionen. Siehe diesen [Abschnitt](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
