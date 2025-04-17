---
title: Liste der Step-Ereignisfelder
description: Liste der Step-Ereignisfelder
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '351'
ht-degree: 100%

---

# Liste der Step-Ereignisfelder {#sharing-field-list}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Die Felder der Step-Ereignisse sind nach Kategorie geordnet.

* Informationsfelder debuggen
* Journey-Felder
* Profilfelder
* Service-Ereignisfelder

## debugInfo

| Feldname | Typ | Beschreibung |
|---|---|------------|
| requestId | Zeichenfolge | Die von Journey Orchestration verwendete Anfrage-ID, um den Fluss einer Anfrage zu verfolgen. |

## journey

Diese Feldergruppe wird im Journey-Schema verwendet (in Verbindung mit journeyStepEvent). Es enthält die folgenden Felder:

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Kennung für die angegebene Journey |
| VersionID | Zeichenfolge | Kennung der Journey-Version. Diese Kennung stellt die Identität einer Journey dar |
| name | Zeichenfolge | Name der Journey |
| description | Zeichenfolge | Beschreibung der Journey |
| version | Zeichenfolge | Version, dargestellt als `major`.`minor` |

## profile

Diese Feldergruppe gilt speziell für journeyStepEvent: Das Ereignis bezieht sich auf die Journey und verfügt nicht über identityMap zur Beschreibung der Profilidentität (sofern vorhanden).

Für journeyStepEvent müssen auch Identitätsfelder hinzugefügt werden:

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Die Profilkennung identifiziert das in einer Journey gesendete/verwendete Profil. Beispiel: foo@adobe.com |
| namespace | Zeichenfolge | In diesem Feld wird der Namespace beschrieben, auf den das in der Journey verwendete Profil verweist. Beispiel: E-Mail, ECID |

## serviceEvents

Dieses Mixin enthält alle Felder, die einem Profilexportvorgang entsprechen.

| Feldname | Typ | Beschreibung |
|---|---|------------|
| ID | Zeichenfolge | Die Kennung des ausgelösten Segmentexportvorgangs |
| status | Zeichenfolge | Der Status des Segmentexportvorgangs: in der Warteschlange, gestartet, abgeschlossen |
| exportCountTotal | Ganzzahl | Der maximale Wert des Segmentexportvorgangs |
| exportCountRealized | Ganzzahl | Die tatsächliche Anzahl von Segmenten, die über den Vorgang exportiert wurden |
| exportCountFailed | Ganzzahl | Die Anzahl der Segmente, bei denen der Export bei dem Vorgang fehlgeschlagen ist |
| exportSegmentID | Zeichenfolge | Die Kennung des exportierten Segments |
| eventType | Zeichenfolge | Der Ereignistyp, der angibt, ob es sich um ein Fehlerereignis eines Informationsereignisses handelt: Info, Fehler |
| eventCode | Zeichenfolge | Der Fehler-Code, der den Grund für den entsprechenden eventType angibt |

## stepEvents

Diese Kategorie enthält die ursprünglichen Step-Ereignisfelder. Siehe diesen [Abschnitt](../building-journeys/sharing-legacy-fields.md).
