---
product: adobe campaign
solution: Journey Orchestration
title: Identitätsfelder für journeyStep-Ereignisse
description: Identitätsfelder für journeyStep-Ereignisse
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 100%

---


# Identitätsfelder für journeyStep-Ereignisse{#sharing-identity-fields}

Dieses Mixin gilt speziell für journeyStepEvent: Das Ereignis bezieht sich auf die Journey und verfügt nicht über die identityMap zur Beschreibung der Profilidentität (sofern vorhanden).

Für journeyStepEvent müssen auch Identitätsfelder hinzugefügt werden:

## profileID

Profilkennung

Typ: Zeichenfolge

## profileNamespace

Namespace der Profilkennung

Typ: Zeichenfolge