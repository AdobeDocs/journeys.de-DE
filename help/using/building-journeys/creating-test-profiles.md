---
product: adobe campaign
title: Erstellen eines Testprofils
description: Erfahren Sie mehr über die Erstellung von Testprofilen
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 100%

---

# Erstellen von Testprofilen {#create-test-profiles}

Bei der Verwendung des Testmodus in einer Journey sind Testprofile erforderlich. Informationen zur Verwendung des Testmodus finden Sie in [diesem Abschnitt](../building-journeys/testing-the-journey.md).

In Adobe Experience Platform gibt es verschiedene Möglichkeiten, ein Testprofil zu erstellen. In dieser Dokumentation konzentrieren wir uns auf zwei Methoden: Hochladen einer [CSV-Datei](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) und Verwenden von [API-Aufrufen](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Sie können auch eine JSON-Datei in einem Datensatz hochladen. Weitere Informationen finden Sie in der [Dokumentation zur Datenaufnahme](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html?lang=de#add-data-to-dataset).

Mit diesen Importmethoden können Sie auch Attribute von Profilen aktualisieren. Auf diese Weise können Sie ein vorhandenes Profil in ein Testprofil umwandeln. Verwenden Sie einfach einen ähnlichen Datei- oder API-Aufruf und schließen Sie nur das Feld „testProfile“ mit dem Wert „true“ ein.

Das Erstellen eines Testprofils ähnelt dem Erstellen von Standardprofilen in Adobe Experience Platform. Weitere Informationen finden Sie in der [Dokumentation zu Echtzeit-Kundenprofilen](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de).

## Voraussetzungen{#test-profile-prerequisites}

Um Profile erstellen zu können, müssen Sie zunächst ein Schema und einen Datensatz in Adobe Experience Platform erstellen.

Zuerst müssen Sie **ein Schema erstellen**. Führen Sie folgende Schritte aus:

1. Klicken Sie in Adobe Experience Platform im linken Menü auf **[!UICONTROL Schemata]**.
   ![](../assets/test-profiles-0.png)
1. Klicken Sie oben rechts auf **[!UICONTROL Schema erstellen]** und wählen Sie dann einen Schematyp aus, z. B. **[!UICONTROL Einzelnes XDM-Profil]**.
   ![](../assets/test-profiles-1.png)
1. Wählen Sie einen Namen für Ihr Schema aus.
1. Klicken Sie im Bereich **[!UICONTROL Mixins]** auf **[!UICONTROL Hinzufügen]**.
   ![](../assets/test-profiles-1-bis.png)
1. Wählen Sie die entsprechenden Mixins aus. Stellen Sie sicher, dass Sie das Mixin **[!UICONTROL Profil-Testdetails]** hinzufügen. Klicken Sie auf **[!UICONTROL Mixin hinzufügen]**.
   ![](../assets/test-profiles-1-ter.png)
Die Liste der Mixins wird im Übersichtsbildschirm des Schemas angezeigt.

   ![](../assets/test-profiles-2.png)
1. Klicken Sie in der Liste der Felder auf das Feld, das Sie als die primäre Identität definieren möchten.
   ![](../assets/test-profiles-3.png)
1. Markieren Sie im rechten Panel **[!UICONTROL Feldeigenschaften]** die Optionen **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** und wählen Sie einen Namespace aus. Wenn die primäre Identität eine E-Mail-Adresse sein soll, wählen Sie den Namespace **[!UICONTROL E-Mail]**. Klicken Sie auf **[!UICONTROL Anwenden]**.
   ![](../assets/test-profiles-4.png)
1. Wählen Sie das Schema aus und aktivieren Sie die Option **[!UICONTROL Profil]** in den **[!UICONTROL Schema-Eigenschaften]**.
   ![](../assets/test-profiles-5.png)
1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!NOTE]
>
>Weitere Informationen zur Erstellung von Schemata finden Sie in der [XDM-Dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de#prerequisites).

Anschließend müssen Sie **den Datensatz erstellen**, in den die Profile importiert werden. Führen Sie folgende Schritte aus:

1. Klicken Sie in Adobe Experience Platform im linken Menü auf **[!UICONTROL Datensätze]** und dann auf **[!UICONTROL Datensatz erstellen]**.
   ![](../assets/test-profiles-6.png)
1. Wählen Sie **[!UICONTROL Datensatz aus Schema erstellen]** aus.
   ![](../assets/test-profiles-7.png)
1. Wählen Sie das zuvor erstellte Schema aus und klicken Sie dann auf **[!UICONTROL Weiter]**.
   ![](../assets/test-profiles-8.png)
1. Wählen Sie einen Namen und klicken Sie dann auf **[!UICONTROL Beenden]**.
   ![](../assets/test-profiles-9.png)
1. Aktivieren Sie die Option **[!UICONTROL Profil]**.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Weitere Informationen zur Erstellung von Datensätzen finden Sie in der [Dokumentation zum Katalogdienst](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de#getting-started).

## Erstellen eines Testprofils mithilfe einer CSV-Datei{#create-test-profiles-csv}

In Adobe Experience Platform können Sie Profile erstellen, indem Sie eine CSV-Datei, die die verschiedenen Profilfelder enthält, in Ihren Datensatz hochladen. Dies ist die einfachste Methode.

1. Erstellen Sie mit einer Tabellenkalkulations-Software eine einfache CSV-Datei.
1. Fügen Sie für jedes erforderliche Feld eine Spalte hinzu. Stellen Sie sicher, dass Sie das primäre Identitätsfeld („personID“ in unserem Beispiel oben) und das Feld „testProfile“ auf „true“ gesetzt hinzufügen.
   ![](../assets/test-profiles-11.png)
1. Fügen Sie pro Profil eine Zeile hinzu und geben Sie die Werte für die einzelnen Felder ein.
   ![](../assets/test-profiles-12.png)
1. Speichern Sie die Tabelle als CSV-Datei. Verwenden Sie als Trennzeichen Kommas.
1. Klicken Sie in Adobe Experience Platform im linken Menü auf **[!UICONTROL Workflows]**.
   ![](../assets/test-profiles-14.png)
1. Wählen Sie **[!UICONTROL CSV einem XDM-Schema zuordnen]** und klicken Sie dann auf **[!UICONTROL Starten]**.
   ![](../assets/test-profiles-16.png)
1. Wählen Sie den Datensatz aus, in den Sie die Profile importieren möchten. Klicken Sie auf **[!UICONTROL Weiter]**.
   ![](../assets/test-profiles-17.png)
1. Klicken Sie auf **[!UICONTROL Datei auswählen]** und wählen Sie Ihre CSV-Datei aus. Klicken Sie nach dem Hochladen der Datei auf **[!UICONTROL Weiter]**.
   ![](../assets/test-profiles-18.png)
1. Ordnen Sie die CSV-Quellfelder den Feldern des Schemas zu und klicken Sie dann auf **[!UICONTROL Beenden]**.
   ![](../assets/test-profiles-19.png)
1. Der Datenimport beginnt. Der Status wechselt von **[!UICONTROL Verarbeitungsvorgang läuft]** zu **[!UICONTROL Erfolg]**. Klicken Sie oben rechts auf **[!UICONTROL Datensatz in der Vorschau ansehen]**.
   ![](../assets/test-profiles-20.png)
1. Vergewissern Sie sich, dass die Testprofile korrekt hinzugefügt wurden.
   ![](../assets/test-profiles-21.png)

Ihre Testprofile werden hinzugefügt und können jetzt beim Testen einer Journey verwendet werden. Siehe [diesen Abschnitt](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Weitere Informationen zu CSV-Importen finden Sie in der [Dokumentation zur Datenaufnahme](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=de#tutorials).

## Erstellen von Testprofilen mithilfe von API-Aufrufen{#create-test-profiles-api}

Sie können Testprofile auch über API-Aufrufe erstellen. Weitere Informationen finden Sie auf dieser [Seite](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

Sie müssen ein Profilschema verwenden, das das Mixin „Profil-Testdetails“ enthält. Die Markierung „testProfile“ ist Teil dieses Mixins.

Achten Sie beim Erstellen eines Profils darauf, diesen Wert zu übergeben: testProfile = true.

Beachten Sie, dass Sie auch ein vorhandenes Profil aktualisieren können, um die Markierung „testProfile“ in „true“ zu ändern.

Hier sehen Sie ein Beispiel für einen API-Aufruf zum Erstellen eines Testprofils:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
