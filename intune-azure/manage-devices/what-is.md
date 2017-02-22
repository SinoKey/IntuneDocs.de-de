---
title: "Verwalten von Geräten mit Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und mit diesen verschiedene Aktionen durchführen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 040c4e18d87110ab7380a64540d08127574a7c46
ms.openlocfilehash: 5a967cc1be387f83f95591186f786db61d3debcd


---

# <a name="what-is-device-management"></a>Was ist die Geräteverwaltung? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Die Workload **Geräte und Gruppen** bietet Ihnen einen Einblick in die von Ihnen verwalteten Geräte. Außerdem können Sie damit Remotetasks auf diesen Geräten ausführen. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte & Gruppen** aus.

    ![Workload „Geräte & Gruppen“](./media/devices-and-groups-workload.png)

Wählen Sie eine der folgenden Optionen aus:

- **Übersicht:** Erhalten Sie Informationen zu Geräten, die Sie registriert haben, und zu den Betriebssystemen der einzelnen Geräte.
- **Verwalten:** Wählen Sie **Alle Geräte** aus, um eine Liste aller von Ihnen verwalteten Geräte anzuzeigen.
    Wählen Sie eines dieser Geräte in der Liste aus, um das Blatt **Übersicht über** <*Gerätename*>  zu öffnen, auf dem Sie eine der folgenden Optionen auswählen können:
    - **Übersicht:** Hier finden Sie allgemeine Informationen über das Gerät, einschließlich Informationen über den Namen, den Besitzer, ob es ein BYOD-Gerät ist, wann es zuletzt eingecheckt wurde u.v.m. Darüber hinaus können Sie die folgenden Remoteaktionen auf dem Gerät ausführen (nicht alle Aktionen werden von allen Plattformen unterstützt):
        - **Unternehmensdaten entfernen:** Entfernt nur Unternehmensdaten, die von Intune verwaltet werden. Es werden keine persönlichen Daten vom Gerät entfernt. Das Gerät wird nicht mehr von Intune verwaltet und kann damit nicht mehr auf Unternehmensressourcen zugreifen (nicht unterstützt für Windows-Geräte, die mit Azure Active Directory verbunden sind).
        - **Zurücksetzung auf Werkseinstellungen:** Setzt das Gerät auf die Standardeinstellungen zurück. Das Gerät wird nicht mehr von Intune verwaltet, und sowohl die Unternehmens- als auch persönliche Daten werden entfernt. Diese Aktion kann nicht rückgängig gemacht werden.
        - **Remotesperre:** Sperrt das Gerät. Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden. Sie können nur Remotesperrungen von Geräten durchführen, für die eine PIN oder ein Kennwort festgelegt wurde.
        - **Kennung zurücksetzen:** Generiert eine neue Kennung für das Gerät, die auf dem Blatt **Übersicht über** <*Gerätename*>  angezeigt wird.
        - **Aktivierungssperre umgehen:** Damit entfernen Sie ohne Apple-ID und Kennwort des Benutzers die Aktivierungssperre auf einem iOS-Gerät. Nachdem Sie die Aktivierungssperre umgangen haben, aktiviert das Gerät die Aktivierungssperre erneut, wenn die App „Mein iPhone suchen“ gestartet wird. Umgehen Sie die Aktivierungssperre nur, wenn Sie physischen Zugriff auf das Gerät haben.
        - **Modus für verlorene Geräte:** Wenn ein Gerät gestohlen wurde, können Sie den Modus für verlorene Geräte aktivieren. Dies ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden.
        - **Neu starten:** Führt einen Neustart des Geräts durch. Der Eigentümer des Geräts wird nicht automatisch über den Neustart benachrichtigt und kann daher Daten verlieren.
        ![Übersicht über das Gerät](http://i.imgur.com/4Rx4VXm.png)
        
    - **Hardware:** Hier finden Sie ausführliche Informationen über das Gerät, einschließlich des freien Speicherplatzes, des Modells und Herstellers usw.
    ![Hardwareinventur für verwaltete Geräte](./media/hardware-inventory.png)
    - **Erkannte Anwendungen:** Zeigt eine Liste aller auf dem Gerät installierten Apps an, die von Intune gefunden wurden.
    ![Knoten „Erkannte Anwendungen“](./media/detected-applications.png)
- **Monitor:** Wählen Sie **Geräteaktionen** aus, um eine Liste der Geräteaktionen, die auf Geräten, die Sie verwalten, ausgeführt wurden, und den aktuellen Status dieser Aktionen anzuzeigen.
![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)



<!--HONumber=Feb17_HO1-->


