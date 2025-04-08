---
product: adobe campaign
title: Feldergruppen
description: Erfahren Sie mehr über Feldergruppen
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 64%

---

# Feldergruppen {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Feldergruppen sind Gruppen von Feldern, die Sie aus einer Datenquelle abrufen und in einer Journey verwenden können.

## Definieren von Feldergruppen {#section_dsz_kjd_fjb}

Für jede Datenquelle können Sie mehrere Feldergruppen definieren.

Sie können beispielsweise eine Feldergruppe mit der Telefonnummer, der E-Mail-Adresse, dem Vornamen und der Adresse des Profils erstellen. Anschließend können Sie diese Daten in Ihrer Journey verwenden, um Bedingungen zu schaffen. Sie können beispielsweise nur dann eine SMS senden, wenn die Telefonnummer des Profils nicht leer ist. Wenn sie leer ist, können Sie eine E-Mail senden.

Obwohl automatisch ein Standardname hinzugefügt wird, sollten Sie Ihrer Feldergruppe einen Namen geben. Der Feldergruppenname ist für andere Anwender in [!DNL Journey Orchestration] sichtbar. Es empfiehlt sich, Feldergruppen einen relevanten Namen zu geben.

Wenn ein Datenquellenfeld in einer Journey verwendet wird, ruft das System alle für diese Feldergruppe definierten Felder ab. Es empfiehlt sich daher, nur die Felder auszuwählen, die Sie für Ihre Journeys benötigen. Dadurch wird die Anfragelatenz in Ihren Journeys verringert und die Performance verbessert. Beachten Sie, dass Sie später problemlos weitere Felder in Feldergruppen hinzufügen können.

Die Anzahl der Journeys, die eine Feldergruppe verwendet, wird im Feld **[!UICONTROL Verwendet in]** angezeigt. Sie können auf die Schaltfläche **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys mit dieser Feldergruppe anzuzeigen.

>[!NOTE]
>
>Beachten Sie, dass eine Feldergruppe, die kein Feld hat, nicht im Ausdruckseditor angezeigt wird.

![](../assets/journey3bis.png)

## Lebenszyklus von Feldergruppen {#section_abk_njd_fjb}

Sie können Felder zu einer Feldergruppe hinzufügen oder daraus entfernen, die in keiner Entwurfs- oder Live-Journey verwendet wird.

Einer Feldergruppe, die in einer oder mehreren Entwurfs- oder Live-Journeys verwendet wird, können Sie ein Feld hinzufügen. Sie können jedoch kein Feld daraus entfernen. Dadurch wird verhindert, dass Journeys unterbrochen werden.

Gehen Sie wie folgt vor, um ein Feld aus einer Feldergruppe zu löschen, die für eine oder mehrere Journeys verwendet wird. Nehmen wir als Beispiel eine Feldergruppe mit dem Namen „Feldergruppe A“.

1. Platzieren Sie den Cursor in der Liste der Feldergruppen auf „Feldergruppe A“ und klicken Sie auf **[!UICONTROL Symbol „Duplizieren]** auf der rechten Seite. Benennen Sie die duplizierte Feldergruppe mit „Feldergruppe B“, z. B. .
1. Entfernen Sie in „Feldergruppe B“ die nicht mehr gewünschten Felder.
1. Überprüfen Sie unter „Feldergruppe A“, wo diese Feldergruppe verwendet wird. Diese Informationen werden im Feld **[!UICONTROL Verwendet in]** angezeigt.
1. Öffnen Sie alle Journey, die „Feldergruppe A“ verwenden.
1. Erstellen Sie neue Versionen jeder dieser Journeys. Bearbeiten Sie alle Aktivitäten mit „Feldergruppe A“ und wählen Sie „Feldergruppe B“ aus.
1. Beenden Sie alte Versionen von Journey, die „Feldergruppe A“ verwenden. Sie sollten dann keine Journey mit „Feldergruppe A“ haben.
1. Entfernen Sie „Feldergruppe A“, da sie nicht mehr verwendet wird.
