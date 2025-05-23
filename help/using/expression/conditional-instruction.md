---
product: adobe campaign
title: Bedingte Anweisung (if, then, else)
description: Erfahren Sie mehr über die bedingte Anweisung
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '209'
ht-degree: 100%

---

# Bedingte Anweisung (if, then, else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Die bedingte Anweisung (if, then, else) wird im erweiterten Editor unterstützt. Sie ermöglicht die Definition komplexerer Ausdrücke. Sie umfasst die folgenden Elemente:

* **[!UICONTROL if]**: die Bedingung, die zuerst ausgewertet werden soll.
* **[!UICONTROL then]**: der auszuwertende Ausdruck, falls das Ergebnis der Auswertung der Bedingung wahr ist.
* **[!UICONTROL else]**: der auszuwertende Ausdruck, falls das Ergebnis der Auswertung der Bedingung falsch ist.

>[!NOTE]
>
>Alle Ausdrücke müssen in Klammern gesetzt werden.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` muss einen booleschen Wert (**boolean**) zurückgeben.

`<expression2>` und `<expression3>` müssen denselben Typ oder kompatible Typen aufweisen. Folgende Signaturen und zurückgegebene Typen werden unterstützt:

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Verwendung**

Mit der bedingten Anweisung können Sie den Workflow der Journey optimieren, indem Sie die Anzahl der Bedingungsaktivitäten reduzieren. Beispielsweise können Sie innerhalb derselben Aktionsaktivität zwei Alternativen für eine Felddefinition angeben, wobei nur ein Bedingungsausdruck verwendet wird.

Beispiel für eine Aktionsaktivität (für ein Feld, das eine Zeichenfolge als Ergebnis der bedingten Anweisung erwartet):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
