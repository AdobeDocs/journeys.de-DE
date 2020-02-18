---
title: Versionshinweise
description: Versionshinweise
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Versionshinweise {#release-notes}

Auf dieser Seite werden alle neuen Funktionen und Verbesserungen bei der Orchestrierung der Customer Journey aufgelistet.
Sie können auch den Abschnitt [Aktualisierungen der Dokumentation](../release-notes/documentation-updates.md) lesen.

## Version Q1 - Februar 2019 {#q1-release---february-2019}

**Zeitzonenmanagement**

Zeitzonen werden jetzt auf Reiseebene verwaltet. In den Reiseeigenschaften wurden zwei Parameter hinzugefügt:

![](../assets/rn-timezone.png)

* Mit der Dropdownliste **Zeitzone** können Sie eine bestimmte Zeitzone auswählen. Standardmäßig wird die Zeitzone des Browsers verwendet.

* Mit dem Kontrollkästchen **Profilzeitzone** können Sie die Profilzeitzone der Erlebnisplattform der Person verwenden, die die Reise beginnt, sofern verfügbar. Andernfalls wird die in der Dropdown-Liste definierte Zeitzone verwendet. Diese Funktion ist nicht mit Reisen ohne Namespace kompatibel.

**Kontexthilfe**

Eine kontextabhängige Hilfefunktion ist jetzt in den verschiedenen Bildschirmen der Journey Orchestration verfügbar. Dadurch können Sie mit einem einzigen Klick direkt auf die Dokumentation über die aktuell von Ihnen verwendete Funktion zugreifen.

Um die kontextbezogene Hilfe anzuzeigen, klicken Sie auf das Symbol &quot;i&quot;in der oberen rechten Ecke des Bildschirms.

Diese Funktion ist derzeit in den Listenbildschirmen &quot;Startseite&quot;, &quot;Datenquellen&quot;, &quot;Ereignisse&quot;und &quot;Aktionen&quot;verfügbar.

**Sonstige Änderungen**

* Im Testmodus können Sie mit einem neuen Parameter den Zeitpeafiner definieren.  Aktivitäten mit Wartezeiten können dauern. So können Sie schnell auf die Testergebnisse zugreifen.

* Im Testmodus können Sie jetzt alle Ereignisse der Reise auslösen.


* Mit einem neuen Parameter können Sie den Zeitpeafiner definieren.  Aktivitäten mit Wartezeiten können dauern. So können Sie schnell auf die Testergebnisse zugreifen.

* Journeys Orchestration ist jetzt in EMEA erhältlich.

* Neues Symbol in der Palette, um nicht verfügbare Elemente anzuzeigen. sans-Namespace. par default.

* Canvas, Abschaltung, Petenton Icone, Qui dit getrennt Knoten.

* Kurzschnitt C ttes les listes

* Benutzeroberfläche der Palette, Suchergebnisse

* Pouvoir capper les call a des APIS extern (Datenquellen oder Aktionen). marque n&#39;accept te que 500 Calls par seconde, elle pourra mettre un capping a 500 call seconds qui evite de surcharger system de loyalty tiers

* logs du test log. Avant status = error. quand auf appalle Systeme. Möglichkeit des Erregers des Codes qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, systeme tiers, error code, error response.

* Anhalten der Löschung

* Reise: Version 1 il te met ist die neueste

1er Mars.


## GA-Version - Dezember 2019 {#ga-release---december-2019}

Die Orchestrierung der Customer Journey ist jetzt allgemein verfügbar.

Erstellen Sie Anwendungsfälle für Echtzeit-Orchestrierung mithilfe von Kontextdaten, die in Ereignissen oder Datenquellen gespeichert sind.

Die Orchestrierung der Customer Journey erlaubt eine Echtzeit-Orchestrierung auf Basis von Kontextdaten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Die Anwendung bestimmt in mehrstufigen Flüssen, die Journeys genannt werden, je nach Profil und Verhalten des Benutzers die nächsten für den Kunden optimalen Aktionen. Dies umfasst sowohl den besten Zeitpunkt als auch die Art der Aktion, z. B. das Senden einer Push-Benachrichtigung über die Transaktionsnachrichtenfunktion von Adobe Campaign Standard (Adobe Campaign Standard erforderlich) oder das Benachrichtigen eines Drittanbietersystems. Diese Entscheidungen werden auf Grundlage von Regeln und Sensei-Werten getroffen.

[Weitere Informationen](../action/working-with-adobe-campaign.md) zur Orchestrierung der Customer Journey.

Zusätzliche Ressourcen:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)