---
product: adobe campaign
title: matchRegExp
description: Erfahren Sie mehr über die Funktion „matchRegExp“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
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
| string | Zeichenfolge |
| regexp | Zeichenfolge |

## Signatur und zurückgegebener Typ

`matchRegExp(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`matchRegExp("Hello World", "Hello\s+World")`

Gibt „true“ zurück.

Erklärung:

Hier prüfen Sie, ob die Zeichenfolge den regulären Ausdruck (Java-Syntax) erfüllt: beginnt mit „Hello“, gefolgt von einer beliebigen Zeichenfolge, und endet mit „World“.
