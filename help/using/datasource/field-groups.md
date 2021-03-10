---
product: adobe campaign
solution: Journey Orchestration
title: Feldergruppen
description: Erfahren Sie mehr über Feldergruppen
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 99%

---



# Feldergruppen {#concept_ntl_ypt_52b}

Feldergruppen sind Gruppen von Feldern, die Sie aus einer Datenquelle abrufen und in einer Journey verwenden können.

## Definieren von Feldergruppen {#section_dsz_kjd_fjb}

Für jede Datenquelle können Sie mehrere Feldergruppen mit einer bestimmten Aufbewahrungsfrist im Cache definieren. 

Sie können beispielsweise eine Feldergruppe mit der Telefonnummer, der E-Mail-Adresse, dem Vornamen und der Adresse des Profils erstellen. Anschließend können Sie diese Daten in Ihrer Journey verwenden, um Bedingungen zu schaffen. Sie können beispielsweise nur dann eine SMS senden, wenn die Telefonnummer des Profils nicht leer ist. Wenn sie leer ist, können Sie eine E-Mail senden.

Obwohl automatisch ein Standardname hinzugefügt wird, sollten Sie Ihrer Feldergruppe einen Namen geben. Der Feldergruppenname ist für andere Anwender in [!DNL Journey Orchestration] sichtbar. Es empfiehlt sich, Feldergruppen einen relevanten Namen zu geben.

Wenn ein Datenquellenfeld in einer Journey verwendet wird, ruft das System alle für diese Feldergruppe definierten Felder ab. Es empfiehlt sich daher, nur die Felder auszuwählen, die Sie für Ihre Journeys benötigen. Dadurch wird die Anfragelatenz in Ihren Journeys verringert und die Performance verbessert. Beachten Sie, dass Sie später problemlos weitere Felder in Feldergruppen hinzufügen können.

Die **[!UICONTROL Aufbewahrungsfrist im Cache]** ist ebenfalls wichtig, da sie Ihnen bei der Performance-Optimierung hilft. Die Aufbewahrungsfrist im Cache bedeutet, dass das System in einer Journey Daten aus einer Feldergruppe, die einmal abgerufen wurden, vorübergehend zwischenspeichert. Wenn dieselben Daten später in derselben Journey benötigt werden, sendet das System keine weitere Anfrage an die Datenquelle. Die Konfiguration der Aufbewahrungsfrist im Cache sollte für jeden Anwendungsfall angepasst werden. Wenn Sie Echtzeitdaten wie z. B. den Status der Hotelreservierung, Wetterinformationen oder die Anzahl der Treuepunkte abrufen müssen, verbinden Sie die Feldergruppe mit diesen Feldern mit einer kurzen Aufbewahrungsfrist im Cache (z. B. 1 Sekunde). Bei Feldern, die seltener aktualisiert werden (Name, Geschlecht), erstellen Sie eine zweite Feldergruppe mit einer längeren Aufbewahrungsfrist im Cache (z. B. 5 Tage).

Die Anzahl der Journeys, die eine Feldergruppe verwendet, wird im Feld **[!UICONTROL Verwendet in]** angezeigt. Sie können auf die Schaltfläche **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys mit dieser Feldergruppe anzuzeigen.

>[!NOTE]
>
>Beachten Sie, dass Feldergruppen ohne Felder nicht im Ausdruckseditor angezeigt werden.

![](../assets/journey3bis.png)

## Lebenszyklus von Feldergruppen {#section_abk_njd_fjb}

Sie können Felder zu einer Feldergruppe hinzufügen oder daraus entfernen, die in keiner Entwurfs- oder Live-Journey verwendet wird.

Einer Feldergruppe, die in einer oder mehreren Entwurfs- oder Live-Journeys verwendet wird, können Sie ein Feld hinzufügen. Sie können jedoch kein Feld daraus entfernen. Dadurch wird verhindert, dass Journeys unterbrochen werden.

Gehen Sie wie folgt vor, um ein Feld aus einer Feldergruppe zu löschen, die für eine oder mehrere Journeys verwendet wird. Verwenden wir ein Beispiel für eine Feldergruppe namens „Feldergruppe A“.

1. Platzieren Sie den Cursor in der Liste der Feldergruppen auf „Feldergruppe A“ und klicken Sie auf der rechten Seite auf das Symbol **[!UICONTROL Duplizieren]**. Benennen Sie die duplizierte Feldergruppe beispielsweise „Feldergruppe B“.
1. Entfernen Sie die nicht mehr benötigten Felder aus „Feldergruppe B“.
1. Überprüfen Sie in „Feldergruppe A“, wo diese Feldergruppe verwendet wird. Diese Informationen werden im Feld **[!UICONTROL Verwendet in]** angezeigt.
1. Öffnen Sie alle Journeys, die „Feldergruppe A“ verwenden.
1. Erstellen Sie neue Versionen jeder dieser Journeys. Bearbeiten Sie alle Aktivitäten mit „Feldergruppe A“ und wählen Sie „Feldergruppe B“ aus.
1. Stoppen Sie alte Versionen von Journeys, die „Feldergruppe A“ verwenden. Sie sollten dann keine Journey mit „Feldergruppe A“ haben.
1. Entfernen Sie „Feldergruppe A“, da sie nicht mehr verwendet wird.
