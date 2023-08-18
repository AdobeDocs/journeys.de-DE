---
product: adobe campaign
title: Verwenden des erweiterten Ausdruckseditors
description: Erfahren Sie, wie Sie erweiterte Ausdrücke erstellen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 100%

---

# Beispiele für erweiterte Ausdrücke

Der erweiterte Ausdruckseditor kann verwendet werden, um Bedingungen zum Filtern von Benutzern in Ihren Journeys zu erstellen. Mit diesen Bedingungen können Sie Benutzer nach Uhrzeit, Datum, Ort, Dauer oder Aktionen wie Kauf oder Warenkorbabbruch ansprechen, damit diese in der Journey erneut angesprochen werden können.

>[!NOTE]
>
>Ereignisse beginnen mit @, Datenquellen mit #.

## Erstellen von Bedingungen anhand von Erlebnisereignissen

Sie benötigen den erweiterten Ausdruckseditor, um Abfragen zu Zeitreihen wie eine Liste der Käufe oder vergangene Klicks auf Nachrichten durchzuführen. Solche Abfragen können nicht mit dem einfachen Editor ausgeführt werden.

Die Erlebnisereignisse werden von Adobe Experience Platform als Sammlung in umgekehrter chronologischer Reihenfolge abgerufen. Entsprechend gilt:

* Die Funktion „first“ gibt das neueste Ereignis zurück.
* Die Funktion „last“ gibt das älteste zurück.

Angenommen, Sie möchten Kunden mit einem Warenkorbabbruch in den letzten sieben Tagen ansprechen. Dazu möchten Sie diesen Kunden, wenn sie sich in der Nähe eines Geschäfts befinden, eine Nachricht mit einem Angebot für Artikel in diesem Geschäft senden, an denen die Kunden interessiert waren.

**Erstellen Sie dazu die folgenden Bedingungen:**

Sprechen Sie in erster Linie Kunden an, die den Online-Store besucht, aber in den letzten sieben Tagen keine Bestellung abgeschlossen haben.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Dieser Ausdruck sucht nach allen Ereignissen für diesen Benutzer, die in den letzten sieben Tagen spezifiziert wurden:**

Anschließend werden alle Ereignisse vom Typ addtocart ausgewählt, die nicht in completePurchase umgewandelt wurden.

>[!NOTE]
>
>Um Felder schnell in den Ausdruck einzufügen, doppelklicken Sie auf das Feld im linken Panel des Editors.

Der angegebene Zeitstempel dient als der Datums-/Uhrzeitwert, der zweite bezeichnet die Anzahl der Tage.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Dieser Ausdruck gibt einen booleschen Wert zurück.

**Erstellen Sie nun einen Ausdruck, der überprüft, ob das Produkt vorrätig ist**

* Dieser Ausdruck such im Inventar nach dem Mengenfeld eines Produkts mit der Angabe, dass es größer als 0 sein soll.

`#{Inventory.fieldgroup3.quantity} > 0`

* Rechts werden die erforderlichen Werte angegeben. Hier müssen wir den Ort des Geschäfts abrufen, der der Position des Ereignisses „ArriveLumaStudio“ zugeordnet ist:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Geben Sie die SKU unter Verwendung der `first`-Funktion an, um die jüngste „addToCart“ -Interaktion abzurufen:

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

Von dort können Sie einen weiteren Pfad zu Ihrer Journey hinzufügen, wenn das Produkt nicht im Store ist, und eine Benachrichtigung mit einem Interaktionsangebot senden. Konfigurieren Sie die Nachrichten entsprechend und verwenden Sie Personalisierungsdaten, um die Nachricht zu verbessern.

## Beispiele für Zeichenfolgenmanipulationen mit dem erweiterten Ausdruckseditor

**In Bedingungen**

Diese Bedingung ruft nur die Geofence-Ereignisse ab, die in &quot;Arlington&quot; ausgelöst wurden:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Erklärung: Dies ist ein strikter Zeichenfolgenvergleich (Groß-/Kleinschreibung beachten), der einer Abfrage im einfachen Modus entspricht, die `equal to` mit der aktivierten Option `Is sensitive` verwendet.

Die gleiche Abfrage mit der deaktivierten Option `Is sensitive` generiert den folgenden Ausdruck im erweiterten Modus:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In Aktionen**

Mit dem folgenden Ausdruck können Sie die CRM-ID in einem Feld zur Aktionspersonalisierung definieren:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Erläuterung: In diesem Beispiel werden die `substr`- und `lastIndexOf`-Funktionen verwendet, um geschweifte Klammern zu entfernen, die die CRM-ID einschließen, die bei einem App-Startereignis übergeben wurde.

Weitere Informationen zur Verwendung des erweiterten Ausdruckseditors finden Sie in [diesem Video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html?lang=de).
