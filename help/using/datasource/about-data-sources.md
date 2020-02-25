---
title: Informationen zu Datenquellen
description: 'Erfahren Sie, wie Sie eine Datenquelle konfigurieren '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# Informationen zu Datenquellen {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Informationen zu Datenquellen&quot;
>abstract=&quot;Die Konfiguration von Datenquellen wird immer von einem technischen Anwender durchgeführt. Mit der Datenquellenkonfiguration können Sie eine Verbindung zu einem System definieren, um zusätzliche Informationen abzurufen, die in Ihren Journeys verwendet werden. Damit können Sie Bedingungen definieren, Parameter- und Personalisierungsdaten in Aktionen verwenden sowie die Wartezeit und die Zeitzone definieren.&quot;

Die Konfiguration von Datenquellen wird immer von einem **technischen Anwender** durchgeführt.

Mit der Datenquellenkonfiguration können Sie eine Verbindung zu einem System definieren, um zusätzliche Informationen abzurufen, die in Ihren Journeys verwendet werden, zum Beispiel für:

* Definition von Bedingungen
* Parameter- und Personalisierungsdaten in Aktionen
* Definition benutzerdefinierter Wartezeiten
* Definition benutzerdefinierter Zeitzonen

Diese Konfiguration ist nicht erforderlich, wenn Ihre Journeys nur lokale Daten aus einer Ereignis-Payload nutzen. Wenn Ihre Journey beispielsweise aus einem Ereignis und einer E-Mail-Aktivität besteht, die nur Daten aus dem Ereignis verwendet, müssen Sie keine Datenquelle konfigurieren.

Es gibt zwei Arten von Datenquellen:

* Die vorkonfigurierte Datenquelle von Experience Platform, die die Verbindung zum Echtzeit-Kundenprofildienst definiert. Dies ist eine integrierte Datenquelle. Siehe [](../datasource/adobe-experience-platform-data-source.md).
* Die externen Datenquellen, mit denen Sie eine Verbindung zu externen Systemen definieren können. Diese können Sie erstellen. Siehe [](../datasource/external-data-sources.md).

Für jede Datenquelle definieren Sie die Informationen, die mit Feldergruppen abgerufen werden sollen. Siehe [](../datasource/field-groups.md).

Im Folgenden finden Sie die wichtigsten Schritte zur Konfiguration der Datenquelle:

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Datenquellen]**.

   Die Liste der Datenquellen wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie unter [](../about/user-interface.md).

   ![](../assets/journey18.png)

1. Anschließend können Sie der integrierten Datenquelle entweder Feldergruppen hinzufügen (siehe [](../datasource/adobe-experience-platform-data-source.md)) oder eine neue externe Datenquelle erstellen (siehe [](../datasource/external-data-sources.md)) und damit verbundene Feldergruppen erstellen (siehe [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Die Datenquelle ist jetzt konfiguriert und kann in Ihren Journeys verwendet werden.
