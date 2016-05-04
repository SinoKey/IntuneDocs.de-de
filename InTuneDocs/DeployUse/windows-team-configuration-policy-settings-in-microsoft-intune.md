---
title: Einstellungen für Windows Team-Konfigurationsrichtlinie in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
author: robstackmsft
---
# Einstellungen für Windows Team-Konfigurationsrichtlinie in Microsoft Intune
Verwenden Sie die Microsoft Intune **Windows 10 Team-Konfigurationsrichtlinie** für registrierte Windows 10 Team-Geräte wie z. B. dem Microsoft Surface Hub konfigurieren.

## Geräteeinstellungen

|Name der Einstellung|Details|
|----------------|-----------|
|**Wenn sich jemand im Raum automatisch zu reaktivieren Bildschirms zulassen**|Ermöglicht das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.|
|**PIN für funkprojektion anfordern**|Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.|
|**Legen Sie ein Wartungsfenster für Updates für das Gerät**|Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können. Sie können die Startzeit und Länge des Fensters (1 bis 5 Stunden) konfigurieren.|
|**Aktivieren von Azure Operational Insights**|Azure Operational Insights Teil der Microsoft Operations Manager-Suite sammelt, speichert und analysiert Daten für die Protokolldateien von Windows 10 Team-Geräten.<br /><br />Um mit Azure Operational Insights verbinden, geben Sie einen **Arbeitsbereichs-ID** und ein **Arbeitsbereichsschlüssel**.|
|**Aktivieren von Miracast-wireless-Projektion**|Aktivieren Sie diese Option, wenn Sie die Windows 10 Team-Gerät aktiviert Miracast-Geräte verwenden, um das Projekt lassen möchten.<br /><br />Wenn Sie diese Option aktivieren und von **Wählen Miracast-Kanal** Wählen Sie den Miracast-Kanal verwendet, um den Projektinhalt.|
|**Wählen Sie die Besprechungsinformationen auf der Willkommensseite angezeigt**|Wenn Sie diese Option aktivieren, können Sie die Informationen, die auf angezeigt wird, die **Besprechungen** der Kachel den **Willkommen** Bildschirm. Sie können:<br /><br />-   **-Planer und nur anzeigen**<br />-   **Anzeigen, organisieren, Zeit und Betreff (Subject für private Konferenzen ausgeblendet)**|
|**Lockscreen Hintergrund-Bild-URL**|Aktivieren Sie diese Einstellung auf einen benutzerdefinierten Hintergrund Anzeigen der **Willkommen** Bildschirm für Windows 10 Team-Geräte auf die URL an.<br /><br />Das Bild muss im PNG-Format vorliegen und die URL muss mit beginnen **https://**.|


### Siehe auch
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Mar16_HO4-->


