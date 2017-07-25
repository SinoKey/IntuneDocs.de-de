---
title: "Anzeigen des Intune-Gerätebestands"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie die von Ihnen über Intune verwalteten Geräte sowie Informationen zu der entsprechenden Hardware und den installierten Apps anzeigen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3618c5ee0b4a7ff0e7b6a4d6ed58f77a2af0ba66
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-view-intune-device-inventory"></a>So zeigen Sie den Intune-Gerätebestand an


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Workload **Geräte** bietet Einblicke in die von Ihnen verwalteten Geräte, einschließlich Informationen zu Hardwarefunktionen und den auf den Geräten installierten Apps. 

So zeigen Sie den Gerätebestand an:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.

Wählen Sie nun eine der folgenden Optionen aus:

- **Übersicht:** Erhalten Sie Informationen zu Geräten, die Sie registriert haben, und zu den Betriebssystemen der einzelnen Geräte.
- **Verwalten:** Wählen Sie **Alle Geräte** aus, um eine Liste aller von Ihnen verwalteten Geräte anzuzeigen.
    Wählen Sie eines dieser Geräte in der Liste aus, um das Blatt **Übersicht über** <*Gerätename*>  zu öffnen, auf dem Sie eine der folgenden Optionen auswählen können:
    - **Übersicht:** Hier finden Sie allgemeine Informationen über das Gerät, einschließlich den Namen, den Besitzer, ob es ein BYOD-Gerät ist, wann es zuletzt eingecheckt wurde u.v.m.
    ![Übersicht über das Gerät](./media/device-overview.png)
    - **Hardware:** Hier finden Sie ausführliche Informationen über das Gerät, einschließlich dessen freien Speicherplatzes, des Modells und Herstellers usw.
    ![Hardwareinventur für verwaltete Geräte](./media/hardware-inventory.png)
    - **Ermittelte Apps:** Zeigt eine Liste aller auf dem Gerät installierten Apps an, die von Intune gefunden wurden.
    ![Knoten „Ermittelte Apps“](./media/detected-applications.png)
    


    - **Gerätekompatibilität:** Zeigt den Kompatibilitätszustand aller Kompatibilitätsrichtlinien an, die dem Gerät zugewiesen wurden.
    - **Gerätekonfiguration:** Zeigt den Kompatibilitätszustand aller Konfigurationsrichtlinien an, die dem Gerät zugewiesen wurden.
- **Monitor:** Wählen Sie **Geräteaktionen** aus, um eine Liste der Geräteaktionen, die auf Geräten, die Sie verwalten, ausgeführt wurden, und deren aktuellen Status anzuzeigen.
- **Setup** > **TeamViewer-Connector:** Ermöglicht Ihnen die Konfiguration der Remoteverwaltung auf Geräten mithilfe der Software TeamViewer. Weitere Informationen finden Sie unter [Bereitstellen von Remoteunterstützung für mit Intune verwaltete Android-Geräte](/intune/device-profile-android-teamviewer).

>[!NOTE]
> Intune sammelt nur auf unternehmenseigenen Geräten App-Inventar. Apps sind auf persönlichen Geräten nicht inventarisiert. Für Windows 10 PCs wird nur Inventar von modernen Apps auf unternehmenseigenen Geräten gesammelt. Intune sammelt keine Informationen über Win32-Apps auf dem Gerät.
