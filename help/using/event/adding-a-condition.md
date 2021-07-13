---
product: adobe campaign
title: Hinzufügen einer Bedingung
description: Erfahren Sie, wie Sie eine Bedingung hinzufügen
feature: Journeys
role: User
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# Hinzufügen einer Bedingung {#concept_rbg_gqt_52b}

Bei systemgenerierten Ereignissen können Sie eine Ereignisbedingung definieren, mit der das System die Verarbeitung von Ereignissen filtern kann. Wenn die Bedingung wahr ist, wird das Ereignis verarbeitet. Wenn die Bedingung nicht wahr ist, wird das Ereignis ignoriert.

Die Bedingung für Ereignisse kann nur auf Daten basieren, die in der Ereignis-Payload übergeben werden. Die auf Ereignisebene definierte Bedingung kann von einem Marketing-Experten auf der Arbeitsfläche nicht geändert werden. Der Zweck besteht darin, diese Bedingung zu härten, wenn dieses Ereignis verwendet wird. Wenn Sie beispielsweise nicht möchten, dass Marketing-Experten bei zu geringem Warenkorbwert Transaktionsabbruchsereignisse verwenden, können Sie eine Bedingung für das Ereignisfeld „Warenkorbwert“ erstellen und einen Wert über 100 US-Dollar festlegen.

Sie können den einfachen Ausdruckseditor oder den erweiterten Ausdruckseditor verwenden, um Bedingungen für Ereignisse einzurichten. Weitere Informationen finden Sie auf [dieser Seite](../expression/expressionadvanced.md).

Sie können beispielsweise eine Bedingung definieren, die nur die Ereignisse eines bestimmten Ereignistyps verarbeitet und die anderen Typen ignoriert. Wenn es sich bei Ihrem Ereignis um einen Transaktionsabbruch handelt und die Payload das Feld für den Warenkorbwert enthält, können Sie eine Ereignisbedingung definieren, um die Ereignisse nur dann zu verarbeiten, wenn der Wert des Warenkorbs größer als 100 US-Dollar ist.

![](../assets/journey78.png)
