---
title: Funktionen zur Verwaltung von Sammlungen
description: Erfahren Sie mehr über die Datentypen in den Funktionen zur Verwaltung von Sammlungen
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 100%

---


# Funktionen zur Verwaltung von Sammlungen {#collection-management-functions}

Die Ausdruckssprache bietet auch eine Reihe von Funktionen zum Abfragen von Sammlungen.

Diese Funktionen werden nachfolgend erläutert. In den folgenden Beispielen verwenden wir die Ereignis-Payload, die eine Sammlung enthält:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**Die Funktion „all(`<condition>`)“**

Die Funktion **[!UICONTROL all]** ermöglicht mithilfe eines booleschen Ausdrucks die Definition eines Filters für eine bestimmte Sammlung.

```
<listExpression>.all(<condition>)
```

Beispielsweise können Sie von allen App-Anwendern diejenigen abfragen, die iOS 13 verwenden (boolescher Ausdruck „app used == iOS 13“). Das Ergebnis dieser Funktion ist die gefilterte Liste mit Elementen, die dem booleschen Ausdruck entsprechen (Beispiel: App-Anwender 1, App-Anwender 34, App-Anwender 432).

In einer Aktivität des Typs „Bedingung der Datenquelle“ können Sie überprüfen, ob das Ergebnis der Funktion **[!UICONTROL all]** null ist. Sie können die Funktion **[!UICONTROL all]** auch mit anderen Funktionen wie **[!UICONTROL count]** kombinieren. Weitere Informationen finden Sie unter [Aktivität „Bedingung der Datenquelle“](../building-journeys/condition-activity.md#data_source_condition).

**Beispiel 1:**

Wir möchten überprüfen, ob ein Anwender eine bestimmte Version einer App installiert hat. Zu diesem Zweck rufen wir alle Push-Benachrichtigungstoken für Apps mit der Version 1.0 ab. Anschließend führen wir eine Bedingung mit der Funktion **[!UICONTROL count]** aus, um zu überprüfen, ob die zurückgegebene Liste von Tokens mindestens ein Element enthält.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Das Ergebnis ist wahr.

**Beispiel 2:**

Hier verwenden wir die Funktion **[!UICONTROL count]**, um zu überprüfen, ob in der Sammlung Push-Benachrichtigungstoken vorhanden sind.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Das Ergebnis ist wahr.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Wenn die Filterbedingung in der Funktion **all()** leer ist, gibt der Filter alle Elemente in der Liste zurück. **Um jedoch die Anzahl der Elemente einer Sammlung zu zählen, ist die Funktion „all“ nicht erforderlich.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Das Ergebnis des Ausdrucks ist **3**.

**Beispiel 3:**

Hier prüfen wir, ob ein Kontakt innerhalb der letzten 24 Stunden keine Mitteilungen erhalten hat. Wir filtern die Sammlung von Erlebnisereignissen, die aus der Experience Platform-Datenquelle abgerufen wurden, mithilfe von zwei Ausdrücken, die auf zwei Elementen der Sammlung basieren. Insbesondere wird der Zeitstempel des Ereignisses mit dem von der Funktion **[!UICONTROL nowWithDelta]** zurückgegebenen Wert „dateTime“ verglichen.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Das Ergebnis ist wahr, wenn es kein Erlebnisereignis gibt, das den beiden Bedingungen entspricht.

**Beispiel 4:**

Hier möchten wir überprüfen, ob ein Kontakt in den letzten 7 Tagen mindestens einmal eine App gestartet hat, um z. B. eine Push-Benachrichtigung auszulösen, die den Kontakt zum Start eines Tutorials einlädt.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** ist nur verfügbar, wenn Ereignissammlungen bearbeitet werden, und **currentDataPackField**,
>wenn Datenquellensammlungen bearbeitet werden. Bei der Verarbeitung von Sammlungen mit **[!UICONTROL all]**, **[!UICONTROL first]** und **[!UICONTROL last]** wird
>jedes Element der Sammlung einzeln durchlaufen. **[!UICONTROL currentEventField]** und **currentDataPackField**
>entsprechen dem Element, das in der Schleife verarbeitet wird.

**Die Funktionen „first(`<condition>`)“ und „last(`<condition>`)“**

Die Funktionen **[!UICONTROL first]** und **[!UICONTROL last]** ermöglichen auch die Definition eines Filters für die Sammlung, wobei das erste/letzte Element der Liste zurückgegeben wird, das dem Filter entspricht.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Beispiel 1:**

Dieser Ausdruck gibt das erste Push-Benachrichtigungstoken zurück, das mit Apps verknüpft ist, deren Version 1.0 ist.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Das Ergebnis ist „token_1“.

**Beispiel 2:**

Dieser Ausdruck gibt das letzte Push-Benachrichtigungstoken zurück, das mit Apps verknüpft ist, deren Version 1.0 ist.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Das Ergebnis ist „token_2“.

>[!NOTE]
>
>Die Erlebnisereignisse werden von Experience Platform als Sammlung in umgekehrter chronologischer Reihenfolge abgerufen. Entsprechend gilt:
>* Die Funktion **[!UICONTROL first]** gibt das neueste Ereignis zurück.
>* Die Funktion **[!UICONTROL last]** gibt das älteste zurück.


**Beispiel 3:**

Wir prüfen, ob das erste (neueste) Adobe Analytics-Ereignis mit einem Wert ungleich null für die DMA-ID den Wert „602“ hat.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**Die Funktion „at(`<index>`)“**

Mit der Funktion **[!UICONTROL at]** können Sie anhand eines Index auf ein bestimmtes Element in einer Sammlung verweisen.
Der Index „0“ ist der erste Index der Sammlung.

_`<listExpression>`.at(`<index>`)_

**Beispiel:**

Dieser Ausdruck gibt das zweite Push-Benachrichtigungstoken der Liste zurück.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Das Ergebnis ist „token_2“.