---
title: Definieren der Nachrichtenparameter
description: Erfahren Sie, wie Sie die Nachrichtenparameter definieren
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
source-git-commit: ae0fb0a8560bbb00ed5be47abf7f42bae5015a7c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 85%

---


# Definieren der Nachrichtenparameter {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Fügen Sie im Abschnitt **[!UICONTROL Nachrichtenparameter]** ein Beispiel der JSON-Payload ein, die an den externen Dienst gesendet werden soll.

![](../assets/customactionpayloadmessage.png)

You will be able to define the parameter type (e.g.: string, integer, etc.).

You will also have a choice between specifying if a parameter is a constant or a variable:

* Konstante bedeutet, dass der Wert des Parameters im Bereich für die Konfiguration der Aktion von einem technischen Anwender definiert wird. Der Wert bleibt über all Journeys hinweg immer gleich. Er ändert sich nicht und wird dem Marketing-Experten nicht angezeigt, wenn die benutzerdefinierte Aktion während der Journey verwendet wird. Er könnte beispielsweise eine ID sein, die das Drittanbietersystem erwartet. In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der übergebene Wert.
* Variable bedeutet, dass der Wert des Parameters variiert. Der Marketing-Experte, der diese benutzerdefinierte Aktion in einer Journey verwendet, kann den von ihm gewünschten Wert weitergeben oder angeben, wo der Wert für diesen Parameter abgerufen werden soll (z. B. vom Ereignis oder von Adobe Experience Platform usw.). In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der Titel, den der Marketing-Experte in der Journey sieht, um diesen Parameter zu benennen.

![](../assets/customactionpayloadmessage2.png)
