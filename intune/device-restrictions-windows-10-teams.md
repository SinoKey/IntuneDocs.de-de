---
title: "Intune-Geräteeinschränkungen für Windows 10 Team"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie etwas über die verfügbaren Geräteeinschränkungen für Windows 10 Team-Geräte."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e7e6e5093b09d7a221083cd36a8d3e5ecbbb8c2
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für Windows 10 Team in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- **Bildschirm aktivieren, wenn eine Person im Raum ist:** Erlaubt das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.
- **PIN für Funkprojektion:** Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.
- **Miracast-Funkprojektion:** Aktivieren Sie diese Option, wenn Sie auf dem Gerät mit Windows 10-Team erlauben möchten, für Miracast aktivierte Geräte zum Projizieren zu verwenden.
- **Anzeige von Besprechungsinformationen auf dem Willkommensbildschirm:** Aktivieren Sie diese Option, um die Informationen auszuwählen, die auf der Kachel „Besprechungen“ auf dem Willkommensbildschirm angezeigt werden. Sie können:
    - **Nur Organisator und Zeit anzeigen**
    - **Organisator, Zeit und Thema anzeigen (Thema bei privaten Besprechungen ausblenden)**
- **URL für Hintergrundbild des Willkommensbildschirms:** Aktivieren Sie diese Einstellung, um auf dem **Willkommensbildschirm** von Windows 10 Team-Geräten einen benutzerdefinierten Hintergrund aus der angegebenen URL anzuzeigen.<br>Das Bild muss im PNG-Format vorliegen und die URL muss mit **https://** beginnen.
- **Wartungsfenster für Updates:** Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können. Sie können die Startzeit und Länge des Fensters (1 bis 5 Stunden) konfigurieren.
- **Azure Operational Insights:** Azure Operational Insights ist Teil der Microsoft Operations Manager-Suite und sammelt, speichert und analysiert Protokolldateidaten von Windows 10-Team-Geräten.<br>Sie müssen eine **Arbeitsbereichs-ID** und einen **Arbeitsbereichsschlüssel** angeben, um die Verbindung mit Azure Operational Insights herstellen zu können.

## <a name="next-steps"></a>Nächste Schritte

Verwenden Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen](device-restrictions-configure.md), um das Profil zu speichern und es Benutzern und Geräten zuzuweisen.
