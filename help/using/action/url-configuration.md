---
title: URL-Konfiguration
description: Erfahren Sie mehr über die URL-Konfiguration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

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
