---
product: adobe campaign
title: matchRegExp
description: Erfahren Sie mehr über die Funktion „matchRegExp“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '86'
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
