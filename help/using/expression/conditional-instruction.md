---
product: adobe campaign
solution: Journey Orchestration
title: Bedingte Anweisung (if, then, else)
description: Erfahren Sie mehr über die bedingte Anweisung
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 98%

---


# Bedingte Anweisung (if, then, else) {#section_cdz_lsk_w3b}

Die bedingte Anweisung (if, then, else) wird im erweiterten Editor unterstützt. Sie ermöglicht die Definition komplexerer Ausdrücke. Sie umfasst die folgenden Elemente:

* **[!UICONTROL if]**: die Bedingung, die zuerst ausgewertet werden soll.
* **[!UICONTROL then]**: der auszuwertende Ausdruck, falls das Ergebnis der Auswertung der Bedingung wahr ist.
* **[!UICONTROL else]**: der auszuwertende Ausdruck, falls das Ergebnis der Auswertung der Bedingung falsch ist.

>[!NOTE]
>
>Alle Ausdrücke müssen in Klammern gesetzt werden.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` muss einen booleschen Wert (**boolean**) zurückgeben.

`<expression2>` und `<expression3>` müssen denselben Typ oder kompatible Typen aufweisen. Folgende Signaturen und zurückgegebene Typen werden unterstützt:

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Verwendung**

Mit der bedingten Anweisung können Sie den Workflow der Journey optimieren, indem Sie die Anzahl der Bedingungsaktivitäten reduzieren. Beispielsweise können Sie innerhalb derselben Aktionsaktivität zwei Alternativen für eine Felddefinition angeben, wobei nur ein Bedingungsausdruck verwendet wird.

Beispiel für eine Aktionsaktivität (für ein Feld, das eine Zeichenfolge als Ergebnis der bedingten Anweisung erwartet):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
