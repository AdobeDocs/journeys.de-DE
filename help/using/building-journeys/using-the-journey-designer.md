---
title: Verwendung des Reisedesigners
description: Weitere Informationen zur Verwendung des Reisedesigners
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Using the journey designer {#concept_m1g_5qt_52b}

Das Menü &quot;Reise-Home&quot;ermöglicht Ihnen, die **Liste der Reisen** anzuzeigen. Erstellen Sie eine neue Reise oder klicken Sie auf eine bestehende, um die Benutzeroberfläche des **Reisedesigners** zu öffnen. Der Designer besteht aus den folgenden Zonen: Palette, Arbeitsfläche und Konfigurationsbereich für die Aktivität.

## Die Reiseliste {#journey_list}

Die **Reiseliste** ermöglicht Ihnen, alle Ihre Reisen gleichzeitig anzuzeigen, deren Status zu sehen und grundlegende Aktionen durchzuführen. Sie können Ihre Reisen duplizieren, beenden oder löschen. Je nach Reise stehen bestimmte Aktionen möglicherweise nicht zur Verfügung. Sie können zum Beispiel eine angehaltene Reise nicht stoppen. Sie können auch die Suchleiste verwenden, um nach einer Reise zu suchen.

Auf die **[!UICONTROL Filter]**können Sie durch Klicken auf das Filtersymbol oben links in der Liste zugreifen. Mit dem Filtermenü können Sie die angezeigten Reisen nach verschiedenen Kriterien filtern (Status, von Ihnen erstellte, in den letzten 30 Tagen geänderte, neueste Versionen usw.). Sie können auch festlegen, dass nur die Reisen angezeigt werden, die ein bestimmtes Ereignis, eine bestimmte Feldgruppe oder eine bestimmte Aktion verwenden. Die in der Liste angezeigten Spalten können konfiguriert werden. Alle Filter und Spalten werden pro Benutzer gespeichert.

![](../assets/journey74.png)

Alle Versionen Ihrer Reisen erscheinen in der Liste mit der Versionsnummer. Näheres wird im Abschnitt [](../building-journeys/journey-versions.md) beschrieben.

![](../assets/journey37.png)

>[!NOTE]
>
>Um die Arbeitsfläche einer Reise auf einer anderen Registerkarte des Browsers zu öffnen, halten Sie die **Strg** - oder **Befehlstaste** gedrückt und klicken Sie auf die Reise.

## The palette {#palette}

The **palette** is on the left-hand side of the screen. Alle verfügbaren Aktivitäten sind in verschiedene Kategorien unterteilt: **[!UICONTROL Veranstaltungen]**,**[!UICONTROL  Orchestrierung]** und **[!UICONTROL Aktionen]**. Sie können die verschiedenen Kategorien erweitern/reduzieren, indem Sie auf ihren Namen klicken. Um eine Aktivität auf Ihrer Reise zu verwenden, ziehen Sie sie per Drag &amp; Drop aus der Palette in Ihre Arbeitsfläche. Sie können auch auf eine Aktivität in der Palette doppelklicken, um sie zur Arbeitsfläche hinzuzufügen, und zwar im nächsten verfügbaren Schritt. Sie müssen jede Aktivität konfigurieren, die über die Palette hinzugefügt wird, bevor Sie die Reise veröffentlichen. Wenn Sie eine Aktivität auf der Arbeitsfläche ablegen und die Konfiguration nicht beenden, bleibt sie auf der Arbeitsfläche, aber eine rote Warnung weist darauf hin, dass die Konfiguration für diese Aktivität nicht abgeschlossen ist.

>[!NOTE]
>
>Beachten Sie, dass beim Einrichten einer Reise Regeln gelten. Unzulässige Konfiguration wird verworfen. Sie können beispielsweise keine Aktionen parallel platzieren, eine Aktivität mit einem vorherigen Schritt verknüpfen, um eine Schleife zu erstellen, eine Reise mit etwas anderem als einem Ereignis starten usw.

![](../assets/journey38.png)

## Die Arbeitsfläche {#canvas}

Die **Arbeitsfläche** ist die zentrale Zone im Reisedesigner. In dieser Zone können Sie Ihre Aktivitäten ablegen und konfigurieren. Klicken Sie auf eine Aktivität auf der Arbeitsfläche, um sie zu konfigurieren. Dadurch wird der Aktivitätskonfigurationsbereich auf der rechten Seite geöffnet. Mit den Schaltflächen &quot;+&quot;und &quot;-&quot;oben rechts können Sie ein- und auszoomen. Auf der Arbeitsfläche können Sie nach allen Aktivitäten einen nächsten Schritt hinzufügen, mit Ausnahme der **[!UICONTROL End]**-Aktivitäten (siehe[](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Bereich &quot;Aktivitätskonfiguration&quot; {#configuration_pane}

Der Bereich &quot; **Aktivitätskonfiguration&quot;** wird angezeigt, wenn Sie auf eine Aktivität in der Palette klicken. Füllen Sie die erforderlichen Felder aus. Klicken Sie auf das Symbol **[!UICONTROL Löschen]**, um die Aktivität zu löschen. Klicken Sie auf**[!UICONTROL  Abbrechen]** , um die Änderungen abzubrechen oder **[!UICONTROL OK]**zu bestätigen. Um Aktivitäten zu löschen, können Sie auch eine Aktivität (oder mehrere) auswählen und die Rücktaste drücken. Durch Drücken der Escape-Taste wird der Aktivitätskonfigurationsbereich geschlossen.

Auf der Arbeitsfläche werden Ihre Aktionen- und Ereignisaktivitäten durch ein Symbol mit dem Namen des Ereignisses oder der Aktion dargestellt. Im Bereich der Aktivitätskonfiguration können Sie das Feld **[!UICONTROL Bezeichnung]**verwenden, um dem Aktivitätsnamen ein Suffix hinzuzufügen. Diese Beschriftungen helfen Ihnen dabei, die Verwendung von Ereignissen und Aktionen zu kontextualisieren, insbesondere wenn Sie dasselbe Ereignis oder dieselbe Aktion mehrmals auf Ihrer Reise verwenden. Sie können auch die Etiketten sehen, die Sie in der Berichterstellung für das Journey Orchestration hinzugefügt haben.

![](../assets/journey59bis.png)

## Aktionen in der oberen Leiste {#top_actions}

Je nach Reisestatus können Sie mithilfe der Schaltflächen oben rechts auf Ihrer Reise verschiedene Aktionen ausführen: **[!UICONTROL Veröffentlichen]**,**[!UICONTROL  Duplizieren]**, **[!UICONTROL Löschen]**,**[!UICONTROL  Reiseeigenschaften]**, **[!UICONTROL Test]**. Diese Schaltflächen werden angezeigt, wenn keine Aktivität ausgewählt ist. Einige Schaltflächen werden kontextuell angezeigt. Die Protokollschaltfläche für den Testmodus wird angezeigt, wenn der Testmodus aktiviert ist (siehe[](../building-journeys/testing-the-journey.md)). Die Berichtsschaltfläche erscheint, wenn die Reise live, gestoppt oder abgeschlossen ist.

![](../assets/journey41.png)

## Die Verwendung von Pfaden auf der Arbeitsfläche {#paths}

Mit mehreren Aktivitäten (**[!UICONTROL Bedingung]**,**[!UICONTROL  Aktionsaktivitäten]** ) können Sie im Falle eines Fehlers oder einer Zeitüberschreitung eine Ausweichaktion definieren. Aktivieren Sie im Bereich &quot;Aktivitätskonfiguration&quot;das Kontrollkästchen: **[!UICONTROL Fügen Sie im Falle eines Timeouts oder Fehlers]**einen alternativen Pfad hinzu. Nach der Aktivität wird ein anderer Pfad hinzugefügt. Die Zeitüberschreitungsdauer wird in den Eigenschaften der Reise definiert (siehe[](../building-journeys/changing-properties.md)von einem Administrator). Wenn eine E-Mail zum Beispiel zu lange zum Senden benötigt wird oder ein Fehler vorliegt, können Sie sich entscheiden, eine SMS zu senden.

![](../assets/journey42.png)

Verschiedene Aktivitäten (Ereignis, Aktion, Warten) ermöglichen es Ihnen, mehrere Pfade danach hinzuzufügen. Setzen Sie dazu den Cursor auf die Aktivität und klicken Sie auf das &quot;+&quot;-Symbol. Es können nur Ereignis- und Warteaktivitäten parallel eingestellt werden. Wenn mehrere Ereignisse parallel festgelegt werden, ist der gewählte Pfad der erste, der stattfindet.

Wenn Sie einem Ereignis zuhören, sollten Sie nicht unbegrenzt auf das Ereignis warten. Es ist nicht obligatorisch, sondern nur eine Best Practice. Wenn Sie ein oder mehrere Ereignisse nur während einer bestimmten Zeit überwachen möchten, platzieren Sie ein oder mehrere Ereignisse und eine Warteaktivität parallel. Näheres wird im Abschnitt [](../building-journeys/event-activities.md#section_vxv_h25_pgb) beschrieben.

Um den Pfad zu löschen, platzieren Sie den Cursor darauf und klicken Sie auf das Symbol mit dem Pfeil **[!UICONTROL löschen]**.

![](../assets/journey42ter.png)
