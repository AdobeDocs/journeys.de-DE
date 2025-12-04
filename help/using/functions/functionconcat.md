---
product: adobe campaign
title: concat
description: Erfahren Sie mehr über die Funktion „concat“
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 100%

---

# concat {#concat}

Verkettet zwei Zeichenfolgenparameter oder eine Liste von Zeichenfolgen.

## Kategorie

Zeichenfolge

## Funktionssyntax

`concat(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste | listString |
| string | Zeichenfolge |

## Signatur und zurückgegebener Typ

`concat(<string>,<string>)`

`concat(<listString>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`concat("Hello","World")`

Gibt „HelloWorld“ zurück.

`concat(["Hello"," ","World"])`

Gibt „Hello World“ zurück.
