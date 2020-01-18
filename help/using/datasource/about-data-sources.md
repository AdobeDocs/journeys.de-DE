---
title: Datenquellen
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
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Datenquellen {#concept_s1s_dqt_52b}

Die Datenquellenkonfiguration wird immer von einem **technischen Benutzer** durchgeführt.

Mit der Datenquellenkonfiguration können Sie eine Verbindung zu einem System definieren, um zusätzliche Informationen abzurufen, die auf Ihren Reisen verwendet werden, zum Beispiel:

* Bedingungsdefinition
* Parameter- und Personalisierungsdaten in Aktionen
* benutzerdefinierte Wartedefinition
* Definition benutzerdefinierter Zeitzonen

Diese Konfiguration ist nicht erforderlich, wenn Ihre Reisen nur lokale Daten aus einer Ereignisnutzlast nutzen. Wenn Ihre Reise beispielsweise aus einem Ereignis und einer E-Mail-Aktivität besteht, die nur Daten aus dem Ereignis verwendet, müssen Sie keine Datenquelle konfigurieren.

Es gibt zwei Arten von Datenquellen:

* Die vorkonfigurierte Experience Platform-Datenquelle, die die Verbindung zum Echtzeit-Kundenprofildienst definiert. Dies ist eine integrierte Datenquelle. Näheres wird im Abschnitt [](../datasource/adobe-experience-platform-data-source.md) beschrieben.
* Die externen Datenquellen, mit denen Sie eine Verbindung zu externen Systemen definieren können. Das sind die, die Sie erstellen können. Näheres wird im Abschnitt [](../datasource/external-data-sources.md) beschrieben.

Für jede Datenquelle definieren Sie die Informationen, die mit Feldgruppen abgerufen werden sollen. Näheres wird im Abschnitt [](../datasource/field-groups.md) beschrieben.

Im Folgenden finden Sie die wichtigsten Schritte zur Konfiguration der Datenquelle:

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Datenquellen]**.

   Die Liste der Datenquellen wird angezeigt. Weitere Informationen [](../about/user-interface.md) zur Benutzeroberfläche finden Sie unter .

   ![](../assets/journey18.png)

1. Anschließend können Sie der integrierten Datenquelle entweder Feldgruppen hinzufügen (siehe [](../datasource/adobe-experience-platform-data-source.md)) oder eine neue externe Datenquelle erstellen (siehe [](../datasource/external-data-sources.md)) und damit verbundene Feldgruppen erstellen (siehe [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Wählen Sie **[!UICONTROL Speichern]**aus.

   Die Datenquelle ist jetzt konfiguriert und kann auf Ihren Reisen verwendet werden.
