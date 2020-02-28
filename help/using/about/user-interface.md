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
source-git-commit: 3efe73dbfee331e2cc42ec737f0258f482171998

---


# Benutzeroberfläche{#concept_rcq_lqt_52b}


>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;Über die Liste der Journeys&quot;
>abstract=&quot;Die Liste der Journeys ermöglicht es Ihnen, alle Ihre Journeys gleichzeitig anzuzeigen, deren Status zu prüfen und grundlegende Aktionen durchzuführen. Sie können Ihre Journeys duplizieren, stoppen oder löschen. Je nach Journey stehen bestimmte Aktionen möglicherweise nicht zur Verfügung. Sie können beispielsweise eine abgeschlossene Reise nicht anhalten oder löschen. Sie können auch die Suchleiste verwenden, um nach einer Journey zu suchen.&quot;
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Demovideo ansehen&quot;

>[!NOTE]
>
>Um Journey Orchestration optimal zu nutzen, empfehlen wir die Verwendung von Chrome als Internetbrowser.
>
>Die vorliegende Dokumentation wird regelmäßig aktualisiert, um aktuelle Änderungen am Produkt widerzuspiegeln. Manche Screenshots können sich jedoch geringfügig von der Benutzeroberfläche des Produkts unterscheiden.

## Kennenlernen der Benutzeroberfläche{#section_jsq_zr1_ffb}

To access the Journey Orchestration&#39;s interface, click the **[!UICONTROL App Selector]** icon, in the top right. Klicken Sie dann rechts unter „Experience Platform“ auf **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

You can also access Journey Orchestration from the Experience Cloud home page, in the **[!UICONTROL Quick access]** section.

![](../assets/journey1bis.png)

Die Hauptmenüs ermöglichen Ihnen die Navigation durch die verschiedenen Funktionen der Reiseorchestrierung: **[!UICONTROL Home]**(Fahrten),**[!UICONTROL Data Sources]****[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klicken Sie auf das ![](../assets/icon-context.png) Symbol in der oberen rechten Ecke des Bildschirms, um die Kontexthilfe anzuzeigen. Es ist über die verschiedenen Bildschirm der Liste der Reisebegleiter (Reisen, Veranstaltungen, Aktionen und Datenquellen) verfügbar. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.

![](../assets/journey2bis.png)

## Suchen und Filtern{#section_lgm_hpz_pgb}

In den **[!UICONTROL Home]**,**[!UICONTROL Data Sources]****[!UICONTROL Events]** und **[!UICONTROL Actions]** Listen können Sie in einer Suchleiste nach einem Element suchen.

The **[!UICONTROL Filters]** can be accessed by clicking on the filter icon on the top left of the list. Mit dem Filtermenü können Sie die angezeigten Elemente anhand unterschiedlicher Kriterien filtern. Sie können festlegen, dass nur die Elemente eines bestimmten Typs oder Status, die von Ihnen erstellten Elemente oder die in den letzten 30 Tagen geänderten Elemente angezeigt werden sollen.

In the **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** and **[!UICONTROL Actions]** lists, use the **Creation filters** to filter on the creation date and user. Sie können beispielsweise festlegen, dass nur die Ereignisse angezeigt werden sollen, die Sie in den letzten 30 Tagen erstellt haben.

In the journey list (under **[!UICONTROL Home]**), in addition to the **[!UICONTROL Creation filters]**, you can also filter the displayed journeys according to their status and version (**[!UICONTROL Status and version filters]**). Sie können auch festlegen, dass nur die Reisen angezeigt werden, die ein bestimmtes Ereignis, eine bestimmte Feldgruppe oder eine bestimmte Aktion (**[!UICONTROL Activity filters]** und **[!UICONTROL Data filters]**) verwenden.Mit dieser Option **[!UICONTROL Publication filters]** können Sie ein Veröffentlichungsdatum oder einen bestimmten Benutzer auswählen. Sie können beispielsweise entscheiden, dass nur die neuesten Versionen von Live-Journeys, die am Vortag veröffentlicht wurden, angezeigt werden sollen. Siehe [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Beachten Sie, dass angezeigte Spalten mithilfe der Konfigurationsschaltfläche oben rechts in den Listen personalisiert werden können. Personalisierung wird für jeden Benutzer individuell gespeichert.

In den Spalten **[!UICONTROL Last update]** und **[!UICONTROL Last update by]** Spalten können Sie anzeigen, wann die letzte Aktualisierung Ihrer Reise stattgefunden hat und welcher Benutzer sie durchgeführt hat.

![](../assets/journey74.png)

In the event, data source and action configuration panes, the **[!UICONTROL Used in]** field displays the number of journeys that use that particular event, field group or action. You can click the **[!UICONTROL View journeys]** button to display the list of corresponding journeys.

![](../assets/journey3bis.png)

In den verschiedenen Listen können Sie grundlegende Aktionen für einzelne Elemente durchführen. Sie können Elemente beispielsweise duplizieren oder löschen.

![](../assets/journey4.png)

## XDM-Feldnamen werden angezeigt{#friendly-names-display}

XDM-Feldnamen werden in Schemata unter Feldnamen und Anzeigenamen definiert, wenn [Ereignisnutzdaten](../event/defining-the-payload-fields.md), [Feldgruppen-Nutzlast](../datasource/field-groups.md) und Felder im [Ausdruckseditor](../expression/expressionadvanced.md)definiert werden.
Bei der Auswahl eines Felds wird der technische Name des Feldes sowie ein benutzerfreundlicherer Name des Feldes angezeigt.

Sie können beim Einrichten von Schemata Deskriptoren wie &quot;xdm:alternativeDisplayInfo&quot;angeben, um Anzeigenamen zu definieren, die Anzeigenamen ersetzen. Sie können auch die Werte &quot;title&quot;und &quot;description&quot;der Schemafelder ändern.

Wenn ein benutzerfreundlicher Name verfügbar ist, wird das Feld wie `<friendly-name>(<name>)`. Ist kein Anzeigename verfügbar, wird der Anzeigename angezeigt, z. B. `<display-name>(<name>)`. Wenn keiner von ihnen definiert ist, wird nur der technische Name des Felds angezeigt `<name>`.

Sie können Anzeigenamendeskriptoren über einen API-Aufruf konfigurieren. Weitere Informationen finden Sie im Entwicklerhandbuch für die [Schemabegistrierung](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md).

![](../assets/xdm-from-descriptors.png)

>[!NOTE]
>
>Benutzerfreundliche Namen werden nicht abgerufen, wenn Sie Felder aus einer Schemaunion auswählen.

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
