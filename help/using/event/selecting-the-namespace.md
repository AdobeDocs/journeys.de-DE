---
product: adobe campaign
title: Auswählen des Namespace
description: Erfahren Sie, wie Sie den Namespace auswählen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 97%

---

# Auswählen des Namespace {#concept_ckb_3qt_52b}

Mit dem Namespace können Sie den Typ des Schlüssels definieren, mit dem die mit dem Ereignis verbundene Person identifiziert wird. Die Konfiguration ist optional. Sie ist erforderlich, wenn Sie in Ihren Journeys zusätzliche Informationen aus dem [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) abrufen möchten. Der Namespace muss nicht definiert werden, wenn Sie nur Daten aus einem Drittanbietersystem über eine benutzerdefinierte Datenquelle verwenden.

Sie können entweder einen der vordefinierten Namespace verwenden oder mit dem Identity-Namespace-Dienst einen neuen erstellen. Mehr dazu erfahren Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html).

Wenn Sie ein Schema mit einer Primäridentität auswählen, werden die Felder **[!UICONTROL Schlüssel]** und **[!UICONTROL Namespace]** vorbelegt. Wenn keine Identität definiert ist, wählen Sie _identityMap > id_ als Primärschlüssel aus. Wählen Sie anschließend einen Namespace aus und der Schlüssel wird (unter dem Feld **[!UICONTROL Namespace]**) mit _identityMap > id_ vorbelegt.

Bei der Auswahl von Feldern werden Primäridentitätsfelder mit Tags versehen.

![](../assets/primary-identity.png)


Wählen Sie einen Namespace aus der Dropdown-Liste aus.

![](../assets/journey17.png)

Pro Journey ist nur ein Namespace zulässig. Wenn Sie mehrere Ereignisse in derselben Journey verwenden, müssen diese denselben Namespace verwenden. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/journey.md).
