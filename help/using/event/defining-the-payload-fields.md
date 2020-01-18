---
title: Definieren der Payload-Felder
description: Erfahren Sie, wie Sie die Payload-Felder definieren
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Definieren der Payload-Felder {#concept_yrw_3qt_52b}

Die Payload-Definition ermöglicht es Ihnen, die vom System erwarteten Informationen aus dem Ereignis Ihrer Reise auszuwählen und den Schlüssel zur Identifizierung der Person, die mit dem Ereignis verbunden ist. Die Nutzlast basiert auf der Experience Cloud XDM-Felddefinition. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Wählen Sie ein XDM-Schema aus der Liste und klicken Sie auf das Feld **[!UICONTROL Nutzlast]**oder auf das Symbol**[!UICONTROL  Bearbeiten]** .

   ![](../assets/journey8.png)

   Alle im Schema definierten Felder werden angezeigt. Die Feldliste variiert von Schema zu Schema. Sie können nach einem bestimmten Feld suchen oder die Filter verwenden, um alle Knoten und Felder oder nur die ausgewählten Felder anzuzeigen. Gemäß der Schemadefinition können einige Felder obligatorisch und vorausgewählt sein. Sie können die Auswahl nicht aufheben.

   >[!NOTE]
   >
   >Vergewissern Sie sich, dass Sie das Mixin &quot;orchestration&quot;zum XDM-Schema hinzugefügt haben. Dadurch wird sichergestellt, dass Ihr Schema alle erforderlichen Informationen für die Zusammenarbeit mit der Journey Orchestration enthält.

   ![](../assets/journey9.png)

1. Wählen Sie die Felder aus, die Sie von der Veranstaltung erwarten. Dies sind die Bereiche, die der Geschäftsbenutzer während der Reise nutzen wird. Sie müssen auch den Schlüssel enthalten, mit dem die mit dem Ereignis verbundene Person identifiziert werden kann (siehe [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Das Feld &quot; **[!UICONTROL eventID]**&quot;wird automatisch in die Liste der ausgewählten Felder eingefügt, damit die Reiseorganisation das Ereignis identifizieren kann. Das System, das das Ereignis durchführt, sollte keine ID generieren. Es sollte die ID verwenden, die in der Nutzdatenvorschau verfügbar ist. Näheres wird im Abschnitt[](../event/previewing-the-payload.md)beschrieben.

1. Wenn Sie die erforderlichen Felder ausgewählt haben, klicken Sie auf **[!UICONTROL Speichern]**oder drücken Sie die**[!UICONTROL  Eingabetaste]**.

   ![](../assets/journey11.png)

   Die Anzahl der ausgewählten Felder wird im Feld **[!UICONTROL Nutzlast]**angezeigt.

   ![](../assets/journey12.png)
