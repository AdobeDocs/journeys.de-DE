---
title: Auswählen des Namespace
description: Erfahren Sie, wie Sie den Namespace auswählen
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


# Auswählen des Namespace {#concept_ckb_3qt_52b}

Mit dem Namespace können Sie den Typ des Schlüssels definieren, mit dem die mit dem Ereignis verbundene Person identifiziert wird. Die Konfiguration ist optional. Es ist erforderlich, wenn Sie auf Ihren Reisen zusätzliche Informationen aus dem [Echtzeit-Kundenprofil](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)abrufen möchten. Die Namespace-Definition ist nicht erforderlich, wenn Sie nur Daten aus einem Drittanbietersystem über eine benutzerdefinierte Datenquelle verwenden.

Sie können entweder eine der vordefinierten verwenden oder mit dem Identitäts-Namespace-Dienst eine neue erstellen. Refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md).

Wenn Sie ein Schema mit einer primären Identität auswählen, werden die Felder **[!UICONTROL Schlüssel]**und**[!UICONTROL  Namespace]** vorausgefüllt. Wenn keine Identität definiert ist, wählen Sie _identityMap > id_ als Primärschlüssel. Dann müssen Sie einen Namespace auswählen, und der Schlüssel wird vorausgefüllt (unter dem Feld **[!UICONTROL Namespace]**) mit _identityMap > id_.

Wählen Sie in der Dropdownliste einen Namespace aus.

![](../assets/journey17.png)

Pro Fahrt ist nur ein Namespace zulässig. Wenn Sie mehrere Ereignisse auf derselben Reise verwenden, müssen diese denselben Namespace verwenden. Näheres wird im Abschnitt [](../building-journeys/journey.md) beschrieben.
