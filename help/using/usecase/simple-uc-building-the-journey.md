---
title: Aufbau der Reise
description: Erfahren Sie, wie Sie eine einfache Verwendungsfallreise erstellen
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


# Aufbau der Reise{#concept_eyw_mcy_w2b}

Der **Geschäftsbenutzer** kann nun die Reise gestalten. Unsere Reise umfasst nur einen Pfad mit folgenden Aktivitäten:

* das &quot;SpaBeacon&quot;- **[!UICONTROL Ereignis]**: wenn eine Person in der Nähe des Wellness-Beacons geht, erhält das System eine Veranstaltung und die Reise beginnt für diese Person.
* eine **[!UICONTROL bedingte]**Aktivität, um zu überprüfen, ob die Person eine Frau ist
* eine **[!UICONTROL E-Mail]**-Aktivität (mit Adobe Campaign Standard)
* Die Aktivität **[!UICONTROL Ende]**

>[!NOTE]
>
>Die **[!UICONTROL Aktivitäten &quot;Push]**&quot;und &quot;**[!UICONTROL  E-Mail]** &quot;stehen nur dann in der Palette zur Verfügung, wenn Sie über Adobe Campaign Standard verfügen.

Weitere Informationen zum Aufbau einer Reise finden Sie unter [](../building-journeys/journey.md).

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Start]**und**[!UICONTROL  Erstellen]** , um eine neue Reise zu erstellen.

   ![](../assets/journey31.png)

1. Bearbeiten Sie die Eigenschaften der Reise im Konfigurationsbereich auf der rechten Seite. Wir nennen es &quot;Spa-Reise&quot; und legen sie auf einen Monat fest, vom 1. bis 31. Dezember.

   ![](../assets/journeyuc1_8.png)

1. Entwerfen Sie Ihre Reise mit Drag &amp; Drop des &quot;SpaBeacon&quot; Ereignisses von der Palette auf die Arbeitsfläche. Sie können auch auf das Ereignis in der Palette doppelklicken, um es der Arbeitsfläche hinzuzufügen.

   ![](../assets/journeyuc1_9.png)

1. Fügen wir nun eine Bedingung hinzu, um zu überprüfen, ob die Person eine Frau ist. Ziehen Sie eine Bedingungsaktivität per Drag &amp; Drop in Ihre Reise.

   ![](../assets/journeyuc1_10.png)

1. Wählen Sie den **[!UICONTROL Datenquellenbedingungstyp]**aus und klicken Sie auf das Feld**[!UICONTROL  Ausdruck]** . Sie können auch eine Bedingungsbeschriftung definieren, die auf dem Pfeil auf der Arbeitsfläche angezeigt wird.

   ![](../assets/journeyuc1_11.png)

1. Suchen Sie mit dem einfachen Ausdruckseditor nach dem Feld für das Geschlecht (_Person > Geschlecht_) und legen Sie es rechts ab, um die folgende Bedingung zu erstellen: &quot;Geschlecht ist gleich &quot;Weiblich&quot;.

   ![](../assets/journeyuc1_12.png)

1. Legen Sie eine **[!UICONTROL E-Mail]**-Aktivität ab und wählen Sie Ihre Transaktionsnachrichtenvorlage &quot;Spa-Rabatt&quot;. Diese Vorlage wurde mit Adobe Campaign entwickelt. Refer to this[page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Klicken Sie in das Feld **[!UICONTROL E-Mail]**und wählen Sie die E-Mail-Adresse aus der Datenquelle aus.

   ![](../assets/journeyuc1_14.png)

1. Definieren Sie auf dieselbe Weise die Personalisierungsfelder für Vornamen und Nachnamen aus der Datenquelle.

   ![](../assets/journeyuc1_15.png)

1. Drop an **[!UICONTROL End]**activity.

   ![](../assets/journeyuc1_17.png)

1. Klicken Sie auf den **[!UICONTROL Test]**-Umschalter und testen Sie Ihre Reise mithilfe von Testprofilen. Wenn ein Fehler auftritt, deaktivieren Sie den Testmodus, ändern Sie Ihre Reise und testen Sie sie erneut. For more information on the test mode, refer to[](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Wenn der Test abgeschlossen ist, können Sie Ihre Reise über das Dropdown-Menü oben rechts veröffentlichen.

   ![](../assets/journeyuc1_18.png)

Wenn eine Frau das nächste Mal in der Nähe des Wellness-Beacons geht, erhält sie sofort eine personalisierte E-Mail mit einem &quot;Spa-Rabatt&quot;.
