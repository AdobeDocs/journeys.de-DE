---
product: adobe campaign
title: Identitätsfelder für journeyStep-Ereignisse
description: Identitätsfelder für journeyStep-Ereignisse
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 100%

---

# Identitätsfelder für journeyStep-Ereignisse {#sharing-identity-fields}

Dieses Mixin gilt speziell für journeyStepEvent: Das Ereignis bezieht sich auf die Journey und verfügt nicht über die identityMap zur Beschreibung der Profilidentität (sofern vorhanden).

Für journeyStepEvent müssen auch Identitätsfelder hinzugefügt werden:

## profileID

Profilkennung

Typ: Zeichenfolge

## profileNamespace

Namespace der Profilkennung

Typ: Zeichenfolge
