---
title: Metriken und Dimensionen
description: Erfahren Sie mehr über Dimensionen und Metriken, die bei Journey Orchestration verfügbar sind.
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 98%

---


# Metriken und Dimensionen {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Die Versanddaten werden nur ausgefüllt, wenn Sie über Adobe Campaign Standard verfügen.

Hier finden Sie eine Liste aller Komponenten, die in dynamischen Berichten enthalten sind, sowie ihrer Definitionen.

In der Tabelle unten finden Sie eine Liste der Dimensionen, die in Journey-Berichten verwendet werden, sowie ihre Definitionen.

Weiterführende Informationen zur Kompatibilität zwischen Dimensionen und Metriken finden Sie auf dieser [Seite](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Journey-Dimensionen {#MBE_table_wk4_bnj_w2b}

In der Tabelle unten finden Sie eine Liste der Dimensionen, die in Journey-Berichten verwendet werden, sowie ihre Definitionen und Formeln.

| Dimensionen | Definition |
|--- |--- |
| **Aktion** | Liste aller Aktionen (**Aktionsname - Aktionsbezeichnung**), die in Journeys verwendet werden (z. B. Push-Benachrichtigung - Checkout-Bestätigung, E-Mail - Treueprämien). |
| **Datenquelle** | List of data sources (**data source name**) used to enrich data in a journey e.g. Adobe Experience platform, Reservation system. |
| **[!UICONTROL Ereignis]** | Liste aller Ereignisse (**Ereignisname - Ereignisbezeichnung**), die in Journeys zum Einsatz kommen (z. B. Geometrixx-Ereignis - Geometrixx-Checkout). |
| **Feldergruppe** | Liste der Feldergruppen (**Feldergruppenname**), die in Journeys zur Datenanreicherung verwendet werden (z. B. Profilfeldgruppe, Geometrixx-Reservierungssystem). |
| **Journey** | Liste aller Journeys (**Journey-Name**), die im Testmodus und live sind (z. B. Transaktionsabbruch, Benachrichtigung zu Hotelreservierung). |
| **Journey-Version** | Liste aller veröffentlichten Journey-Versionen (**Journey-Name + Nummer der Version**), z. B. Transaktionsabbruch v1, Benachrichtigung zu Hotelreservierung v2. |
| **Orchestrierung** | Liste aller Orchestrierungsaktivitäten (**Bedingung, Ende, Warten**), die definiert sind und in Journeys verwendet werden. |

## Versanddimensionen {#delivery-dimensions}

Die nachstehende Tabelle enthält eine Liste der in Journey-Berichten verwendeten Versanddimensionen sowie ihrer Definitionen und Formeln.

| Dimension | Definition |
|--- |--- |
| **Browser** | Browser, in dem die Nachricht geöffnet oder angeklickt wurde |
| **Versandname** | Titel und Kennung des Versands. |
| **Gerät** | Gerät, mit dem die E-Mail/SMS/Push-Benachrichtigung geöffnet/angezeigt/angeklickt wurde. |
| **Nachrichtentyp** | Der für den Versand verwendete Kanal, beispielsweise E-Mail, SMS, Push-Benachrichtigung oder In-App-Nachricht. |
| **Name der App** | Der Name der App. |
| **Plattform** | Plattform des Geräts, auf dem die Nachricht geöffnet/angezeigt/angeklickt wurde. |
| **[!UICONTROL Push-Plattform]** | Plattform des Geräts, auf dem die Push-Benachrichtigung geöffnet wurde (z. B. iOS oder Android). |
| **Empfänger-Domain** | Die zum Öffnen der E-Mail verwendete Domain. |
| **Tracking-URL** | URL, auf die der Benutzer in der Nachricht geklickt hat. |
| **Kategorie des URL-Trackings** | Die der Tracking-URL zugewiesene Kategorie. |
| **Titel des URL-Trackings** | Der an die URL vergebene Titel, wie „Mirrorseite“, „Kontakt“ oder „Öffnung“. |
| **Variante** | Variante der E-Mail im Fall von A/B-Tests. |


## Journey-Metriken {#MBE_p_p22_c4j_w2b}

In der Tabelle unten finden Sie eine Liste der Metriken, die in Journey-Berichten verwendet werden, sowie ihrer Definitionen und Formeln.

| Metrik | Definition |
|--- |---|
| **Abgeschlossen** | Gesamtzahl der Kontakte, die die Journey normal beendet haben. |
| **Abschlussrate** | Gesamtzahl der Kontakte, die die Journey normal beendet haben, in Bezug auf die Gesamtzahl der Kontakte, die in die Journey eingestiegen sind. |
| **Aktuell** | Gesamtzahl der Kontakte, die sich derzeit in der Journey befinden, d. h. die Zahl der Kontakte, die die Journey begonnen haben, abzüglich der Personen, die die Journey abgebrochen haben bzw. bei denen es zu Fehlern und Zeitüberschreitungen gekommen ist. |
| **Aktuelle Rate** | Gesamtzahl der Kontakte, die sich derzeit in der Journey befinden, in Bezug auf die Zahl der Kontakte, die in die Journey eingestiegen sind. |
| **Eingestiegen** | Gesamtzahl der Ereignisse, die aufgetreten sind, um einen individuellen Einstieg in die Journey zu starten. |
| **Fehler** | Gesamtzahl der Fehler, die während einer Journey aufgetreten sind, jedoch nicht verhindert haben, dass die Journey erfolgreich war. |
| **Fehler in Aktion** | Gesamtzahl der Fehler, die bei Aktionen aufgetreten sind. |
| **Fehler bei Anreicherung** | Gesamtzahl der Fehler, die beim Aufrufen einer Datenquelle/Feldergruppe bei der Datenanreicherung aufgetreten sind. |
| **Fehler bei Ereignis** | Gesamtzahl der Fehler, die bei Ereignissen aufgetreten sind. |
| **Fehlerrate** | Gesamtzahl der bei einer Journey aufgetretenen Fehler in Bezug auf die Gesamtzahl des Auftretens in der Journey. |
| **Ausgeführte Aktion** | Gesamtzahl der für eine Journey durchgeführten Aktionen. |
| **Ausgeführte Anreicherung** | Gesamtzahl der durch Aufruf einer Datenquelle ausgeführten Anreicherungen, um bestimmte Feldergruppen abzurufen. |
| **Ausgeführtes Ereignis** | Gesamtzahl der für eine Journey durchgeführten Aktionen. |
| **Ausgeführte Orchestrierung** | Gesamtzahl der für eine Journey ausgeführten Orchestrierungsobjekte (Ende, Warten, Bedingung). |
| **Fehlgeschlagen** | Gesamtzahl der Journeys, die nicht erfolgreich ausgeführt wurden. |
| **Fehlerrate** | Gesamtzahl der Journeys, die in Bezug auf die Zahl der ausgeführten Journeys nicht erfolgreich ausgeführt wurden. |

## Versandmetriken {#delivery-metrics}

In der Tabelle unten finden Sie eine Liste der Metriken, die in Journey-Berichten verwendet werden, sowie ihrer Definitionen und Formeln.

| Metrik | Definition |
|--- |--- |
| **Auf Blockierungsliste** | Zahl der Empfänger, die eine E-Mail als Spam oder Junk gekennzeichnet haben |
| **Blockierungslistenrate** | Gesamtzahl der Nachrichten auf der Blockierungsliste in Bezug auf die gesendeten Nachrichten. |
| **Bounces + Fehler** | Gesamtzahl der über alle Sendungen hinweg kumulierten Fehler und der automatischen Bounce-Verarbeitung in Bezug auf die Gesamtzahl der gesendeten Nachrichten. |
| **Bounce + Fehlerrate** | Gesamtzahl der Nachrichten, bei denen es zu einem Bounce gekommen ist, in Bezug auf die gesendeten Nachrichten. |
| **Klick** | Zahl der Klicks auf einen Inhalt in einem Versand. |
| **Durchklickrate** | Gesamtzahl der Klicks in einem Versand in Bezug auf die Zahl der gesendeten Nachrichten. |
| **Zugestellt** | Zahl der erfolgreich gesendeten Nachrichten in Bezug auf die Gesamtzahl der gesendeten Nachrichten. |
| **Zustellrate** | Gesamtzahl der erfolgreich zugestellten Nachrichten in Bezug auf die gesendeten Nachrichten. |
| **Fehler** | Gesamtzahl der Fehler, die während einer Journey aufgetreten sind, jedoch nicht verhindert haben, dass die Journey erfolgreich war. |
| **Hardbounce** | Gesamtzahl der permanenten Fehler, beispielsweise eine falsche E-Mail-Adresse. |
| **Hardbounce-Rate** | Gesamtzahl der versendeten Nachrichten, die aufgrund permanenter Fehler fehlgeschlagen sind, in Bezug auf die gesendeten Nachrichten. |
| **Mirrorseite** | Zahl der Empfänger, die auf den Mirrorseiten-Link geklickt haben. |
| **Mirrorseitenrate** | Gesamtzahl der Klicks auf den Mirrorseiten-Link in Bezug auf die Gesamtzahl der zugestellten Sendungen. |
| **Öffnungen** | Anzahl der Öffnungen einer Nachricht in einem Versand. |
| **Öffnungsrate** | Gesamtzahl der geöffneten Nachrichten in Bezug auf die Zahl der zugestellten Nachrichten. |
| **Quarantäne** | Zahl der Bounce-Nachrichten, bei denen eine Adresse unter Quarantäne gestellt wurde |
| **Quarantänerate** | Gesamtzahl der Nachrichten in Quarantäne in Bezug auf die gesendeten Nachrichten. |
| **Zurückgewiesen** | Zahl der Nachrichten, die von SMTP-Servern als Spam gekennzeichnet wurden. |
| **Zurückweisungsrate** | Gesamtzahl der als abgelehnt markierten Nachrichten in Bezug auf die gesendeten Nachrichten. |
| **Verarbeitet/gesendet** | Gesamtzahl der gesendeten Nachrichten für den Versand. |
| **Softbounce** | Gesamtzahl der temporären Fehler, beispielsweise bei einem vollen Posteingang. |
| **Softbounce-Rate** | Gesamtzahl der versendeten Nachrichten, die aus einem temporären Grund fehlgeschlagen sind, in Bezug auf die gesendeten Nachrichten. |
| **Einzelklicks** | Zahl der Empfänger, die auf einen Inhalt in einem Versand geklickt haben. |
| **Einzelöffnungen** | Zahl der Empfänger, die den Versand geöffnet haben. |
| **Abgemeldet** | Zahl der Klicks auf den Abmelde-Link. |
| **Abmelderate** | Gesamtzahl der Abmeldungen durch Empfänger in Bezug auf die gesendeten Nachrichten. |
