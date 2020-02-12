---
title: matchRegExp
description: Erfahren Sie mehr über die Funktion „matchRegExp“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

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
