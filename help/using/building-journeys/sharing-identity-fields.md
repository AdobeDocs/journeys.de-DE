---
product: adobe campaign
title: Identitätsfelder für journeyStep-Ereignisse
description: Identitätsfelder für journeyStep-Ereignisse
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '104'
ht-degree: 100%

---

# Identitätsfelder für journeyStep-Ereignisse {#sharing-identity-fields}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Dieses Mixin gilt speziell für journeyStepEvent: Das Ereignis bezieht sich auf die Journey und verfügt nicht über die identityMap zur Beschreibung der Profilidentität (sofern vorhanden).

Für journeyStepEvent müssen auch Identitätsfelder hinzugefügt werden:

## profileID

Profilkennung

Typ: Zeichenfolge

## profileNamespace

Namespace der Profilkennung

Typ: Zeichenfolge
