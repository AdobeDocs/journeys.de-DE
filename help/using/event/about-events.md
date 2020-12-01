---
product: adobe campaign
solution: Journey Orchestration
title: Informationen zu Ereignissen
description: Weitere Informationen zu Ereignissen
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 70%

---


# Allgemeine Funktionsweise {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informationen zu Ereignissen"
>abstract="Ein Ereignis ist mit einer Person verbunden. Es bezieht sich auf das Verhalten einer Person (z. B. eine Person hat ein Produkt gekauft, einen Shop besucht, eine Website verlassen usw.) oder auf etwas, das mit einer Person in Verbindung steht (z. B. eine Person hat 10.000 Treuepunkte erreicht). Diese Ereignisse werden von [!DNL Journey Orchestration] in Journeys überwacht, um die besten nächsten Aktionen zu orchestrieren."

Ein Ereignis ist mit einer Person verbunden. Es bezieht sich auf das Verhalten einer Person (z. B. eine Person hat ein Produkt gekauft, einen Shop besucht, eine Website verlassen usw.) oder auf etwas, das mit einer Person in Verbindung steht (z. B. eine Person hat 10.000 Treuepunkte erreicht). Diese Ereignisse werden von [!DNL Journey Orchestration] in Journeys überwacht, um die besten nächsten Aktionen zu orchestrieren.

Diese Konfiguration wird immer von einem **technischen Anwender** durchgeführt und ist **obligatorisch**, da [!DNL Journey Orchestration] dazu bestimmt ist, Ereignisse zu überwachen.

Mit der Ereigniskonfiguration können Sie festlegen, welche Informationen [!DNL Journey Orchestration] als Ereignisse erhält. Sie können mehrere Ereignisse (in verschiedenen Schritten der Journey) verwenden und mehrere Journeys können dasselbe Ereignis verwenden.

Wenn Sie ein Ereignis bearbeiten, das in einer Entwurfs- oder Live-Journey verwendet wird, können Sie nur den Namen oder die Beschreibung ändern oder Payload-Felder hinzufügen. Die Bearbeitungsmöglichkeiten von Entwurfs- oder Live-Journeys sind stark beschränkt, damit Unterbrechungen von Journeys vermieden werden.

Sie können zwei Typen von Ereignissen definieren:

* **Regelbasierte** Ereignis: dieser Ereignis generiert keine eventID. Mit dem einfachen Ausdruck-Editor definieren Sie einfach eine Regel, die vom System verwendet wird, um die relevanten Ereignis zu identifizieren, die Ihre Reisen auslösen. Diese Regel kann auf einem beliebigen Feld basieren, das in der Ereignis-Payload verfügbar ist, z. B. dem Standort des Profils oder der Anzahl der Artikel, die dem Warenkorb des Profils hinzugefügt wurden.

   >[!CAUTION]
   >
   >Für regelbasierte Ereignisse wird eine Deckelungsregel definiert. Die Anzahl der qualifizierten Ereignisse, die eine Journey verarbeiten kann, wird auf 400.000 pro Minute begrenzt. Für weitere Informationen wenden Sie sich an Ihren Ansprechpartner bei Ihrem Alpha-Programm. Zusätzlich zu dieser Deckelungsregel wird eine Begrenzung auf 5000 Ereignis pro Sekunde auf Fahrtebene definiert.

* **Systemgenerierte** Ereignis: Für diese Ereignis ist eine eventID erforderlich. Dieses eventID-Feld wird beim Erstellen des Ereignisses automatisch generiert. Das System, das das Ereignis schiebt, sollte keine ID generieren, sondern die in der Payload-Vorschau verfügbare weitergeben.

Informationen zum Erstellen eines Ereignisses finden Sie auf dieser [Seite](../event/about-creating.md).

