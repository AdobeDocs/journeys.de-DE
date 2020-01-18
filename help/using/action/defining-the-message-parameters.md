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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Definieren der Nachrichtenparameter {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Fügen Sie im Abschnitt **[!UICONTROL Meldungsparameter]**ein Beispiel der JSON-Nutzlast ein, die an den externen Dienst gesendet werden soll.


![](../assets/customactionpayloadmessage.png)

Sie können festlegen, ob der Parametertyp richtig ist (z.B.: Zeichenfolge, Ganzzahl usw.).

Sie haben außerdem die Wahl zwischen der Angabe eines Parameters als Konstante oder Variable:

* Konstante bedeutet, dass der Wert des Parameters im Aktionskonfigurationsbereich von einer technischen Person definiert wird. Der Wert ist über Reisen hinweg immer gleich. Es ändert sich nicht, und der Marketingspezialist sieht es nicht, wenn er die benutzerdefinierte Aktion während der Reise verwendet. Es könnte beispielsweise eine ID sein, die das Drittanbietersystem erwartet. In diesem Fall ist das Feld rechts neben der Umschalt-Konstante/Variable der weitergegebene Wert.
* Variable bedeutet, dass der Wert des Parameters variiert. Der Marketingexperte, der diese benutzerdefinierte Aktion auf einer Reise verwendet, kann den von ihm gewünschten Wert weitergeben oder angeben, wo der Wert für diesen Parameter abgerufen werden soll (z. B. vom Ereignis oder von der Datenplattform...). In diesem Fall ist das Feld auf der rechten Seite der umschaltbaren Konstante/Variable die Beschriftung, die der Marketingexperte auf der Reise sehen wird, um diesen Parameter zu benennen.
