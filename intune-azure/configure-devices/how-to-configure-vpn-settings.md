---
title: So konfigurieren Sie Intune-VPN-Einstellungen
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune VPN-Einstellungen auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 2d93edb688dbf296137a133f0b7ae065fc1cc89d
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Konfigurieren von VPN-Einstellungen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Virtuelle private Netzwerke (virtual private networks, VPNs) bieten Ihren Benutzern sicheren Remotezugriff auf Ihr Unternehmensnetzwerk. Geräte verwenden ein VPN-Verbindungsprofil, um eine Verbindung mit dem VPN-Server zu initiieren. **VPN-Profile** in Microsoft Intune ermöglichen Ihnen die Bereitstellung von VPN-Einstellungen für Benutzer und Geräte in Ihrer Organisation, damit diese leicht eine sichere Verbindung zum Netzwerk herstellen können.

Nehmen Sie z. B. an, Sie möchten allen iOS-Geräten die Einstellungen zur Verfügung stellen, die zum Verbinden mit einer Dateifreigabe im Unternehmensnetzwerk erforderlich sind. Sie erstellen ein VPN-Profil mit den Einstellungen, die zum Herstellen einer Verbindung mit dem Unternehmensnetzwerk erforderlich sind, und weisen dieses Profil dann allen Benutzern mit iOS-Geräten zu. Die Benutzer sehen die VPN-Verbindung in der Liste der verfügbaren Netzwerke und können mit geringem Aufwand eine Verbindung herstellen.

## <a name="vpn-connection-types"></a>VPN-Verbindungstypen

Sie können VPN-Profile mit den folgenden Verbindungstypen erstellen:

||||||||
|-|-|-|-|-|-|-|
|Verbindungstyp|Android|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|Pulse Secure|Ja|Ja|Ja|Ja|Ja|Ja|
|Cisco (IPsec)|Nein|Ja|Nein|Nein|Nein|Nein|
|Citrix|Ja|Ja|Nein|Nein|Nein|Nein|
|F5 Edge Client|Ja|Ja|Ja|Ja|Ja|Ja|
|Dell SonicWALL Mobile Connect|Ja|Ja|Ja|Ja|Ja|Ja|
|Check Point Capsule VPN|Ja|Ja|Ja|Ja|Ja|Ja|
|Cisco AnyConnect|Ja|Ja|Ja|Nein|Nein|Nein|
|Automatisch|Nein|Nein|Nein|Nein|Nein|Ja|
|IKEv2|Nein|Nein|Nein|Nein|Nein|Ja|
|L2TP|Nein|Nein|Nein|Nein|Nein|Ja|
|PPTP|Nein|Nein|Nein|Nein|Nein|Ja|
|Benutzerdefiniert|Nein|Ja|Ja|Nein|Nein|Nein|


> [!IMPORTANT]
> Vor der Verwendung von VPN-Profilen, die auf einem Gerät bereitgestellt werden, müssen Sie die entsprechende VPN-App für das Profil installieren. Die Informationen im Thema [Was ist die App-Verwaltung in Microsoft Intune?](/intune-azure/manage-apps/what-is-app-management) unterstützen Sie beim Bereitstellen der App mit Intune.  

Informationen zum Erstellen benutzerdefinierter VPN-Profile mithilfe von URI-Einstellungen finden Sie unter [Erstellen benutzerdefinierter VPN-Profile](create-custom-vpn-profiles.md).     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Erstellen eines Geräteprofils mit VPN-Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das VPN-Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie VPN-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die VPN-Geräteeinstellungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **VPN** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](vpn-for-android.md)
    - [Einstellungen für iOS](vpn-for-ios.md)
    - [Einstellungen für macOS](vpn-for-macos.md)
    - [Einstellungen für Windows Phone 8.1](vpn-for-windows-phone-8-1.md)
    - [Einstellungen für Windows 8.1](vpn-for-windows-8-1.md)
    - [Einstellungen für Windows 10](vpn-for-windows-10.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.


## <a name="methods-of-securing-vpn-profiles"></a>Methoden zum Schützen von VPN-Profilen

VPN-Profile können eine Reihe verschiedener Verbindungstypen und Protokolle von unterschiedlichen Herstellern verwenden. Diese Verbindungen werden in der Regel mit einer von zwei Methoden gesichert.

### <a name="certificates"></a>Zertifikate

Beim Erstellen des VPN-Profils wählen Sie ein SCEP- oder PKCS-Zertifikatprofil aus, das Sie zuvor in Intune erstellt haben. Dies wird als Identitätszertifikat bezeichnet. Es dient zur Authentifizierung anhand eines von Ihnen erstellten vertrauenswürdigen Zertifikatprofils (oder eines *Stammzertifikats*), mit dem überprüft wird, ob das Gerät des Benutzers eine Verbindung herstellen darf. Das vertrauenswürdige Zertifikat wird auf dem Computer bereitgestellt, der die VPN-Verbindung authentifiziert, in der Regel ist dies der VPN-Server.

Weitere Informationen zum Erstellen und Verwenden von Zertifikatprofilen in Intune finden Sie unter [Konfigurieren von Zertifikaten mit Microsoft Intune](how-to-configure-certificates.md).

### <a name="user-name-and-password"></a>Benutzername und Kennwort

Der Benutzer authentifiziert sich beim VPN-Server durch Angabe seines Benutzernamens und Kennworts.

