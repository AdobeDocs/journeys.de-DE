---
title: URL-Konfiguration
description: Informationen zur URL-Konfiguration
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


# URL configuration {#concept_gbg_1f1_2gb}

Beim Konfigurieren einer benutzerdefinierten Aktion müssen Sie die folgenden **[!UICONTROL URL-Konfigurationsparameter]**definieren:

![](../assets/journeyurlconfiguration.png)

1. Fügen Sie die **[!UICONTROL URL]**des externen Dienstes hinzu.

   >[!NOTE]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen. Die Verwendung nicht öffentlicher Adobe-Adressen und die Verwendung von IP-Adressen ist nicht zulässig.

1. Wählen Sie die Aufrufmethode **[!UICONTROL aus]**: kann entweder**[!UICONTROL  POST]** oder **[!UICONTROL PUT]**sein.
1. Klicken Sie im Abschnitt **[!UICONTROL Kopfzeilen]**auf Kopfzeilenfeld****hinzufügen, um ein neues Schlüssel/Wert-Paar zu definieren. Sie entsprechen den HTTP-Headern der Anforderung an den externen Dienst. Um Schlüssel/Wert-Paare zu löschen, platzieren Sie den Cursor im Feld **[!UICONTROL Kopfzeilen]**und klicken Sie auf das Symbol**[!UICONTROL  Löschen]** .

   **[!UICONTROL Content-Type]**und**[!UICONTROL  Charset]** werden standardmäßig eingestellt und können nicht gelöscht oder überschrieben werden.

   >[!NOTE]
   >
   >Kopfzeilen werden gemäß den folgenden [Parsing-Regeln](https://tools.ietf.org/html/rfc7230#section-3.2.4)validiert.
