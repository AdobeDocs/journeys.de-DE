---
product: adobe campaign
solution: Journey Orchestration
title: Springen zwischen Journeys
description: Springen zwischen Journeys
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: 8685dfdcbfb414af89b304a6a9a0f9418959909b
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 80%

---


# Profil aktualisieren {#update-profile}

Mit der Aktionsaktivität **[!UICONTROL Profil aktualisieren]** können Sie ein vorhandenes Adobe Experience Platform-Profil mit Informationen aus dem Ereignis, aus einer Datenquelle oder mit einem bestimmten Wert aktualisieren.

## Wichtige Hinweise     

* Die Aktion **Profil aktualisieren** kann nur in Journeys verwendet werden, die mit einem Ereignis beginnen, das über einen Namespace verfügt.
* Die Aktion aktualisiert nur die vorhandenen Felder, sie erstellt keine neuen Profilfelder.
* Sie können die Aktion **Profil aktualisieren** nicht verwenden, um Erlebnisereignisse zu generieren, z. B. einen Kauf.
* Wie bei jeder anderen Aktion können Sie einen alternativen Pfad für den Fall eines Fehlers oder einer Zeitüberschreitung definieren und Sie können nicht zwei Aktionen parallel platzieren.
* Die an Platform gesendete Aktualisierungsanfrage erfolgt schnell, jedoch nicht sofort/innerhalb einer Sekunde. Es dauert normalerweise ein paar Sekunden, manchmal aber auch mehr, ohne dass dies garantiert werden kann. Wenn eine Aktion beispielsweise „Feld 1“ verwendet, das durch eine davor positionierte Profilaktualisierungsaktion aktualisiert wurde, sollte nicht davon ausgegangen werden, dass „Feld 1“ durch die Aktion aktualisiert wird.
* Datenquellen verfügen auf Feldergruppenebene über eine Einstellungsmöglichkeit für die Aufbewahrungsfrist im Cache. Soll in einer Journey ein kürzlich aktualisiertes Profilfeld genutzt werden, sollte eine sehr kurze Aufbewahrungsfrist im Cache definiert werden.

## Verwenden des Testmodus {#using-the-test-mode}

Im Testmodus wird die Aktualisierung des Profils nicht simuliert. Die Aktualisierung wird für das Testprofil durchgeführt.

Nur Profil können im Testmodus in eine Journey wechseln. Sie können entweder ein neues Profil erstellen oder ein vorhandenes Profil in ein Test-Profil umwandeln. In Adobe Experience Platform können Sie die Attribute von Profilen über API-Aufrufe aktualisieren, jedoch nicht über die Oberfläche. Am einfachsten ist dies mit der Action-Aktivität **Profil aktualisieren** und dem booleschen Testfeld des Profils von &quot;false&quot;in &quot;true&quot;.

Weitere Informationen zum Testmodus finden Sie in diesem [Abschnitt](../building-journeys/testing-the-journey.md).

## Verwenden des Profil-Updates

1. Entwerfen Sie Ihre Journey, indem Sie mit einem Ereignis beginnen. Siehe diesen [Abschnitt](../building-journeys/journey.md).

1. Legen Sie im Abschnitt **Aktion** der Palette die Aktivität **Profil aktualisieren** auf der Arbeitsfläche ab.

   ![](../assets/profileupdate0.png)

1. Wählen Sie ein Schema aus der Liste aus.

1. Klicken Sie auf **Felder**, um das Feld auszuwählen, das Sie aktualisieren möchten. Es kann nur ein Feld ausgewählt werden.

   ![](../assets/profileupdate2.png)

1. Wählen Sie einen Datensatz aus der Liste aus. Die Auswahl des Datensatzes bestimmt, wo der neue Wert des Profilfelds gespeichert wird.

1. Klicken Sie auf das Feld **Wert**, um den gewünschten Wert zu definieren:

   * Mit dem einfachen Ausdruckseditor können Sie ein Feld aus einer Datenquelle oder aus dem eingehenden Ereignis auswählen.

      ![](../assets/profileupdate4.png)

   * Wenn Sie einen bestimmten Wert definieren oder erweiterte Funktionen nutzen möchten, klicken Sie auf **Erweiterter Modus**.

      ![](../assets/profileupdate3.png)

Die Aktivität **Profil aktualisieren** ist jetzt konfiguriert.

![](../assets/profileupdate1.png)
