---
product: adobe campaign
title: 'Datenquelle von Adobe Experience Platform '
description: 'Erfahren Sie, wie Sie die Datenquelle von Adobe Experience Platform konfigurieren '
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# Datenquelle von Adobe Experience Platform {#concept_zrb_nqt_52b}

Die Datenquelle von Adobe Experience Platform definiert die Verbindung zum Echtzeit-Kundenprofildienst. Diese Datenquelle ist integriert und vorkonfiguriert. Sie kann nicht gelöscht werden. Diese Datenquelle dient zum Abrufen und Verwenden von Daten aus dem Echtzeit-Kundenprofildienst (überprüfen Sie beispielsweise, ob es sich bei der Person, die an einer Journey teilnimmt, um eine Frau handelt). Sie ermöglicht Ihnen die Verwendung von Profildaten und Erlebnisereignisdaten. Weitere Informationen zum Echtzeit-Kundenprofildienst finden Sie auf dieser [Seite](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de).

>[!NOTE]
>
>Sie können die 1.000 neuesten Erlebnisereignisse abrufen, die vor weniger als einem Jahr erstellt wurden.

Um die Verbindung zum Echtzeit-Kundenprofildienst zu ermöglichen, müssen wir einen Schlüssel zur Identifizierung einer Person und einen Namespace verwenden, der den Schlüssel kontextualisiert. Daher können Sie diese Datenquelle nur verwenden, wenn Ihre Journeys mit einem Ereignis beginnen, das einen Schlüssel und einen Namespace enthält. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/journey.md).

Sie können die vorkonfigurierte Feldergruppe mit dem Namen „ProfileFieldGroup“ bearbeiten, neue hinzufügen und diejenigen entfernen, die nicht in Entwurfs- oder Live-Journeys verwendet werden. Weitere Informationen finden Sie auf [dieser Seite](../datasource/field-groups.md).

Im Folgenden finden Sie die wichtigsten Schritte, um der integrierten Datenquelle Feldergruppen hinzuzufügen.

1. Wählen Sie in der Liste der Datenquellen die integrierte Datenquelle von Adobe Experience Platform aus.

   Dadurch wird der Konfigurationsbereich für die Datenquellen auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey23.png)

1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, um eine neue Reihe von Feldern zum Abrufen zu definieren. Weitere Informationen finden Sie auf [dieser Seite](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Wählen Sie ein Schema aus der Dropdown-Liste **[!UICONTROL Schema]** aus. In diesem Feld werden die in Adobe Experience Platform verfügbaren Profil- und Erlebnisereignisschemata aufgelistet. Die Schemaerstellung wird nicht in [!DNL Journey Orchestration] durchgeführt. Sie wird in Adobe Experience Platform ausgeführt.
1. Wählen Sie die Felder aus, die Sie verwenden möchten.
1. Definieren Sie die Aufbewahrungsfrist im Cache.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Wenn Sie den Cursor auf dem Namen einer Feldergruppe platzieren, werden rechts zwei Symbole angezeigt. Damit können Sie die Feldergruppe löschen und duplizieren. Beachten Sie, dass das Symbol **[!UICONTROL Löschen]** nur verfügbar ist, wenn die Feldergruppe in keiner Live- oder Entwurfs-Journey verwendet wird (die Information wird im Feld **[!UICONTROL Verwendet in]** angezeigt).
