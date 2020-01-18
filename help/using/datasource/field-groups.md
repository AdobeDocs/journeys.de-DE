---
title: Feldgruppen
description: Informationen zu Feldgruppen
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



# Field groups {#concept_ntl_ypt_52b}

## Definieren von Feldgruppen {#section_dsz_kjd_fjb}

Für jede Datenquelle können Sie mehrere Feldgruppen mit einer bestimmten Cachedauer definieren. Sie ermöglichen Ihnen die Auswahl der Felder, die Sie aus der Datenquelle abrufen möchten, die Sie auf Ihren Reisen verwenden möchten.

Sie können beispielsweise eine Feldgruppe mit der Telefonnummer, der E-Mail, dem Vornamen und der Adresse des Profils erstellen. Anschließend können Sie diese Daten auf Ihrer Reise verwenden, um Bedingungen zu schaffen. Sie können beispielsweise nur dann eine SMS senden, wenn die Telefonnummer des Profils nicht leer ist. Wenn es leer ist, können Sie eine E-Mail senden.

Obwohl automatisch ein Standardname hinzugefügt wird, sollten Sie Ihrer Feldgruppe einen Namen geben. Tatsächlich wird der Feldgruppenname für andere Benutzer im Journey Orchestration sichtbar sein. Es empfiehlt sich, Feldgruppen einen relevanten Namen zu geben.

Wenn ein Datenquellenfeld in einer Reise verwendet wird, ruft das System alle für diese Feldgruppe definierten Felder ab. Es empfiehlt sich daher, nur die Felder auszuwählen, die Sie für Ihre Reisen benötigen. Dadurch wird die Anforderungslatenz bei Ihren Reisen verringert und die Leistung erhöht. Beachten Sie, dass Sie später problemlos weitere Felder in Feldgruppen hinzufügen können.

**[!UICONTROL Die Cachedauer]**ist ebenfalls wichtig, da sie Ihnen bei der Leistungsoptimierung hilft. Die Cachedauer bedeutet, dass das System die Daten während einer Fahrt, wenn Daten aus einer Feldgruppe einmal abgerufen werden, vorübergehend zwischenspeichert. Wenn dieselben Daten später auf derselben Reise benötigt werden, stellt das System keine weitere Anforderung an die Datenquelle dar. Die Konfiguration der Cachedauer sollte für jeden Anwendungsfall angepasst werden. Wenn Sie Echtzeitdaten wie Hotelreservierungsstatus, Wetterinformationen oder die Anzahl der Treuepunkte abrufen müssen, verbinden Sie die Feldgruppe mit diesen Feldern mit einer kurzen Cache-Dauer (z. B. 1 Sekunde). Bei Feldern, die seltener aktualisiert werden (Name, Geschlecht), erstellen Sie eine zweite Feldgruppe mit einer längeren Cachedauer (z. B. 5 Tage).

Die Anzahl der Reisen, die eine Feldgruppe verwenden, wird im Feld **[!UICONTROL Verwendet in]**angezeigt. Sie können auf die Schaltfläche &quot;Reisen**[!UICONTROL  anzeigen]** &quot;klicken, um die Liste der Reisen mit dieser Feldgruppe anzuzeigen.

>[!NOTE]
>
>Beachten Sie, dass Feldgruppen ohne Feld nicht im Ausdruckseditor angezeigt werden.

![](../assets/journey3bis.png)

## Lebenszyklus von Feldgruppen {#section_abk_njd_fjb}

Sie können Felder zu einer Feldgruppe hinzufügen oder daraus entfernen, die in keinem Entwurf oder einer Live-Reise verwendet wird.

Sie können ein Feld hinzufügen, aber nicht aus einer Feldgruppe entfernen, die in einem oder mehreren Entwurfs- oder Live-Reisen verwendet wird. Dadurch wird verhindert, dass Reisen unterbrochen werden.

Gehen Sie wie folgt vor, um ein Feld aus einer Feldgruppe zu löschen, die für eine oder mehrere Reisen verwendet wird. Verwenden wir ein Beispiel für eine Feldgruppe namens &quot;Feldgruppe A&quot;.

1. Platzieren Sie in der Liste der Feldgruppen den Cursor auf &quot;Feldgruppe A&quot;und klicken Sie auf das Symbol **[!UICONTROL Duplizieren]**rechts. Benennen Sie beispielsweise die duplizierte Feldgruppe &quot;Feldgruppe B&quot;.
1. Entfernen Sie unter &quot;Feldgruppe B&quot;die nicht mehr benötigten Felder.
1. Überprüfen Sie unter &quot;Feldgruppe A&quot;, wo diese Feldgruppe verwendet wird. Diese Informationen werden im Feld **[!UICONTROL Verwendet in]**angezeigt.
1. Öffnen Sie alle Fahrten, die &quot;Feldgruppe A&quot; verwenden.
1. Erstellen Sie neue Versionen jeder dieser Reisen. Bearbeiten Sie alle Aktivitäten mit &quot;Feldgruppe A&quot;und wählen Sie &quot;Feldgruppe B&quot;.
1. Beenden Sie alte Versionen von Reisen, die &quot;Feldgruppe A&quot;verwenden. Sie sollten dann keine Reise mit &quot;Feldgruppe A&quot;haben.
1. Entfernen Sie &quot;Feldgruppe A&quot;, da sie nicht mehr verwendet wird.
