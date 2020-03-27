---
title: Die Benutzeroberfläche
description: Erfahren Sie mehr über die Benutzeroberfläche
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bc5b29eefa4d787cd448352252823a616489d8c8

---


# Benutzeroberfläche{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Um Journey Orchestration optimal zu nutzen, empfehlen wir die Verwendung von Chrome als Internetbrowser.
>
>Die vorliegende Dokumentation wird regelmäßig aktualisiert, um aktuelle Änderungen am Produkt widerzuspiegeln. Manche Screenshots können jedoch geringfügig von der Benutzeroberfläche des Produkts abweichen.

## Zugang zur Reiseorganisation{#accessing_journey_orchestration}

To access the Journey Orchestration&#39;s interface, click the **[!UICONTROL App Selector]** icon, in the top right. Klicken Sie dann rechts unter „Experience Platform“ auf **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

You can also access Journey Orchestration from the Experience Cloud home page, in the **[!UICONTROL Quick access]** section.

![](../assets/journey1bis.png)

## Kennenlernen der Benutzeroberfläche{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;Über die Liste der Journeys&quot;
>abstract=&quot;Die Liste der Journeys ermöglicht es Ihnen, alle Ihre Journeys gleichzeitig anzuzeigen, deren Status zu prüfen und grundlegende Aktionen durchzuführen. Sie können Ihre Journeys duplizieren, stoppen oder löschen. Je nach Journey stehen bestimmte Aktionen möglicherweise nicht zur Verfügung. Sie können beispielsweise eine abgeschlossene Reise nicht löschen oder neu starten. Sie können daraus eine neue Version erstellen oder diese Duplikat erstellen. Sie können auch die Suchleiste verwenden, um nach einer Journey zu suchen.&quot;
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Demovideo ansehen&quot;

The top menus allow you to navigate through the different functionalities of Journey Orchestration: **[!UICONTROL Home]**(the journeys),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klicken Sie auf das ![](../assets/icon-context.png)-Symbol oben rechts im Bildschirm, um die Kontexthilfe anzuzeigen. Sie ist jetzt in allen Listenbildschirmen (Journeys, Ereignisse, Aktionen und Datenquellen) von Journey Orchestration verfügbar. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.

![](../assets/journey2bis.png)

## Suchen und Filtern{#section_lgm_hpz_pgb}

In den **[!UICONTROL Home]**,**[!UICONTROL Data Sources]****[!UICONTROL Events]** und **[!UICONTROL Actions]** Listen können Sie in einer Suchleiste nach einem Element suchen.

The **[!UICONTROL Filters]** can be accessed by clicking on the filter icon on the top left of the list. Mit dem Filtermenü können Sie die angezeigten Elemente anhand unterschiedlicher Kriterien filtern. Sie können festlegen, dass nur die Elemente eines bestimmten Typs oder Status, die von Ihnen erstellten Elemente oder die in den letzten 30 Tagen geänderten Elemente angezeigt werden sollen.

In the **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** and **[!UICONTROL Actions]** lists, use the **Creation filters** to filter on the creation date and user. Sie können beispielsweise festlegen, dass nur die Ereignisse angezeigt werden sollen, die Sie in den letzten 30 Tagen erstellt haben.

In the journey list (under **[!UICONTROL Home]**), in addition to the **[!UICONTROL Creation filters]**, you can also filter the displayed journeys according to their status and version (**[!UICONTROL Status and version filters]**). You can also choose to only display the journeys that use a particular event, field group or action (**[!UICONTROL Activity filters]** and **[!UICONTROL Data filters]**).The **[!UICONTROL Publication filters]** let you select a publication date or user. Sie können beispielsweise entscheiden, dass nur die neuesten Versionen von Live-Journeys, die am Vortag veröffentlicht wurden, angezeigt werden sollen. Siehe [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Beachten Sie, dass angezeigte Spalten mithilfe der Konfigurationsschaltfläche oben rechts in den Listen personalisiert werden können. Personalisierung wird für jeden Benutzer individuell gespeichert.

The **[!UICONTROL Last update]** and **[!UICONTROL Last update by]** columns allow you to display when has the last update of your journeys occured and which user operated it.

![](../assets/journey74.png)

In the event, data source and action configuration panes, the **[!UICONTROL Used in]** field displays the number of journeys that use that particular event, field group or action. You can click the **[!UICONTROL View journeys]** button to display the list of corresponding journeys.

![](../assets/journey3bis.png)

In den verschiedenen Listen können Sie grundlegende Aktionen für einzelne Elemente durchführen. Sie können Elemente beispielsweise duplizieren oder löschen.

![](../assets/journey4.png)

## Durchsuchen von Datenplattformfeldern {#friendly-names-display}

Bei der Definition von [Ereignis-Payload](../event/defining-the-payload-fields.md), [Feldgruppen-Payload](../datasource/field-groups.md) und der Auswahl von Feldern im [Ausdruckseditor](../expression/expressionadvanced.md) wird der Anzeigename zusätzlich zum Feldnamen angezeigt. Diese Informationen werden aus der Schemadefinition im Experience-Datenmodell abgerufen.

Wenn beim Einrichten von Schemata Deskriptoren wie „xdm:alternativeDisplayInfo“ angegeben werden, werden die Anzeigenamen durch benutzerfreundliche Namen ersetzt. Dies ist besonders bei der Verwendung von eVars und generischen Feldern nützlich. Deskriptoren für benutzerfreundliche Namen können über einen API-Aufruf konfiguriert werden. Weitere Informationen finden Sie im [Entwicklerhandbuch zur Schema Registry](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md).

![](../assets/xdm-from-descriptors.png)

Wenn ein benutzerfreundlicher Name verfügbar ist, wird das Feld als `<friendly-name>(<name>)` angezeigt. Ist kein benutzerfreundlicher Name verfügbar, wird der Anzeigename angezeigt, z. B. `<display-name>(<name>)`. Wenn keiner der Namen definiert ist, wird nur der technische Name des Felds `<name>` angezeigt.

>[!NOTE]
>
>Benutzerfreundliche Namen werden nicht abgerufen, wenn Sie Felder aus einer Vereinigungsmenge von Schemata auswählen.

## Verwenden der verschiedenen Tastaturbefehle{#section_ksq_zr1_ffb}

Hier finden Sie die verschiedenen Tastaturbefehle, die in der Benutzeroberfläche von Journey Orchestration verfügbar sind.

_In der Liste der Journeys, Aktionen, Datenquellen oder Ereignisse:_

* Drücken Sie **c**, um eine neue Journey, Aktion, Datenquelle oder ein neues Ereignis zu erstellen.

_Beim Konfigurieren einer Aktivität in einer Journey:_

Die Arbeitsfläche wird automatisch gespeichert. Oben links in der Arbeitsfläche sehen Sie den Speicherstatus.

* Drücken Sie **Esc**, um den Konfigurationsbereich zu schließen und die vorgenommenen Änderungen zu verwerfen. Dies entspricht der Schaltfläche **[!UICONTROL Cancel]**.
* Press **[!UICONTROL Enter]** or click outside the pane to close the configuration pane. Änderungen werden gespeichert. Dies entspricht der Schaltfläche **[!UICONTROL Ok]**.
* If you press **[!UICONTROL Delete]** or **backspace**, you can then press **[!UICONTROL Enter]** to confirm the deletion.

_In Popups:_

* Drücken Sie **Esc**, um sie zu schließen (entspricht der Schaltfläche **Abbrechen**).
* Press **[!UICONTROL Enter]** to save or confirm (equivalent of the **[!UICONTROL Ok]** or **[!UICONTROL Save]** button).

_Im Ereignis-, Datenquellen- oder Aktionskonfigurationsbereich:_

* Drücken Sie **Esc**, um den Konfigurationsbereich ohne Speichern zu schließen.
* Press **[!UICONTROL Enter]** to save modifications and close the configuration pane.
* Drücken Sie die **Tabulatortaste**, um zwischen den verschiedenen zu konfigurierenden Feldern zu wechseln.

_Im einfachen Ausdruckseditor:_

* Doppelklicken Sie links auf ein Feld, um eine Abfrage hinzuzufügen (entspricht Drag-and-Drop).

_Beim Durchsuchen von XDM-Feldern:_

* Bei Aktivierung eines „Knotens“ werden alle Felder des Knotens ausgewählt.

_In allen Textbereichen:_

* Verwenden Sie die Tastenkombination **Strg-Taste/Befehlstaste+A**, um den Text auszuwählen. In der Payload-Vorschau wird die Payload ausgewählt.

_In einem Bildschirm mit einer Suchleiste:_

* Verwenden Sie die Tastenkombination **Strg-Taste/Befehlstaste+F**, um die Suchleiste auszuwählen.

_In der Arbeitsfläche einer Journey:_

* Verwenden Sie die Tastenkombination **Strg-Taste/Befehlstaste+A**, um alle Aktivitäten auszuwählen.
* When one or several activities are selected, press **[!UICONTROL Delete]** or **backspace** to delete them. Then you can press **[!UICONTROL Enter]** to confirm in the confirmation pop-up.
* Doppelklicken Sie auf eine Aktivität in der linken Palette, um sie an der ersten verfügbaren Position (von oben nach unten) hinzuzufügen.
