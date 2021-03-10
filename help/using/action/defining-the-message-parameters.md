---
product: adobe campaign
solution: Journey Orchestration
title: Definieren der Nachrichtenparameter
description: Erfahren Sie, wie Sie die Nachrichtenparameter definieren
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 99%

---


# Definieren der Nachrichtenparameter {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Fügen Sie im Abschnitt **[!UICONTROL Nachrichtenparameter]** ein Beispiel der JSON-Payload ein, die an den externen Dienst gesendet werden soll.

![](../assets/customactionpayloadmessage.png)

Sie können den Parametertyp definieren (z. B.: Zeichenfolge, Ganzzahl usw.).

Sie können außerdem angeben, ob ein Parameter eine Konstante oder eine Variable ist:

* Konstante bedeutet, dass der Wert des Parameters im Bereich für die Konfiguration der Aktion von einem technischen Anwender definiert wird. Der Wert bleibt über all Journeys hinweg immer gleich. Er ändert sich nicht und wird dem Marketing-Experten nicht angezeigt, wenn die benutzerdefinierte Aktion während der Journey verwendet wird. Er könnte beispielsweise eine ID sein, die das Drittanbietersystem erwartet. In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der übergebene Wert.
* Variable bedeutet, dass der Wert des Parameters variiert. Der Marketing-Experte, der diese benutzerdefinierte Aktion in einer Journey verwendet, kann den von ihm gewünschten Wert weitergeben oder angeben, wo der Wert für diesen Parameter abgerufen werden soll (z. B. vom Ereignis oder von Adobe Experience Platform usw.). In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der Titel, den der Marketing-Experte in der Journey sieht, um diesen Parameter zu benennen.

![](../assets/customactionpayloadmessage2.png)
