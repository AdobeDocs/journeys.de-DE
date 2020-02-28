---
title: Feldergruppen
description: Erfahren Sie mehr über Feldergruppen
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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---



# Feldergruppen {#concept_ntl_ypt_52b}

Feldgruppen sind Feldgruppen, die Sie aus einer Datenquelle abrufen und auf einer Reise verwenden können.

## Definieren von Feldergruppen {#section_dsz_kjd_fjb}

Für jede Datenquelle können Sie mehrere Feldergruppen mit einer bestimmten Aufbewahrungsfrist im Cache definieren.

Sie können beispielsweise eine Feldergruppe mit der Telefonnummer, der E-Mail-Adresse, dem Vornamen und der Adresse des Profils erstellen. Anschließend können Sie diese Daten in Ihrer Journey verwenden, um Bedingungen zu schaffen. Sie können beispielsweise nur dann eine SMS senden, wenn die Telefonnummer des Profils nicht leer ist. Wenn sie leer ist, können Sie eine E-Mail senden.

Obwohl automatisch ein Standardname hinzugefügt wird, sollten Sie Ihrer Feldergruppe einen Namen geben. Der Feldergruppenname ist für andere Anwender in Journey Orchestration sichtbar. Es empfiehlt sich, Feldergruppen einen relevanten Namen zu geben.

Wenn ein Datenquellenfeld in einer Journey verwendet wird, ruft das System alle für diese Feldergruppe definierten Felder ab. Es empfiehlt sich daher, nur die Felder auszuwählen, die Sie für Ihre Journeys benötigen. Dadurch wird die Anfragelatenz in Ihren Journeys verringert und die Performance verbessert. Beachten Sie, dass Sie später problemlos weitere Felder in Feldergruppen hinzufügen können.

**[!UICONTROL Cache duration]** ist auch wichtig, da es Ihnen dabei hilft, die Leistung zu optimieren. Die Aufbewahrungsfrist im Cache bedeutet, dass das System in einer Journey Daten aus einer Feldergruppe, die einmal abgerufen wurden, vorübergehend zwischenspeichert. Wenn dieselben Daten später in derselben Journey benötigt werden, sendet das System keine weitere Anfrage an die Datenquelle. Die Konfiguration der Aufbewahrungsfrist im Cache sollte für jeden Anwendungsfall angepasst werden. Wenn Sie Echtzeitdaten wie z. B. den Status der Hotelreservierung, Wetterinformationen oder die Anzahl der Treuepunkte abrufen müssen, verbinden Sie die Feldergruppe mit diesen Feldern mit einer kurzen Aufbewahrungsfrist im Cache (z. B. 1 Sekunde). Bei Feldern, die seltener aktualisiert werden (Name, Geschlecht), erstellen Sie eine zweite Feldergruppe mit einer längeren Aufbewahrungsfrist im Cache (z. B. 5 Tage).

The number of journeys that use a field group is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of journeys using this field group.

>[!NOTE]
>
>Beachten Sie, dass Feldergruppen ohne Felder nicht im Ausdruckseditor angezeigt werden.

![](../assets/journey3bis.png)

## Lebenszyklus von Feldergruppen {#section_abk_njd_fjb}

Sie können Felder zu einer Feldergruppe hinzufügen oder daraus entfernen, die in keiner Entwurfs- oder Live-Journey verwendet wird.

Einer Feldergruppe, die in einer oder mehreren Entwurfs- oder Live-Journeys verwendet wird, können Sie ein Feld hinzufügen. Sie können jedoch kein Feld daraus entfernen. Dadurch wird verhindert, dass Journeys unterbrochen werden.

Gehen Sie wie folgt vor, um ein Feld aus einer Feldergruppe zu löschen, die für eine oder mehrere Journeys verwendet wird. Verwenden wir ein Beispiel für eine Feldergruppe namens „Feldergruppe A“.

1. In the list of field groups, place the cursor on “Field Group A” and click on the **[!UICONTROL Duplicate]** icon located on the right. Benennen Sie die duplizierte Feldergruppe beispielsweise „Feldergruppe B“.
1. Entfernen Sie die nicht mehr benötigten Felder aus „Feldergruppe B“.
1. Überprüfen Sie in „Feldergruppe A“, wo diese Feldergruppe verwendet wird. This information is displayed in the **[!UICONTROL Used in]** field.
1. Öffnen Sie alle Journeys, die „Feldergruppe A“ verwenden.
1. Erstellen Sie neue Versionen jeder dieser Journeys. Bearbeiten Sie alle Aktivitäten mit „Feldergruppe A“ und wählen Sie „Feldergruppe B“ aus.
1. Stoppen Sie alte Versionen von Journeys, die „Feldergruppe A“ verwenden. Sie sollten dann keine Journey mit „Feldergruppe A“ haben.
1. Entfernen Sie „Feldergruppe A“, da sie nicht mehr verwendet wird.
