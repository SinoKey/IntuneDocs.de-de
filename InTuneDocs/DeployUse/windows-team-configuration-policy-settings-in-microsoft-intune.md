---
# required metadata

title: Einstellungen für Windows Team-Konfigurationsrichtlinien in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einstellungen für Windows Team-Konfigurationsrichtlinie in Microsoft Intune
Verwenden Sie die **allgemeine Windows 10 Team-Konfigurationsrichtlinie** von Microsoft Intune, um Einstellungen für registrierte Windows 10 Team-Geräte (z. B. Microsoft Surface Hub) zu konfigurieren.

|Name der Einstellung|Details|
|----------------|-----------|
|**Wenn sich jemand im Raum automatisch zu reaktivieren Bildschirms zulassen**|Ermöglicht das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.|
|**PIN für funkprojektion anfordern**|Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.|
|**Einrichten eines Wartungsfensters für Geräteupdates**|Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können. Sie können die Startzeit und Länge des Fensters (1 bis 5 Stunden) konfigurieren.|
|**Aktivieren von Azure Operational Insights**|Azure Operational Insights ist Teil der Microsoft Operations Manager-Suite und sammelt, speichert und analysiert Protokolldaten von Windows 10-Teamgeräten.<br /><br />Sie müssen eine **Arbeitsbereichs-ID** und einen **Arbeitsbereichsschlüssel** angeben, um die Verbindung mit Azure Operational Insights herstellen zu können..|
|**Aktivieren der drahtlosen Miracast-Projektion**|Aktivieren Sie diese Option, wenn Sie es dem Windows 10-Teamgerät ermöglichen möchten, für Miracast aktivierte Geräte zum Projizieren zu verwenden.<br /><br />Wenn Sie diese Option aktivieren, wählen Sie unter **Miracast-Kanal auswählen** den Miracast-Kanal aus, der zum Projizieren von Inhalten verwendet wurde.|
|**Auswählen der auf der Begrüßungsseite angezeigten Besprechungsinformationen**|Wenn Sie diese Option aktivieren, können Sie die Informationen auswählen, die auf der Kachel **Besprechungen** des Bildschirms **Willkommen** angezeigt werden. Sie können:<br /><br />-   **Nur Organisator und Zeit anzeigen**<br />-   **Organisator, Zeit und Betreff anzeigen (Betreff wird für private Besprechungen ausgeblendet)**|
|**URL für Hintergrundbild des Sperrbildschirms**|Aktivieren Sie diese Einstellung, um auf dem Bildschirm **Willkommen** für Windows 10-Teamgeräte einen benutzerdefinierten Hintergrund über die von Ihnen angegebene URL anzuzeigen.<br /><br />Das Bild muss im PNG-Format vorliegen, und die URL muss mit **https://** beginnen..|


### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


