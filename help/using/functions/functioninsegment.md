---
product: adobe campaign
title: inSegment
description: Erfahren Sie mehr über die Funktion „inSegment“
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 100%
---
# inSegment {#inSegment}

Überprüft, ob ein Kontakt zu einem bestimmten Segment gehört.

>[!NOTE]
>
>Sie können bis zu 100 Segmente abrufen.

Der Segmentname muss eine Zeichenfolgenkonstante sein. Er darf weder ein Feldverweis noch ein Ausdruck sein.

Segmente werden in [Adobe Experience Platform](https://platform.adobe.com/segment/overview) definiert. Der Ausdruckseditor bietet eine automatisch ausgefüllte Segmentliste.

Segmente können drei Status haben:

* vorhanden: Entität befindet sich weiterhin im Segment.
* realisiert: Entität tritt in das Segment ein.
* beendet: Entität verlässt das Segment.

Nur Personen mit den Segmentteilnahmestatus **Realisiert** und **Vorhanden** werden als Mitglieder des Segments betrachtet. Weitere Informationen zum Auswerten eines Segments finden Sie in der [Dokumentation zum Segmentierungs-Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=de#interpret-segment-results).

`IF inSegment('segmentName') == true` bedeutet, dass Sie eine segmentMembership mit dem Status „eingetreten/vorhanden“ haben.

`ELSE inSegment('segmentName') == false` bedeutet, dass Sie über eine segmentMitgliedschaft mit dem Status „beendet“ haben.

## Kategorie

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parameter

| Parameter | Beschreibung | Typ |
|--- |--- |--- |
| Segment | Der Segmentname | `<string>` |

## Signatur und zurückgegebener Typ

`inSegment(<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`inSegment("men over 50")`

Erklärung:

Die Funktion gibt **[!UICONTROL true]** zurück, wenn der Kontakt in der Journey-Instanz Teil des Adobe Experience Platform-Segments namens „Herren über 50“ ist, andernfalls wird **[!UICONTROL false]** zurückgegeben.
