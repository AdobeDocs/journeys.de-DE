---
title: Adobe Campaign-Aktionen verwenden
description: Informationen zu Adobe Campaign-Aktionen
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


# Adobe Campaign-Aktionen verwenden {#using_campaign_action}

Wenn Sie über Adobe Campaign Standard verfügen, stehen die folgenden vordefinierten Aktionsaktivitäten zur Verfügung: **[!UICONTROL E-Mail]**,**[!UICONTROL  Push]** und **[!UICONTROL SMS]**.

>[!NOTE]
>
>Dazu müssen Sie die integrierte Aktion konfigurieren. Siehe Abschnitt [](../action/working-with-adobe-campaign.md).

Für jeden dieser Kanäle wählen Sie eine Adobe Campaign Standard- **Vorlage** für Transaktionsnachrichten aus. Tatsächlich ist das Journey Orchestration keine Botschaft, die eine Lösung darstellt. Für die integrierten E-Mail-, SMS- und Push-Kanäle setzen wir auf Transaktionsnachrichten, um das Senden von Nachrichten auszuführen. Das bedeutet, dass Sie, wenn Sie eine bestimmte Nachrichtenvorlage auf Ihren Reisen verwenden möchten, diese in Adobe Campaign Standard veröffentlichen müssen. Auf dieser [Seite](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) erfahren Sie, wie Sie diese Funktion verwenden.

![](../assets/journey59.png)

Sie können ein Ereignis (auch als Echtzeit bezeichnet) oder eine Vorlage für Profiltransaktionsmeldungen verwenden.

>[!NOTE]
>
>Wenn wir Echtzeit-Transaktionsmeldungen (rtEvent) senden oder Nachrichten mit einem Drittanbietersystem über eine benutzerdefinierte Aktion weiterleiten, ist ein spezifisches Setup für Ermüdung, Blacklist oder Abmeldung erforderlich. Wenn beispielsweise ein Attribut &quot;Blacklist&quot;oder &quot;unsubscribe&quot;in der Plattform oder in einem Drittanbietersystem gespeichert ist, muss vor dem Senden der Nachricht eine Bedingung hinzugefügt werden, um diese Bedingung zu überprüfen.

Wenn Sie eine Vorlage auswählen, werden alle Felder, die in der Nutzlast der Nachricht erwartet werden, im Aktivitätskonfigurationsbereich unter **[!UICONTROL Adresse]**und**[!UICONTROL  Personalisierungsdaten]**angezeigt. Sie müssen jedes dieser Felder dem zu verwendenden Feld zuordnen, entweder aus dem Ereignis oder aus der Datenquelle. Sie können auch den erweiterten Ausdruckseditor verwenden, um einen Wert manuell zu übergeben, Datenbearbeitung bei abgerufenen Informationen durchzuführen (z. B. eine Zeichenfolge in Großbuchstaben zu konvertieren) oder Funktionen wie &quot;if, then, else&quot;zu verwenden. Näheres wird im Abschnitt [](../expression/expressionadvanced.md) beschrieben.

![](../assets/journey60.png)

## E-Mail und SMS {#section_asc_51g_nhb}

Für **[!UICONTROL E-Mail]**und**[!UICONTROL  SMS]**sind die Parameter identisch.

>[!NOTE]
>
>Wenn Sie für E-Mails eine Profiltransaktionsvorlage verwenden, wird der Abmeldungsmechanismus standardmäßig von Campaign Standard verarbeitet. Fügen Sie der Vorlage einfach einen Inhaltsblock für den Link **[!UICONTROL zum]**Abmelden hinzu ([weitere Informationen](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Wenn Sie eine ereignisbasierte Vorlage (rtEvent) verwenden, müssen Sie der Nachricht einen Link hinzufügen, über den die E-Mail der Person im URL-Parameter übergeben wird und auf eine Einstiegsseite zum Rückgängigmachen des Abonnements verwiesen wird. Sie müssen diese Einstiegsseite erstellen und sicherstellen, dass die Entscheidung der Person, sich abzumelden, an Adobe übermittelt wird.

Zuerst müssen Sie eine Transaktionsnachrichtenvorlage auswählen. Näheres wird im Abschnitt [](../building-journeys/about-action-activities.md) beschrieben.

Es stehen zwei Kategorien zur Verfügung: Daten **[!UICONTROL zur Adresse]**und**[!UICONTROL  Personalisierung]**.

Sie können auf einfache Weise definieren, wo die **[!UICONTROL Adresse]**oder die**[!UICONTROL  Personalisierungsdaten]** abgerufen werden sollen. Sie können durch Ereignisse und verfügbare Datenquellen-Felder navigieren. Sie können den erweiterten Ausdruckseditor auch für erweiterte Anwendungsfälle verwenden, z. B. für die Verwendung einer Datenquelle, die die Übermittlung von Parametern oder die Durchführung von Manipulationen erfordert. Näheres wird im Abschnitt [](../expression/expressionadvanced.md) beschrieben.

**[!UICONTROL Adresse]**

>[!NOTE]
>
>Diese Kategorie ist nur sichtbar, wenn Sie eine Transaktionsmeldung &quot;event&quot;auswählen. Bei &quot;Profilmeldungen&quot;wird das Feld &quot; **[!UICONTROL Adresse]**&quot;vom System automatisch aus Adobe Campaign Standard abgerufen.

Dies sind die Felder, die das System benötigt, um zu wissen, wo die Nachricht zu senden. Bei einer E-Mail-Vorlage ist dies die E-Mail-Adresse. Für eine SMS ist es die Handynummer.

![](../assets/journey61.png)

**[!UICONTROL Personalisierungsdaten]**

>[!NOTE]
>
>Eine Sammlung in Personalisierungsdaten kann nicht übergeben werden. Wenn die transaktionale E-Mail oder SMS Sammlungen erwartet, funktioniert sie nicht. Beachten Sie außerdem, dass die Personalisierungsdaten ein erwartetes Format haben (Beispiel: Zeichenfolge, Dezimalzahl usw.) Sie müssen darauf achten, dass diese erwarteten Formate eingehalten werden.

Diese Felder werden von der Adobe Campaign Standard-Meldung erwartet. Diese Felder können verwendet werden, um die Nachricht zu personalisieren, eine bedingte Formatierung anzuwenden oder eine bestimmte Meldungsvariante auszuwählen.

![](../assets/journey62.png)

## Push-Benachrichtigung {#section_im3_hvf_nhb}

Vor der Verwendung der Push-Aktivität muss Ihre mobile App zusammen mit Campaign Standard konfiguriert werden, um Push-Benachrichtigungen zu senden. Verwenden Sie diesen [Artikel](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) , um die erforderlichen Implementierungsschritte für Mobilgeräte zu unternehmen.

Zuerst müssen Sie eine mobile App aus der Dropdownliste und eine Transaktionsnachricht auswählen. Näheres wird im Abschnitt [](../building-journeys/about-action-activities.md) beschrieben.

![](../assets/journey62bis.png)

Es stehen zwei Kategorien zur Verfügung: **[!UICONTROL Target]**- und**[!UICONTROL  Personalisierungsdaten]**.

**[!UICONTROL Zielgruppe]**

>[!NOTE]
>
>Diese Kategorie ist nur sichtbar, wenn Sie eine Ereignismeldung auswählen. Bei Profilmeldungen werden die **[!UICONTROL Target]**-Felder automatisch vom System unter Verwendung der von Adobe Campaign Standard durchgeführten Abstimmung abgerufen.

In diesem Abschnitt müssen Sie die **[!UICONTROL Push-Plattform]**definieren. In der Dropdownliste können Sie**[!UICONTROL  Apple Push Notification Server]** (iOS) oder **[!UICONTROL Firebase Cloud Messaging]**(Android) auswählen. Sie können alternativ ein bestimmtes Feld aus einem Ereignis oder einer Datenquelle auswählen oder einen erweiterten Ausdruck definieren.

Sie müssen auch das **[!UICONTROL Registrierungstoken]**definieren. Der Ausdruck hängt davon ab, wie das Token in der Nutzlast des Ereignisses oder in anderen Informationen zur Reiseorganisation definiert wird. Es kann sich um ein einfaches Feld oder einen komplexeren Ausdruck handeln, wenn das Token beispielsweise in einer Sammlung definiert ist:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalisierungsdaten]**

>[!NOTE]
>
>Eine Sammlung in Personalisierungsdaten kann nicht übergeben werden. Wenn der transaktionale Push Sammlungen erwartet, funktioniert er nicht. Beachten Sie außerdem, dass die Personalisierungsdaten ein erwartetes Format haben (Beispiel: Zeichenfolge, Dezimalzahl usw.) Sie müssen darauf achten, dass diese erwarteten Formate eingehalten werden.

Dies sind die Felder, die von der Transaktionsvorlage erwartet werden, die in Ihrer Adobe Campaign Standard-Meldung verwendet wird. Mit diesen Feldern können Sie Ihre Nachricht personalisieren, bedingte Formatierungen anwenden oder eine bestimmte Meldungsvariante auswählen.
