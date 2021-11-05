---
title: Schrittereignisfeldliste
description: Schrittereignisfeldliste
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 4291dfc91c2fb29d294416ceed022ee00842c870
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 32%

---

# Schrittereignisfeldliste {#sharing-field-list}

Die Felder der Schrittereignisse sind nach Kategorie geordnet.

* Informationsfelder debuggen
* Journey-Felder
* Profilfelder
* Dienstereignisfelder

## debugInfo

| Feldname | Typ | Beschreibung |
|---|---|------------|
| requestId | Zeichenfolge | Die von Journey Orchestration verwendete Anfrage-ID zum Verfolgen des Anfrageflusses. |

## Journey

Diese Feldergruppe wird im Journey-Schema verwendet (in Verbindung mit journeyStepEvent). Es enthält die folgenden Felder:

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Kennung für die angegebene Journey |
| VersionID | Zeichenfolge | Kennung der Journey-Version. Diese Kennung stellt die Identität einer Journey dar |
| name | Zeichenfolge | Name der Journey |
| description | Zeichenfolge | Beschreibung der Journey |
| version | Zeichenfolge | Version, dargestellt als `major`.`minor` |

## profile

Diese Feldergruppe ist spezifisch für journeyStepEvent: Dieses Ereignis steht im Zusammenhang mit Journey und verfügt nicht über die identityMap, die die Profilidentität beschreibt, sofern vorhanden.

Für journeyStepEvent müssen auch Identitätsfelder hinzugefügt werden:

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Die Profilkennung identifiziert das in einer Journey gesendete/verwendete Profil. Beispiel: foo@adobe.com |
| namespace | Zeichenfolge | In diesem Feld wird der Namespace beschrieben, auf den das in der Journey verwendete Profil verweist. Beispiel: E-Mail, ECID |

## serviceEvents

Dieses Mixin enthält alle Felder, die einem Profilexport-Auftrag entsprechen.

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Die Kennung des vom Segmentexport ausgelösten Auftrags |
| status | Zeichenfolge | Der Status des Segmentexportauftrags: in die Warteschlange gestellt, gestartet, fertig gestellt |
| exportCountTotal | Ganzzahl | Der maximale Wert des Segmentexportauftrags |
| exportCountRealized | Ganzzahl | Die tatsächliche Anzahl von Segmenten, die über den Auftrag exportiert wurden |
| exportCountFailed | Ganzzahl | Die Anzahl der Segmente, die beim Exportieren durch den Auftrag fehlgeschlagen sind |
| exportSegmentID | Zeichenfolge | Die Kennung des zu exportierenden Segments |
| eventType | Zeichenfolge | Der Ereignistyp, der angibt, ob es sich um ein Fehlerereignis von info -Ereignis handelt: Info, Fehler |
| eventCode | Zeichenfolge | Der Fehlercode, der den Grund für den entsprechenden eventType angibt |

## stepEvents

Diese Kategorie enthält die Felder für das ursprüngliche Schrittereignis. Siehe diesen [Abschnitt](../building-journeys/sharing-legacy-fields.md).
