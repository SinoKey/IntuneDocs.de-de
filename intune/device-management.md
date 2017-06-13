---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Hier erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Aktionen ausführen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1fdb86184875d7082659d608b445b41b2ad9aa9e
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Was ist die Microsoft Intune Geräteverwaltung?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.

Wählen Sie eine der folgenden Optionen aus:

- **Übersicht:** Erhalten Sie Informationen zu Geräten, die Sie registriert haben, und zu den Betriebssystemen der einzelnen Geräte.
- **Verwalten:** Wählen Sie **Alle Geräte** aus, um eine Liste aller von Ihnen verwalteten Geräte anzuzeigen.
    Wählen Sie eines dieser Geräte in der Liste aus, um das Blatt **Übersicht über** <*Gerätename*>  zu öffnen, auf dem Sie eine der folgenden Optionen auswählen können:
    - **Übersicht:** Hier finden Sie allgemeine Informationen über das Gerät, einschließlich Informationen über den Namen, den Besitzer, ob es ein BYOD-Gerät ist, wann es zuletzt eingecheckt wurde u.v.m.

    - **Hardware:** Hier finden Sie ausführliche Informationen über das Gerät, einschließlich des freien Speicherplatzes, des Modells und Herstellers usw.
    ![Hardwareinventur für verwaltete Geräte](./media/hardware-inventory.png)
    - **Erkannte Anwendungen:** Zeigt eine Liste aller auf dem Gerät installierten Apps an, die von Intune gefunden wurden.
    ![Knoten „Erkannte Anwendungen“](./media/detected-applications.png)
- **Monitor:** Wählen Sie **Geräteaktionen** aus, um eine Liste der Geräteaktionen, die auf Geräten, die Sie verwalten, ausgeführt wurden, und den aktuellen Status dieser Aktionen anzuzeigen.
![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)
- **Hilfe und Support:** Zeigt Links zur Problembehandlung und die Supportdokumentation an.

## <a name="available-device-actions"></a>Verfügbare Geräteaktionen

Darüber hinaus können Sie die folgenden Remoteaktionen auf dem Gerät ausführen (nicht alle Aktionen werden von allen Plattformen unterstützt):

### <a name="remove-company-data"></a>**Unternehmensdaten entfernen**
Entfernt nur Unternehmensdaten, die von Intune verwaltet werden. Es werden keine persönlichen Daten vom Gerät entfernt. Das Gerät wird nicht mehr von Intune verwaltet und kann damit nicht mehr auf Unternehmensressourcen zugreifen (nicht unterstützt für Windows-Geräte, die mit Azure Active Directory verbunden sind).

### <a name="factory-reset"></a>**Zurücksetzen auf Werkseinstellungen**
Setzt das Gerät auf die Standardeinstellungen zurück. Das Gerät wird nicht mehr von Intune verwaltet, und sowohl die Unternehmens- als auch persönliche Daten werden entfernt. Diese Aktion kann nicht rückgängig gemacht werden.

### <a name="remote-lock"></a>**Remotesperre**
Sperrt das Gerät. Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden. Sie können nur Remotesperrungen von Geräten durchführen, für die eine PIN oder ein Kennwort festgelegt wurde.

### <a name="reset-passcode"></a>**Kennung zurücksetzen**
Generiert eine neue Kennung für das Gerät, die auf dem Blatt **Übersicht über** <*Gerätename*>  angezeigt wird.

### <a name="bypass-activation-lock"></a>**Aktivierungssperre umgehen**
Entfernt der Aktivierungssperre auf einem iOS-Gerät ohne Apple-ID und Kennwort des Benutzers. Nachdem Sie die Aktivierungssperre umgangen haben, aktiviert das Gerät die Aktivierungssperre erneut, wenn die App „Mein iPhone suchen“ gestartet wird. Umgehen Sie die Aktivierungssperre nur, wenn Sie physischen Zugriff auf das Gerät haben.

### <a name="fresh-start"></a>**Sauberer Start**

Entfernt alle Apps, die auf einem Windows 10-PC mit Creators Update installiert wurden, und aktualisiert den PC dann auf die neueste Windows-Version.
Mit dieser Option können vorinstallierte OEM-Apps entfernt werden, die oft mit einem neuen PC geliefert werden. Sie können konfigurieren, ob Benutzerdaten beibehalten werden, wenn diese Geräteaktion ausgegeben wird. In diesem Fall werden alle Apps und Einstellungen entfernt, die Inhalte des Basisordners des Benutzers bleiben jedoch erhalten.


### <a name="lost-mode"></a>**Modus für verlorene Geräte**
Falls ein Gerät verloren geht oder gestohlen wird, können Sie den Modus für verlorene Geräte aktivieren. Dies ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden. Dazu gehen Sie folgendermaßen vor:
1.    Wählen Sie auf dem Blatt mit den Eigenschaften eines iOS-Geräts die Option **Mehr** > **Modus für verlorene Geräte** aus.
2.    Aktivieren Sie auf dem Blatt **Modus für verlorene Geräte** den Modus für verlorene Geräte, und geben Sie die anzuzeigende Nachricht sowie optional eine Kontakttelefonnummer ein.
3.    Klicken Sie auf **OK**.
Wenn Sie den Modus für verlorene Geräte aktivieren, kann das Gerät nicht mehr verwendet werden. Der Benutzer kann erst wieder auf das Gerät zugreifen, wenn Sie den Modus für verlorene Geräte wieder deaktivieren. Bei aktiviertem Modus für verlorene Geräte können Sie mithilfe der Aktion **Gerät suchen** ermitteln, wo sich das Gerät befindet.
Um den Modus für verlorene Geräte zu verwenden, muss es sich bei dem Gerät um ein firmeneigenes, über DEP registriertes iOS-Gerät im überwachten Modus handeln.

### <a name="locate-device"></a>**Gerät suchen**
Mithilfe dieser Remoteaktion können Sie den Standort eines verloren gegangenen oder gestohlenen iOS-Geräts auf einer Karte anzeigen. Bei dem Gerät muss es sich um ein firmeneigenes, über DEP registriertes iOS-Gerät im überwachten Modus handeln. Diese Aktion kann nur verwendet werden, wenn das Gerät zuvor in den Modus für verlorene Geräte versetzt wurde.
1.    Wählen Sie auf dem Blatt mit den Eigenschaften eines iOS-Geräts die Option **Mehr** > **Gerät suchen** aus.
2.    Wenn das Gerät gefunden wurde, wird seine Position auf dem Blatt **Gerät suchen** angezeigt.
    Blatt ![Gerät suchen](./media/locate-device.png)

>[!NOTE]
>Aus Datenschutzgründen können Sie nur begrenzt in die Karte hineinzoomen.

### <a name="restart"></a>**Neu starten**
Durchführen eines Neustart des Geräts Der Eigentümer des Geräts wird nicht automatisch über den Neustart benachrichtigt und kann daher Daten verlieren.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Sicherheit und Datenschutz im Zusammenhang mit dem Modus für verlorene Geräte und der Aktion „Gerät suchen“
- Vor der Aktivierung dieser Aktion werden keinerlei Informationen zum Standort des Geräts an Intune gesendet.
- Bei Verwendung der Aktion „Gerät suchen“ werden die Koordinaten des Geräts in Form von Breiten- und Längengrad an Intune gesendet und im Azure-Portal angezeigt.
- Die Daten werden 24 Stunden lang gespeichert und dann entfernt. Die Standortdaten können nicht manuell entfernt werden.
- Die Standortdaten werden sowohl im gespeicherten Zustand als auch bei der Übertragung verschlüsselt.
- Beim Konfigurieren des Modus für verlorene Geräte empfiehlt es sich, in der Nachricht für den Sperrbildschirm darauf hinzuweisen, dass der Standort des Geräts ermittelt werden kann.

