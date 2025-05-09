---
product: adobe campaign
title: Abbrechen einer Journey
description: Erfahren Sie, wie Sie eine Journey beenden
feature: Journeys
role: User
level: Intermediate
exl-id: 2d1b9d6b-0a53-436c-b251-ce77cb931aaa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '427'
ht-degree: 100%

---

# Abbrechen einer Journey


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Mit den Optionen **[!UICONTROL Stoppen]** und **[!UICONTROL Für neue Eintritte schließen]** können Sie **Live**-Journeys beenden. Wenn Sie eine Journey schließen, wird **der Eintritt neuer Kunden in die Journey blockiert** und die bereits in der Journey befindlichen Kunden können diese bis zum Ende durchlaufen. Dies ist die empfohlene Art, eine Journey zu beenden, da sie für die Kunden das beste Erlebnis bietet. Wenn Sie hingegen eine Journey stoppen, wird die Reise der bereits in der Journey befindlichen Personen abgebrochen. Die Journey wird praktisch deaktiviert.

>[!NOTE]
>
>Beachten Sie, dass Sie eine geschlossene oder gestoppte Journey nicht fortsetzen können.
>
>Das Konzept der Beendigung einer Journey wird in diesem [Abschnitt](../building-journeys/journey.md#ending_a_journey) beschrieben.

## Schließen einer Journey

Sie können eine Journey manuell schließen. In diesem Fall können Kundinnen und Kunden, die sich bereits in der Journey befinden, ihren Pfad bis zum Ende verfolgen, neue Anwenderinnen und Anwender können jedoch nicht in die Journey eintreten.

Wenn eine Journey geschlossen ist, weist sie den Status **[!UICONTROL Geschlossen (kein Eintritt)]** auf. Nach der standardmäßigen globalen maximalen Wartezeit von 30 Tagen wechselt die Journey zum Status **Beendet**. Weitere Informationen finden Sie in diesem [Abschnitt](../building-journeys/changing-properties.md#entrance).

Eine geschlossene Journey-Version kann weder neu gestartet noch gelöscht werden. Stattdessen können Sie eine neue Version davon erstellen oder sie duplizieren. Nur abgeschlossene Journeys können gelöscht werden.

Wenn Sie eine Journey schließen möchten, klicken Sie auf **[!UICONTROL Für neue Eintritte schließen]**, während Sie die Maus über die jeweilige Journey in der Liste der Journeys bewegen.

![](../assets/do-not-localize/journey-finish-quick-action.png)

Alternativ können Sie auch folgendermaßen vorgehen:

1. Klicken Sie auf der **[!UICONTROL Startseite]** auf die Journey, die Sie schließen möchten.
1. Klicken Sie oben rechts auf den Abwärtspfeil.

   ![](../assets/finish_drop_down_list.png)

1. Klicken Sie auf **[!UICONTROL Für neue Eintritte schließen]**. Das folgende Dialogfeld wird angezeigt.
1. Klicken Sie zur Bestätigung auf **[!UICONTROL Für neue Eintritte schließen]**.

## Stoppen einer Journey

Sie können eine Journey stoppen, wenn ein unerwartetes Ereignis eintritt und die gesamte Verarbeitung der Journey unverzüglich abgebrochen werden muss.

Eine gestoppte Journey-Version kann nicht nochmals gestartet werden.

Wird eine Journey gestoppt, hat sie den Status **[!UICONTROL Gestoppt]**.

Sie können eine Journey stoppen (z. B. wenn ein Marketing-Experte erkennt, dass die Journey auf die falsche Zielgruppe ausgerichtet ist oder wenn eine benutzerdefinierte Aktion, mit der Nachrichten gesendet werden sollen, nicht richtig funktioniert), indem Sie auf **[!UICONTROL Stoppen]** klicken, während Sie die Maus über die jeweilige Journey in der Liste der Journeys bewegen.

![](../assets/do-not-localize/journey-stop-quick-action.png)

Alternativ können Sie auch folgendermaßen vorgehen:

1. Klicken Sie auf der **[!UICONTROL Startseite]** auf die Journey, die Sie stoppen möchten.
1. Klicken Sie oben rechts auf den Abwärtspfeil.

![](../assets/finish_drop_down_list.png)

1. Klicken Sie auf **[!UICONTROL Anhalten]**. Das folgende Dialogfeld wird angezeigt.
1. Klicken Sie zur Bestätigung auf **[!UICONTROL Stoppen]**.
