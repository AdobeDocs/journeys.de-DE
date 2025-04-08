---
product: adobe campaign
title: Definieren der Aktionsparameter
description: Erfahren Sie, wie Sie die Aktionsparameter definieren
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 83%

---

# Definieren der Aktionsparameter {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


![](../assets/messageparameterssection.png)

Fügen Sie im Abschnitt **[!UICONTROL Aktionsparameter]** ein Beispiel der JSON-Payload ein, die an den externen Service gesendet werden soll.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Feldnamen in der Payload dürfen das Zeichen „.“ nicht enthalten. Sie können nicht mit dem Zeichen „$“ beginnen.

Sie können den Parametertyp definieren (z. B. Zeichenfolge, Ganzzahl usw.).

Sie können auch angeben, ob ein Parameter eine Konstante oder eine Variable ist:

* Konstante bedeutet, dass der Wert des Parameters im Bereich für die Konfiguration der Aktion von einem technischen Anwender definiert wird. Der Wert bleibt über alle Journeys hinweg immer gleich. Er ändert sich nicht und wird den Marketing-Fachleuten nicht angezeigt, wenn die benutzerdefinierte Aktion während der Journey verwendet wird. Es kann sich beispielsweise um eine ID handeln, die das Drittanbietersystem erwartet. In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der übergebene Wert.
* Variable bedeutet, dass der Wert des Parameters variiert. Der Marketing-Experte, der diese benutzerdefinierte Aktion in einer Journey verwendet, kann den von ihm gewünschten Wert weitergeben oder angeben, wo der Wert für diesen Parameter abgerufen werden soll (z. B. vom Ereignis oder von Adobe Experience Platform usw.). In diesem Fall ist das Feld rechts neben dem Umschalter zwischen Konstante und Variable der Titel, den der Marketing-Experte in der Journey sieht, um diesen Parameter zu benennen.

![](../assets/customactionpayloadmessage2.png)
