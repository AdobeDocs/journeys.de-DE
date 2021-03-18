---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Erfahren Sie mehr über die Funktion „matchRegExp“
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 100%

---


# matchRegExp {#matchRegExp}

Gibt „true“ zurück, wenn die Zeichenfolge im ersten Parameter mit dem regulären Ausdruck im zweiten Parameter übereinstimmt. Weiterführende Informationen finden Sie auf [dieser Seite](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Kategorie

Zeichenfolge

## Funktionssyntax

`matchRegExp(<parameters>)`

## Parameter

| Parameter | Typ |
|--- |--- |
| string | string |
| regexp | string |

## Signatur und zurückgegebener Typ

`matchRegExp(<string>,<string>)`

Gibt „true“ zurück.

## Beispiel

`matchRegExp("Hello World", "Hello\s+World")`

Gibt „true“ zurück.

Erklärung:

Hier prüfen Sie, ob die Zeichenfolge den regulären Ausdruck (Java-Syntax) erfüllt: beginnt mit „Hello“, gefolgt von einer beliebigen Zeichenfolge, und endet mit „World“.
