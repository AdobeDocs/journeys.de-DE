---
product: adobe campaign
title: URL-Konfiguration
description: Erfahren Sie mehr über die URL-Konfiguration
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 19%

---

# URL-Konfiguration {#concept_gbg_1f1_2gb}

Beim Konfigurieren einer benutzerdefinierten Aktion müssen Sie die folgenden **[!UICONTROL URL-Konfigurationsparameter]** definieren:

![](../assets/journeyurlconfiguration.png)

1. Geben Sie im Feld **[!UICONTROL URL]** die URL des externen Dienstes an:

   * Wenn die URL statisch ist, geben Sie die URL in dieses Feld ein.

   * Wenn die URL einen dynamischen Pfad enthält, geben Sie nur den statischen Teil der URL ein, d. h. das Schema, den Host, den Port und optional einen statischen Teil des Pfads.

      Beispiel: `https://xxx.yyy.com:8080/somethingstatic/`

      Sie geben den dynamischen Pfad der URL an, wenn Sie die benutzerdefinierte Aktion zu einer Journey hinzufügen. [Weitere Informationen](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Aus Sicherheitsgründen empfehlen wir dringend, das HTTPS-Schema für die URL zu verwenden. Die Verwendung nicht öffentlicher Adobe-Adressen und die Verwendung von IP-Adressen sind nicht zulässig.

1. Wählen Sie die **[!UICONTROL Aufrufmethode]** aus: Sie kann entweder **[!UICONTROL POST]** oder **[!UICONTROL PUT]** sein.
1. Definieren Sie im Abschnitt **[!UICONTROL Headers]** die HTTP-Header der Anforderungsnachricht, die an den externen Dienst gesendet werden soll:
   1. Um ein Header-Feld hinzuzufügen, klicken Sie auf **[!UICONTROL Header-Feld hinzufügen]**.
   1. Geben Sie den Schlüssel des Header-Felds ein.
   1. Um einen dynamischen Wert für das Schlüssel-Wert-Paar festzulegen, wählen Sie **[!UICONTROL Variable]** aus. Wählen Sie andernfalls **[!UICONTROL Konstante]** aus.

      Beispielsweise können Sie für einen Zeitstempel einen dynamischen Wert festlegen.

   1. Wenn Sie **[!UICONTROL Konstante]** ausgewählt haben, geben Sie den Konstantenwert ein.

      Wenn Sie **[!UICONTROL Variable]** ausgewählt haben, geben Sie diese Variable an, wenn Sie die benutzerdefinierte Aktion zu einer Journey hinzufügen. [Weitere Informationen](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Um ein Kopfzeilenfeld zu löschen, verweisen Sie auf das Kopfzeilenfeld und klicken Sie auf das Symbol **[!UICONTROL Löschen]** .
   Die Header-Felder **[!UICONTROL Content-Type]** und **[!UICONTROL Charset]** werden standardmäßig festgelegt. Sie können diese Felder nicht ändern oder löschen.

   Nachdem Sie die benutzerdefinierte Aktion zu einer Journey hinzugefügt haben, können Sie ihr weiterhin Kopfzeilenfelder hinzufügen, wenn sich die Journey im Entwurfsstatus befindet. Wenn Sie nicht möchten, dass die Journey von Konfigurationsänderungen betroffen ist, duplizieren Sie die benutzerdefinierte Aktion und fügen Sie die Kopfzeilenfelder zur neuen benutzerdefinierten Aktion hinzu.

   >[!NOTE]
   >
   >Kopfzeilen werden gemäß den Feldanalyseregeln validiert. [Weitere Informationen](https://tools.ietf.org/html/rfc7230#section-3.2.4).
