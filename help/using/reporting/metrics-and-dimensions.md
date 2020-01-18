---
title: Metriken und Dimensionen
description: Erfahren Sie mehr über Dimensionen und Metriken, die für die Reiseorganisation verfügbar sind
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Metriken und Dimensionen {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Bereitstellungsdaten werden nur ausgefüllt, wenn Sie über Adobe Campaign Standard verfügen.

Hier finden Sie die Liste aller in dynamischen Berichten verfügbaren Komponenten sowie deren Definitionen.

Die nachstehende Tabelle enthält eine Liste der in Reiseberichten verwendeten Dimensionen und deren Definitionen.

To learn more on compatibility between dimensions and metrics, refer to [this page](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Reisedimensionen {#MBE_table_wk4_bnj_w2b}

Die nachstehende Tabelle enthält eine Liste der in Reiseberichten verwendeten Dimensionen, deren Definitionen und Formeln.

| Dimensionen | Definition |
|--- |--- |
| **Aktionen** | Liste aller Aktionen (**Aktionsname - Aktionsbezeichnung**), die auf Reisen verwendet werden, z.B. Push - Checkout-Bestätigung, E-Mail - Rewards-Treue. |
| **Datenquelle** | Liste der Datenquellen (Name der **Datenquelle**), die zur Datenbereicherung in einer Reise verwendet werden, z.B. Erlebnis-Plattform, Reservierungssystem. |
| **[!UICONTROL Event]** | Liste aller Ereignisse (**Ereignisname - Ereignisbezeichnung**), die bei Reisen verwendet werden, z. B. Geometrixx-Ereignis - Geometrixx-Checkout. |
| **Verwendete** | Liste der Feldgruppen (**Feldgruppenname**), die zur Datenbereicherung bei Reisen verwendet werden, z. B. Profilfeldgruppe, Geometrixx Reservierungssystem. |
| **Journey** | Liste aller Fahrten (**Reisename**) im Testmodus und live, z.B. Warenkorbabbruch, Hotelreservierungsmeldung. |
| **Reiseversion** | Liste aller veröffentlichten Reiseversionen (**Reisename und Versionsnummer**), z.B. Warenkorbabbruch v1, Hotelreservierungsbenachrichtigung v2. |
| **Orchestrierung** | Liste aller Orchesteraktivitäten (**Bedingung, Ende, Warten**), die für Fahrten definiert und verwendet werden. |

## Auslieferungsdimensionen {#delivery-dimensions}

Die nachstehende Tabelle enthält eine Liste der in Reiseberichten verwendeten Auslieferungsdimensionen, deren Definitionen und Formeln.

| Dimension | Definition |
|--- |--- |
| **Browser** | Browser, in dem die Nachricht geöffnet oder angeklickt wurde |
| **Bereitstellungsname** | Titel und Kennung des Versands |
| **Gerät** | Gerät, auf dem die E-Mail/SMS/Push-Benachrichtigung geöffnet/angesehen/angeklickt wurde. |
| **Nachrichtentyp** | Der für den Versand verwendete Kanal, beispielsweise E-Mail, SMS, Push-Benachrichtigung oder In-App-Nachricht |
| **Name der Mobile App** | Name der Mobile App |
| **Plattform** | Plattform des Geräts, auf dem die Nachricht geöffnet/angesehen/angeklickt wurde |
| **[!UICONTROL Push-Plattform]** | Plattform des Geräts, auf dem die Push-Benachrichtigung geöffnet wurde, wie iOS oder Android |
| **Empfänger-Domain** | Die zum Öffnen der E-Mail verwendete Domain |
| **Tracking-URL** | URL, die der Benutzer in der Nachricht angeklickt hat |
| **Kategorie des URL-Trackings** | Die der Tracking-URL zugewiesene Kategorie |
| **Titel des URL-Trackings** | Der an die URL vergebene Titel, wie &quot;Mirrorseite&quot;, &quot;Kontakt&quot; oder &quot;Öffnung&quot;. |
| **Variante** | Variante der E-Mail im Fall von A/B-Tests |


## Reisemetriken {#MBE_p_p22_c4j_w2b}

Die nachstehende Tabelle enthält eine Liste der in Reiseberichten verwendeten Metriken, deren Definitionen und Formeln.

| Metrik | Definition |
|--- |---|
| **Abgeschlossen** | Gesamtzahl der Personen, die die Reise normal beendet haben. |
| **Abschlussrate** | Gesamtzahl der Personen, die die Reise normal beendet haben, im Vergleich zur Gesamtzahl der Personen, die die Reise betreten haben. |
| **Aktuell** | Die Gesamtzahl der Personen, die sich derzeit auf der Reise befinden, d. h. die Anzahl der Eingaben abzüglich der Personen, die die Reise abgebrochen haben, Fehler und Zeitüberschreitungen. |
| **Aktueller Zinssatz** | Gesamtzahl der Personen, die sich derzeit auf der Reise befinden, im Vergleich zur Anzahl der Personen, die die Reise betreten haben. |
| **Eingestiegen** | Gesamtanzahl der Ereignisse, die aufgetreten sind, um einen einzelnen Eintrag auf der Reise zu starten. |
| **Fehler** | Gesamtanzahl der Fehler, die während einer Reise aufgetreten sind, die jedoch nicht daran gehindert wurden, erfolgreich zu sein. |
| **Fehler in Aktion** | Gesamtanzahl der Fehler, die bei Aktionen aufgetreten sind. |
| **Fehler bei der Anreicherung** | Gesamtanzahl der Fehler, die bei einer Datenanreicherung beim Aufruf einer Datenquelle/Feldgruppe aufgetreten sind. |
| **Fehler beim Ereignis** | Gesamtanzahl der Fehler, die bei Ereignissen aufgetreten sind. |
| **Fehlerrate** | Gesamtzahl der während einer Reise aufgetretenen Fehler im Vergleich zur Gesamtzahl der Vorfälle auf der Reise. |
| **Ausgeführte Aktion** | Gesamtzahl der durchgeführten Aktionen für eine Reise. |
| **Ausgeführte Anreicherung** | Die Gesamtzahl der durch Aufruf einer Datenquelle ausgeführten Anreicherungen, um bestimmte Feldgruppen abzurufen. |
| **Ausgeführtes Ereignis** | Gesamtzahl der durchgeführten Aktionen für eine Reise. |
| **Vollstreckte Orchestrierung** | Gesamtanzahl der für eine Reise ausgeführten Orchesterationsobjekte (Ende, Warten, Bedingung). |
| **Fehlgeschlagen** | Gesamtzahl der Fahrten, die nicht erfolgreich durchgeführt wurden. |
| **Fehlerhafte Rate** | Gesamtzahl der Fahrten, die im Vergleich zur Anzahl der Fahrten nicht erfolgreich durchgeführt wurden. |

## Bereitstellungsmetriken {#delivery-metrics}

Die nachstehende Tabelle enthält eine Liste der Metriken, die in Fahrtenberichten verwendet werden, deren Definitionen und Formeln.

| Metrik | Definition |
|--- |--- |
| **Auf Blacklist** | Anzahl der Empfänger, die eine E-Mail als Spam oder Junk gekennzeichnet haben |
| **Blacklist-Rate** | Die Gesamtzahl der Nachrichten, die als auf der schwarzen Liste erscheinen, im Vergleich zu den gesendeten Nachrichten. |
| **Bounces + Fehler** | Gesamtzahl der über alle Sendungen hinweg kumulierten Fehler und der automatischen Bounce-Verarbeitung in Bezug auf die Gesamtzahl der gesendeten Nachrichten |
| **Absprung- und Fehlerquote** | Gesamtanzahl der Nachrichten, die im Vergleich zu den gesendeten Nachrichten abgeschnitten haben. |
| **Klicken** | Die Anzahl der Klicks auf einen Inhalt in einem Versand. |
| **Durchklickrate** | Gesamtanzahl der Klicks in einer Bereitstellung im Vergleich zur Anzahl der gesendeten Nachrichten. |
| **Zugestellt** | Anzahl der erfolgreich gesendeten Nachrichten in Bezug auf die Gesamtzahl der gesendeten Nachrichten |
| **Zustellrate** | Die Gesamtzahl der erfolgreich ausgelieferten Nachrichten im Vergleich zu den gesendeten Nachrichten. |
| **Fehler** | Gesamtanzahl der Fehler, die während einer Reise aufgetreten sind, die jedoch nicht daran gehindert wurden, erfolgreich zu sein. |
| **Hardbounce** | Gesamtzahl der permanenten Fehler, beispielsweise einer falschen E-Mail-Adresse |
| **Hardbounce-Rate** | Gesamtanzahl der Auslieferungen, die aufgrund permanenter Fehler im Vergleich zu den gesendeten Nachrichten fehlgeschlagen sind. |
| **Mirrorseite** | Die Anzahl der Empfänger, die den Mirrorseiten-Link angeklickt haben |
| **Mirrorseitenrate** | Gesamtanzahl der Klicks auf den Link der Spiegelseite im Vergleich zu den insgesamt bereitgestellten Nachrichten. |
| **Öffnungen** | Anzahl der Öffnungen einer Nachricht in einem Versand. |
| **Öffnungsrate** | Gesamtanzahl der geöffneten Nachrichten im Vergleich zur Anzahl der gesendeten Nachrichten. |
| **Quarantäne** | Anzahl der Bounce-Nachrichten, aufgrund derer eine Adresse unter Quarantäne gestellt wurde |
| **Quarantänerate** | Gesamtzahl der Quarantäne im Vergleich zu den gesendeten Meldungen. |
| **Zurückgewiesen** | Anzahl der Sendungen, die von SMTP-Servern als Spam gekennzeichnet wurden |
| **Zurückweisungsrate** | Gesamtzahl der als abgelehnt markierten Nachrichten im Vergleich zu den gesendeten Nachrichten. |
| **Verarbeitet/gesendet** | Gesamtzahl der gesendeten Nachrichten |
| **Softbounce** | Gesamtzahl der temporären Fehler, beispielsweise einer vollen Inbox |
| **Softbounce-Rate** | Gesamtanzahl der Auslieferungen, die aus temporären Gründen im Vergleich zu den gesendeten Nachrichten fehlgeschlagen sind. |
| **Einzelklicks** | Anzahl der Empfänger, die einen Inhalt in einem Versand angeklickt haben |
| **Einzelöffnungen** | Anzahl der Empfänger, die den Versand geöffnet haben |
| **Abgemeldet** | Gesamtanzahl der Klicks auf den Abmelde-Link. |
| **Abmelderate** | Gesamtanzahl der Abmeldeabbrüche nach Empfänger im Vergleich zu den bereitgestellten Nachrichten. |
