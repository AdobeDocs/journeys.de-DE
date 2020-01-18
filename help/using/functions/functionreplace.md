---
title: ersetzen
description: Informationen zum Funktionsaustausch
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# replace {#replace}

Ersetzt das erste Vorkommen, das mit der Zielzeichenfolge übereinstimmt, durch die Ersatzzeichenfolge in der Basiszeichenfolge.

Die Ersetzung erfolgt vom Anfang der Zeichenfolge bis zum Ende, wenn z. B. &quot;aa&quot;durch &quot;b&quot;in der Zeichenfolge &quot;aaa&quot;ersetzt wird, führt dies zu &quot;ba&quot;anstatt zu &quot;ab&quot;.

## Kategorie

String

## Funktionssyntax

`replace(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|--------------|
| base | string |
| target | string |
| Ersatz | string |

## Unterschrift und zurückgegebener Typ

`replace(<base>,<target>,<replacement>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`replace("Hello World", "l", "x")`

Gibt &quot;Hexlo World&quot;zurück.
