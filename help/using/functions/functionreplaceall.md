---
title: replaceAll
description: Erfahren Sie mehr über die Funktion replaceAll
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# replaceAll {#replaceAll}

Ersetzt alle Vorkommnisse, die mit der Zielzeichenfolge übereinstimmen, durch die Ersatzzeichenfolge in der Basiszeichenfolge.

Die Ersetzung erfolgt vom Anfang der Zeichenfolge bis zum Ende, wenn z. B. &quot;aa&quot;durch &quot;b&quot;in der Zeichenfolge &quot;aaa&quot;ersetzt wird, führt dies zu &quot;ba&quot;anstatt zu &quot;ab&quot;.

## Kategorie

String

## Funktionssyntax

`replaceAll(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|--------------|
| base | string |
| target | string |
| Ersatz | string |

## Unterschrift und zurückgegebener Typ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`replaceAll("Hello World", "l", "x")`

Gibt &quot;Hexxo Worxd&quot;zurück.
