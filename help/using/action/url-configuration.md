---
product: adobe campaign
solution: Journey Orchestration
title: URL-Konfiguration
description: Erfahren Sie mehr über die URL-Konfiguration
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 98%

---


# URL-Konfiguration {#concept_gbg_1f1_2gb}

Beim Konfigurieren einer benutzerdefinierten Aktion müssen Sie die folgenden **[!UICONTROL URL-Konfigurationsparameter]** definieren:

![](../assets/journeyurlconfiguration.png)

1. Fügen Sie die **[!UICONTROL URL]** des externen Dienstes hinzu.

   >[!NOTE]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen. Die Verwendung nicht öffentlicher Adobe-Adressen und die Verwendung von IP-Adressen sind nicht zulässig.

1. Wählen Sie die **[!UICONTROL Aufrufmethode]** aus: Sie kann entweder **[!UICONTROL POST]** oder **[!UICONTROL PUT]** sein.
1. Klicken Sie im Abschnitt **[!UICONTROL Kopfzeilen]** auf **[!UICONTROL Feld für Kopfzeile hinzufügen]**, um ein neues Schlüssel/Wert-Paar zu definieren. Sie entsprechen den HTTP-Kopfzeilen der Anfrage an den externen Dienst. Um Schlüssel/Wert-Paare zu löschen, platzieren Sie den Cursor im Feld **[!UICONTROL Kopfzeilen]** und klicken Sie auf das Symbol **[!UICONTROL Löschen]**.

   **[!UICONTROL Inhaltstyp]** und **[!UICONTROL Zeichensatz]** sind standardmäßig festgelegt und können nicht gelöscht oder überschrieben werden.

   >[!NOTE]
   >
   >Kopfzeilen werden gemäß den folgenden [Parsing-Regeln](https://tools.ietf.org/html/rfc7230#section-3.2.4) validiert.
