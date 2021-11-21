---
product: adobe campaign
title: Verwenden benutzerdefinierter Aktionen
description: Erfahren Sie mehr über Aktionsaktivitäten
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 100%

---

# Verwenden benutzerdefinierter Aktionen {#section_f2c_hbg_nhb}

Im Konfigurationsbereich für die Aktivität werden die URL-Konfigurationsparameter und die Authentifizierungsparameter angezeigt, die für die benutzerdefinierte Aktion konfiguriert sind. [Weitere Informationen](../action/about-custom-action-configuration.md).

>[!NOTE]
>
>Eine einfache Kollektion kann nicht in benutzerdefinierten Aktionsparametern übergeben werden. Komplexere Kollektionsfelder (Arrays von Objekten) werden nicht unterstützt.  Beachten Sie außerdem, dass die Parameter ein erwartetes Format haben (Beispiel: Zeichenfolge, Dezimalzahl usw.). Sie müssen darauf achten, dass diese erwarteten Formate eingehalten werden.

## URL-Konfiguration

### Dynamischer Pfad

Wenn die URL einen dynamischen Pfad enthält, geben Sie den Pfad im Feld **[!UICONTROL Pfad]** an.

>[!NOTE]
>
>Sie können den statischen Teil der URL nicht in der Journey, sondern müssen ihn in der globalen Konfiguration der benutzerdefinierten Aktion einrichten. [Weitere Informationen](../action/about-custom-action-configuration.md).

Verwenden Sie zum Verketten von Feldern und Nur-Text-Zeichenfolgen die Zeichenfolgen-Funktionen oder das Pluszeichen (+) im erweiterten Ausdruckseditor. Schließen Sie Nur-Text-Zeichenfolgen in einfachen Anführungszeichen (&#39;) oder in doppelten Anführungszeichen (&quot;) ein. [Weitere Informationen](../expression/expressionadvanced.md).

Die folgende Tabelle zeigt ein Beispiel für die Konfiguration:

| Feld | Wert |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Pfad | `The id of marketingCampaign + '/messages'` |

Die verkettete URL sieht folgendermaßen aus:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### Header

Im Abschnitt **[!UICONTROL URL-Konfiguration]** werden die dynamischen Header-Felder, jedoch nicht die konstanten Header-Felder angezeigt. Dynamische Header-Felder sind HTTP-Header-Felder, deren Wert als Variable konfiguriert ist. [Weitere Informationen](../action/about-custom-action-configuration.md).

Geben Sie bei Bedarf den Wert der dynamischen Header-Felder an:

1. Wählen Sie in der Journey die benutzerdefinierte Aktion aus.
1. Klicken Sie im Abschnitt **[!UICONTROL URL-Konfiguration]** im Konfigurationsbereich auf das Stiftsymbol neben dem Header-Feld.

   ![](../assets/journey-dynamicheaderfield.png)

1. Wählen Sie ein Feld aus und klicken Sie auf **[!UICONTROL OK]**.

## Aktionsparameter

Im Abschnitt **[!UICONTROL Aktionsparameter]** sehen Sie die Nachrichtenparameter, die als _Variable_ definiert sind. Für diese Parameter können Sie festlegen, wo diese Informationen abgerufen werden sollen (Beispiel: Ereignisse, Datenquellen), Werte manuell übergeben oder den erweiterten Ausdruckseditor für erweiterte Anwendungsfälle verwenden. Erweiterte Anwendungsfälle können Datenmanipulationen und andere Funktionen sein. [Weitere Informationen](../expression/expressionadvanced.md).

**Verwandte Themen**

[Konfigurieren einer Aktion](../action/about-custom-action-configuration.md)
