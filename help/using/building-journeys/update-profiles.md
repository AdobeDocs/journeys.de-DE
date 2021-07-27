---
product: adobe campaign
title: Springen zwischen Journeys
description: Springen zwischen Journeys
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 100%

---

# Profil aktualisieren {#update-profile}

Mit der Aktionsaktivität **[!UICONTROL Profil aktualisieren]** können Sie ein vorhandenes Adobe Experience Platform-Profil mit Informationen aus dem Ereignis, aus einer Datenquelle oder mit einem bestimmten Wert aktualisieren.

## Wichtige Hinweise     

* Die Aktion **Profil aktualisieren** kann nur in Journeys verwendet werden, die mit einem Ereignis beginnen, das über einen Namespace verfügt.
* Die Aktion aktualisiert nur die vorhandenen Felder, sie erstellt keine neuen Profilfelder.
* Sie können die Aktion **Profil aktualisieren** nicht verwenden, um Erlebnisereignisse zu generieren, z. B. einen Kauf.
* Wie bei jeder anderen Aktion können Sie einen alternativen Pfad für den Fall eines Fehlers oder einer Zeitüberschreitung definieren und Sie können nicht zwei Aktionen parallel platzieren.
* Die an Platform gesendete Aktualisierungsanfrage erfolgt schnell, jedoch nicht sofort/innerhalb einer Sekunde. Es dauert normalerweise ein paar Sekunden, manchmal aber auch mehr, ohne dass dies garantiert werden kann. Wenn eine Aktion beispielsweise „Feld 1“ verwendet, das durch eine davor positionierte Profilaktualisierungsaktion aktualisiert wurde, sollte nicht davon ausgegangen werden, dass „Feld 1“ durch die Aktion aktualisiert wird.
* Im Testmodus wird die Aktualisierung des Profils nicht simuliert. Die Aktualisierung wird für das Testprofil durchgeführt.

## Verwenden der Profilaktualisierung

1. Entwerfen Sie Ihre Journey, indem Sie mit einem Ereignis beginnen. Siehe diesen [Abschnitt](../building-journeys/journey.md).

1. Legen Sie im Abschnitt **Aktion** der Palette die Aktivität **Profil aktualisieren** auf der Arbeitsfläche ab.

   ![](../assets/profileupdate0.png)

1. Wählen Sie ein Schema aus der Liste aus.

1. Klicken Sie auf **Felder**, um das Feld auszuwählen, das Sie aktualisieren möchten. Es kann nur ein Feld ausgewählt werden.

   ![](../assets/profileupdate2.png)

1. Wählen Sie einen Datensatz aus der Liste aus.

   >[!NOTE]
   >
   >Die Aktion **Profil aktualisieren** aktualisiert die Profildaten in Echtzeit, aktualisiert jedoch keine Datensätze. Die Datensatzauswahl ist erforderlich, da das Profil ein Datensatz ist, der mit einem Datensatz verknüpft ist.

1. Klicken Sie auf das Feld **Wert**, um den gewünschten Wert zu definieren:

   * Mit dem einfachen Ausdruckseditor können Sie ein Feld aus einer Datenquelle oder aus dem eingehenden Ereignis auswählen.

      ![](../assets/profileupdate4.png)

   * Wenn Sie einen bestimmten Wert definieren oder erweiterte Funktionen nutzen möchten, klicken Sie auf **Erweiterter Modus**.

      ![](../assets/profileupdate3.png)

Die Aktivität **Profil aktualisieren** ist jetzt konfiguriert.

![](../assets/profileupdate1.png)
