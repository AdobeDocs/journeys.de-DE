---
title: Hinzufügen einer Bedingung
description: Erfahren Sie, wie Sie eine Bedingung hinzufügen
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
source-git-commit: 5df2fecc56d2d2d081d952f17aadf103f2f0140a

---



# Hinzufügen einer Bedingung {#concept_rbg_gqt_52b}

Mit der Ereignisbedingung kann das System die Verarbeitung von Ereignissen filtern. Wenn die Bedingung &quot;true&quot;ist, wird das Ereignis verarbeitet. Wenn die Bedingung nicht wahr ist, wird das Ereignis ignoriert.

Die Bedingung für Ereignisse kann nur auf Daten basieren, die in der Ereignisnutzlast übergeben werden. Die auf Ereignisebene definierte Bedingung kann von einem Marketingspezialisten auf der Arbeitsfläche nicht geändert werden. Der Zweck besteht darin, diese Bedingung zu härten, wenn dieses Ereignis verwendet wird. Wenn Sie beispielsweise nie möchten, dass Marketingexperten Warenkorbereignisse verwenden, wenn der Warenkorbwert zu klein ist, können Sie eine Bedingung für das Ereignisfeld &quot;Warenkorbwert&quot;erstellen und einen Wert über 100 Dollar festlegen.

Sie können den einfachen Ausdruckseditor oder den erweiterten Ausdruckseditor verwenden, um Bedingungen für Ereignisse einzurichten. Näheres wird im Abschnitt [](../expression/expressionadvanced.md) beschrieben.

Sie können beispielsweise eine Bedingung definieren, die nur die Ereignisse eines bestimmten Ereignistyps verarbeitet und die anderen Typen ignoriert. Wenn es sich bei Ihrem Ereignis um einen Warenkorbabbruch handelt und die Nutzlast das Feld für den Wert des Einkaufswagens enthält, können Sie eine Ereignisbedingung definieren, um die Ereignisse nur dann zu verarbeiten, wenn der Wert des Einkaufswagens größer als 100 Dollar ist.

![](../assets/journey78.png)
