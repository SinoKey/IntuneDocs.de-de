---
title: Was ist App-Verwaltung? | Microsoft-Dokumentation
titleSuffix: Intune Azure preview
description: 'Intune in Azure (Vorschau): In diesem Thema lernen Sie die Grundlagen der App-Verwaltung mit Microsoft Intune kennen.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 34970d6adcfe41a6de9636a5605a17f9f5ef2d82
ms.contentlocale: de-de
ms.lasthandoff: 05/05/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>Was ist die Microsoft Intune App-Verwaltung?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Als IT-Administrator sind Sie wahrscheinlich beauftragt, sicherzustellen, dass die Endbenutzer Zugriff auf die Apps haben, die sie für ihre Arbeit benötigen. Dies kann aus verschiedenen Gründen eine große Herausforderung darstellen:
- Es gibt eine Vielzahl von Geräteplattformen und App-Typen.
- Sie müssen möglicherweise Apps auf unternehmenseigenen Geräten und auch auf Geräten von Benutzern verwalten.
- Bei all dem müssen Sie außerdem sicherstellen, dass Ihr Netzwerk und Ihrer Daten geschützt bleiben. 

Darüber hinaus müssen Sie ggf. auch Apps auf Geräten, die nicht in Intune registriert sind, zuweisen und verwalten.

Intune bietet eine Reihe von Funktionen, die Ihnen dabei helfen, die benötigten Apps auf allen erforderlichen Geräten bereitzustellen.

## <a name="app-management-capabilities-by-platform"></a>App-Verwaltungsfunktionen nach Plattform

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Hinzufügen und Zuweisen von Apps für Geräte und Benutzer|Ja|Ja|Ja|Ja|
|Zuweisen von Apps für Geräte, die nicht bei Intune registriert sind|Ja|Ja|Nein|Nein|
|Steuern des Startverhaltens von Apps mithilfe von App-Konfigurationsrichtlinien|Nein|Ja|Nein|Nein|
|Verwenden von Richtlinien für die Bereitstellung mobiler Apps zum Verlängern abgelaufener Apps|Nein|Ja|Nein|Nein|
|Schützen von Unternehmensdaten in Apps mit App-Schutzrichtlinien|Ja|Ja|Nein|Nein<sup>1</sup>|
|Entfernen ausschließlich von Unternehmensdaten aus einer installierten App (Selektive App-Zurücksetzung)|Ja|Ja|Ja|Ja|
|Überwachen von App-Zuweisungen|Ja|Ja|Ja|Ja|
|Zuweisen und Nachverfolgen von Per Volumenlizenz in einem App-Store erworbenen Apps|Nein|Nein|Nein|Ja|
|Verpflichtende Installation von Apps auf Geräten (erforderlich)<sup>2</sup>|Ja|Ja|Ja|Ja|
|Optionale Installation auf Geräten über das Unternehmensportal (verfügbare Installation)|Ja|Ja|Ja|Ja|
|Installieren von Verknüpfungen zu Apps im Internet (Webclip)|Ja|Ja|Ja|Ja|
|Interne (branchenspezifische) Apps|Ja|Ja|Nein|Nein|
|Apps aus einem Store|Ja|Ja|Ja|Ja|
|Aktualisierung von Apps|Ja|Ja|Ja|Ja|

<sup>1</sup> Erwägen Sie die Verwendung [Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection) für den Schutz von Apps auf Geräten mit Windows 10.

<sup>2</sup> Gilt nur für Geräte, die von Intune verwaltet werden.


## <a name="how-to-get-started"></a>Erste Schritte

Sie finden die meisten Informationen zu Apps im Workload **Mobile Apps**, auf die Sie wie folgt zugreifen können:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.

    ![Workload „Mobile Apps“](./media/apps-workload.png)

### <a name="manage"></a>Verwalten von
- **Apps:** Hier können Sie die meisten Apps hinzufügen, zuweisen und überwachen. 
    - [Hinzufügen von Apps](add-apps.md)
    - [Zuweisen von Apps](deploy-apps.md)
    - [Überwachen von Apps](monitor-apps.md)
- **App-Konfigurationsrichtlinien:** Verwenden Sie App-Konfigurationsrichtlinien, um Einstellungen anzugeben, die beim Ausführen einer App durch den Benutzer erforderlich sein können. Details hierzu finden Sie in den folgenden Abschnitten:
    - [App-Konfigurationsrichtlinien](app-configuration-policies.md)
- **App-Schutzrichtlinien:** Ermöglichen Ihnen das Zuordnen von Einstellungen für eine App zum Schutz der Unternehmensdaten, die diese verwendet. Sie können z.B. die Funktionen einer App zur Kommunikation mit anderen Apps einschränken oder erzwingen, dass der Benutzer eine PIN eingeben muss, um auf eine Unternehmens-App zuzugreifen.
    - [App-Schutzrichtlinien](app-protection-policies.md)
- **Selektive App-Zurücksetzung:** Entfernt nur Unternehmensdaten von einem Benutzergerät, das Sie auswählen.
    - [Selektive App-Zurücksetzung](app-selective-wipe.md)
- **iOS-Bereitstellungsprofil:**: iOS-Apps enthalten ein Bereitstellungsprofil und Code, der von einem Zertifikat signiert ist. Wenn das Zertifikat abläuft, kann die App nicht mehr ausgeführt werden. Intune stellt Ihnen die Tools zum proaktiven Zuweisen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.
    - [iOS-App-Bereitstellungsprofile](ios-app-provisioning-profile.md)

### <a name="monitor"></a>Überwachen
- **Lizenzierte Apps:** Ermöglicht das Anzeigen, Zuweisen und Überwachen von per Volumenlizenz in den App Stores erworbenen Apps.
    - [Per Volumenlizenz erworbene Apps aus dem Windows Store für Unternehmen](wsfb-apps.md)
- **Erkannte Apps:** Zeigt alle Apps, die von Intune zugewiesen und auf einem Gerät installiert wurden.
- **App-Installationsstatus:** Zeigt den Status einer App-Zuweisung, die Sie erstellt haben.
- **App-Schutzstatus:** Zeigt den Status einer App-Schutzrichtlinie für einen ausgewählten Benutzer an.

Weitere Informationen finden Sie unter [Überwachen von Apps](monitor-apps.md).

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **Windows Store für Unternehmen:** Richten Sie die Integration in den Windows Store für Unternehmen ein. Anschließend können Sie erworbene Anwendungen mit Intune synchronisieren, zuweisen und Ihre Lizenznutzung verfolgen. 
    - [Per Volumenlizenz erworbene Apps aus dem Windows Store für Unternehmen](wsfb-apps.md)
- **Unternehmensportalbranding:** Passen Sie das Unternehmensportal mit Ihrem Unternehmensbranding an. 
    - [Konfiguration des Unternehmensportals](company-portal-app.md)

