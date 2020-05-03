---
title: Verwenden des erweiterten Ausdruckseditors
description: Erfahren Sie, wie Sie erweiterte Ausdrücke erstellen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 28cb56e5f631acd8e2a49cf0bce55e7226892595

---


# Verwenden des erweiterten Ausdruckseditors

Der Editor für erweiterte Ausdrücke kann verwendet werden, um Bedingungen zu erstellen, mit denen Sie Benutzer auf Ihren Reisen filtern können. Diese Bedingungen ermöglichen es Ihnen, Zielgruppen an Zeit, Datum, Ort, Dauer oder Aktionen wie Kauf oder Abbruch von Warenkorb vorzunehmen, damit sie auf die Reise gezielt eingesetzt werden können.

>[!NOTE]
>
>Ereignisse Beginn mit @, Datenquellen mit #.

## Erstellen von Bedingungen für Experience Ereignisses

Der erweiterte Ausdruck-Editor ist obligatorisch, um Abfragen für Zeitreihen wie eine Liste von Käufen oder vergangene Klicks auf Nachrichten durchzuführen. Solche Abfragen können nicht mit dem einfachen Editor ausgeführt werden.

Die Erlebnisereignisse werden von Experience Platform als Sammlung in umgekehrter chronologischer Reihenfolge abgerufen. Entsprechend gilt:

* Die Funktion first gibt das neueste Ereignis zurück.
* Die Funktion last gibt das älteste zurück.

Nehmen wir an, Sie möchten Kunden in den letzten 7 Tagen mit einem Warenkorbabbruch eine Zielgruppe senden, um eine Nachricht zu senden, wenn der Kunde in der Nähe eines Geschäfts ist, mit einem Angebot zu Artikeln, die er wollte, die im Geschäft sind.

**Sie müssen die folgenden Bedingungen erstellen:**

Zunächst einmal Kunden aus der Zielgruppe, die den Online-Shop besucht haben, die Bestellung aber in den letzten 7 Tagen nicht abgeschlossen haben.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Dieser Ausdruck sucht nach allen Ereignissen für diesen Benutzer, die in den letzten 7 Tagen angegeben wurden:**

Anschließend werden alle Ereignis des Typs addtocart ausgewählt, die nicht in eine completePurchase umgewandelt wurden.

>[!NOTE]
>
>Um Felder schnell in den Ausdruck einzufügen, klicken Sie bei Dublette auf das Feld im linken Bereich des Editors.

Der angegebene Zeitstempel dient als Datumszeitwert, der zweite als Anzahl von Tagen.

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    AndNot(in( &quot;completePurchase&quot;, #{experience PlatformDataSource
    .ExperienceEventFieldGroup
    
    
    
    
    
    
    .experienceeventEventAll(inLastDays(currentDataPackField.timestamp, 7)).productData.productInteraction})&quot;

Dieser Ausdruck gibt einen booleschen Wert zurück.

**Erstellen wir nun einen Ausdruck, der überprüft, ob das Produkt auf Lager ist**

* Im Lagerbestand sucht dieser Ausdruck nach dem Mengenfeld eines Produkts und legt fest, dass es größer als 0 sein sollte.

`#{Inventory.fieldgroup3.quantity} > 0`

* Auf der rechten Seite werden die erforderlichen Werte angegeben, hier müssen wir den Speicherort des Stores abrufen, der vom Speicherort des Ereignisses &quot;ArriveLumaStudio&quot; zugeordnet wird:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Geben Sie SKU an, indem Sie die Funktion zum Abrufen der aktuellsten &quot;addToCart&quot;-Interaktion verwenden: `first`

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Von dort können Sie einen weiteren Pfad zu Ihrer Reise hinzufügen, wenn das Produkt nicht im Store ist, und eine Benachrichtigung mit dem Interaktions-Angebot senden. Konfigurieren Sie Nachrichten entsprechend und verwenden Sie Personalisierungsdaten, um die Zielgruppe der Nachricht zu verbessern.

## Beispiele für Zeichenfolgen-Manipulationen mit dem erweiterten Ausdruck-Editor

**unter Bedingungen**

Diese Bedingung ruft nur die Geofence-Ereignis ab, die in &quot;Arlington&quot;ausgelöst werden:

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Erklärung: Dies ist ein strikter Zeichenfolgenvergleich (Groß-/Kleinschreibung beachten), der einer Abfrage im einfachen Modus entspricht, die `equal to` mit `Is sensitive` aktivierter Option verwendet wird.

Die gleiche Abfrage mit `Is sensitive` nicht aktiviertem generiert den folgenden Ausdruck im erweiterten Modus:

    &quot;
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**In Aktionen**

Im folgenden Ausdruck können Sie die CRM-ID in einem Aktionspersonalisierungsfeld definieren:

    &quot;
    substr(@{MobileAppLaunch
    ._myorganisation
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganisation
    .identification
    .crmid}
    }
    
    
    &quot;

Erklärung: In diesem Beispiel werden geschweifte Klammern `substr` und `lastIndexOf` Funktionen entfernt, die die mit einem mobilen App-Launch-Ereignis übergebene CRM-ID einschließen.

Weitere Informationen zur Verwendung des erweiterten Ausdruck-Editors finden Sie in [diesem Video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
