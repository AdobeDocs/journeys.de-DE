---
title: Informationen zu Aktionen
description: Erfahren Sie, wie Sie eine Aktion konfigurieren
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: ht
source-wordcount: '287'
ht-degree: 100%

---


# Informationen zu Aktionen {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Informationen zu Aktionen"
>abstract="Hier definieren Sie die Verbindung zum System, das Nachrichten senden soll. Die hier definierten Aktionen stehen dann in der linken Palette Ihrer Journey in der Kategorie „Aktion“ zur Verfügung. "

Aktionen sind Verbindungen, über die Sie Kunden personalisierte Echtzeit-Erlebnisse bereitstellen können. Dies sind z. B. Push-Benachrichtigungen, E-Mails, SMS oder andere digitale Interaktionen, die Sie in Ihrem Unternehmen verwenden. 

Über benutzerdefinierte Aktionen können Sie die Verbindung eines Drittanbietersystems zum Senden von Nachrichten oder API-Aufrufen konfigurieren. Eine Aktion kann mit jedem Dienst eines beliebigen Anbieters konfiguriert werden, der über eine REST-API mit einer JSON-formatierten Payload aufgerufen werden kann.

Die Aktionen stehen in der linken Palette Ihrer Journey in der Kategorie **[!UICONTROL Aktion]** zur Verfügung (siehe [](../building-journeys/about-action-activities.md)).

>[!NOTE]
>
>Die Konfiguration von benutzerdefinierten Aktionen wird immer von einem **technischen Anwender** durchgeführt.

In der Liste der **Aktionen** können Sie auf c drücken, um eine neue Journey, Aktion oder Datenquelle oder ein neues Ereignis zu erstellen. Weitere Informationen zu den Tastaturbefehlen in [!DNL Journey Orchestration] finden Sie unter [](../about/user-interface.md#section_ksq_zr1_ffb).

Um die Aktionsliste anzuzeigen oder eine neue Aktion zu konfigurieren, klicken Sie in den oberen Menüs auf **[!UICONTROL Aktionen]**. Die Liste der Aktionen wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie unter [](../about/user-interface.md).

![](../assets/custom1.png)

Falls Sie Adobe Campaign Standard verwenden, müssen Sie die vordefinierte Aktion zum Senden von E-Mails, Push-Benachrichtigungen und SMS mit den nativen Funktionen für Transaktionsnachrichten konfigurieren. Siehe [](../action/working-with-adobe-campaign.md).

Wenn Sie ein Drittanbietersystem (z. B. Epsilon, Facebook, Adobe.io, Firebase) zum Senden von Nachrichten verwenden, müssen Sie eine benutzerdefinierte Aktion hinzufügen und konfigurieren. Siehe [](../action/about-custom-action-configuration.md).

Weitere Informationen zur Konfiguration einer Aktion für [!DNL Journey Orchestration] und zur Verwendung dieser Aktion in einer Journey finden Sie in diesem [Anleitungsvideo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html).
