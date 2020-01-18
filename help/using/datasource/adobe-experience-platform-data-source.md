---
title: 'Adobe Experience Platform-Datenquelle '
description: 'Erfahren Sie, wie Sie die Adobe Experience Platform-Datenquelle konfigurieren '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Adobe Experience Platform data source {#concept_zrb_nqt_52b}

Die Experience Platform-Datenquelle definiert die Verbindung zum Echtzeit-Kundenprofildienst. Diese Datenquelle ist integriert und vorkonfiguriert. Es kann nicht gelöscht werden. Diese Datenquelle dient zum Abrufen und Verwenden von Daten aus dem Echtzeit-Kundenprofildienst (z. B. zur Überprüfung, ob die Person, die eine Reise absolvierte, eine Frau ist). Es ermöglicht Ihnen die Verwendung von Profildaten und Experience Events-Daten. Weitere Informationen zum Echtzeit-Kundenprofildienst finden Sie auf dieser [Seite](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

>[!NOTE]
>
>Sie können die 1000 neuesten Erlebnisereignisse abrufen, die vor weniger als einem Jahr erstellt wurden.

Um die Verbindung zum Echtzeit-Kundenprofildienst zu ermöglichen, müssen wir einen Schlüssel zur Identifizierung einer Person und einen Namespace verwenden, der den Schlüssel kontextualisiert. Daher können Sie diese Datenquelle nur verwenden, wenn Ihre Reisen mit einem Ereignis beginnen, das einen Schlüssel und einen Namespace enthält. Näheres wird im Abschnitt [](../building-journeys/journey.md) beschrieben.

Sie können die vorkonfigurierte Feldgruppe mit dem Namen &quot;ProfileFieldGroup&quot;bearbeiten, neue hinzufügen und diejenigen entfernen, die nicht in Entwurfs- oder Live-Reisen verwendet werden. Näheres wird im Abschnitt [](../datasource/field-groups.md) beschrieben.

Im Folgenden finden Sie die wichtigsten Schritte, um der integrierten Datenquelle Feldgruppen hinzuzufügen.

1. Wählen Sie in der Liste der Datenquellen die integrierte Experience Platform-Datenquelle aus.

   Dadurch wird der Bereich für die Datenquellenkonfiguration auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey23.png)

1. Klicken Sie auf Neue Feldgruppe **[!UICONTROL hinzufügen]**, um eine neue Feldreihe zum Abrufen zu definieren. Näheres wird im Abschnitt[](../datasource/field-groups.md)beschrieben.

   ![](../assets/journey24.png)

1. Wählen Sie ein Schema aus der Dropdownliste **[!UICONTROL Schema]**. In diesem Feld werden die in der Plattform verfügbaren Profil- und Erlebnisereignisschemata aufgelistet. Die Schemaerstellung wird nicht im Journey Orchestration durchgeführt. Er wird in der Datenplattform ausgeführt.
1. Wählen Sie die zu verwendenden Felder aus.
1. Definieren Sie die Cachedauer.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Wenn Sie den Cursor auf den Namen einer Feldgruppe setzen, werden rechts zwei Symbole angezeigt. Damit können Sie die Feldgruppe löschen und duplizieren. Beachten Sie, dass das Symbol &quot; **[!UICONTROL Löschen]**&quot;nur verfügbar ist, wenn die Feldgruppe auf keiner Live- oder Entwurfsreise verwendet wird (Informationen, die im Feld &quot;**[!UICONTROL  Verwendet in]** &quot;angezeigt werden).
