---
title: Einschränkungen für benutzerdefinierte Aktionen
description: Erfahren Sie mehr über die Einschränkungen für benutzerdefinierte Aktionen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Einschränkungen für benutzerdefinierte Aktionen {#concept_lh2_df1_2gb}

Für die Verwendung von benutzerdefinierten Aktionen gelten folgende Einschränkungen:

* Es gibt keine Begrenzung oder Pufferung/Ausgleichung des Sendevolumens.
* Im Falle eines Fehlers werden systematisch zwei weitere Zustellversuche durchgeführt. Sie können die Anzahl der weiteren Zustellversuche nicht entsprechend der erhaltenen Fehlermeldung anpassen.
* Mit dem integrierten **[!UICONTROL Reaktionsereignis]** können Sie auf vordefinierte Aktionen reagieren (siehe [](../building-journeys/event-activities.md)). Wenn Sie auf eine Nachricht reagieren möchten, die über eine benutzerdefinierte Aktion gesendet wird, müssen Sie ein spezielles Ereignis konfigurieren.
* Die URL der benutzerdefinierten Aktion unterstützt keine dynamischen Parameter.
* Es werden nur POST- und PUT-Aufrufmethoden unterstützt.
* Der Name des Abfrageparameters oder der Kopfzeile darf nicht mit „.“ oder „$“ beginnen.
* IP-Adressen sind nicht zulässig.
* Interne Adobe-Adressen (.adobe.) sind nicht zulässig.
