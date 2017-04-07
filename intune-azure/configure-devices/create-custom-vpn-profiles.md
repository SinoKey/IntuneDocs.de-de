---
title: Erstellen von benutzerdefinierten VPN-Profilen mit Microsoft Intune
titleSuffix: Intune Azure preview
description: Verwenden Sie benutzerdefinierte Konfigurationen, um VPN-Profile in Intune zu erstellen.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 990f3ff6528b537d1ea62c82440f1e46bcde8c95
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Erstellen von benutzerdefinierten VPN-Profilen in Microsoft Intune

## <a name="create-a-custom-configuration"></a>Erstellen einer benutzerdefinierten Konfiguration
Sie können benutzerdefinierte Intune-Konfigurationsrichtlinien verwenden, um VPN-Profile für folgende Geräte zu erstellen:

* Geräte unter Android 4 und höher
* Registrierte Geräte unter Windows 8.1 und höher
* Geräte unter Windows Phone 8.1 und höher
* Registrierte Geräte unter Windows 10 Desktop 
* Geräte unter Windows 10 Mobile

Dieser Richtlinientyp kann hilfreich sein, wenn die standardmäßigen Intune-VPN-Richtlinien nicht die Einstellungen enthalten, die Sie verwenden möchten.

## <a name="to-create-a-custom-configuration-policy"></a>So erstellen Sie eine benutzerdefinierte Konfigurationsrichtlinie:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
5. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
6. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das VPN-Profil ein.
7. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie VPN-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:
    - **Android**
    - **iOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)
    - **macOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)
    - **Windows Phone 8.1**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.
7. Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** für jede URI-Einstellung, die Sie angeben möchten, **Hinzufügen** aus, geben Sie die geforderten Informationen ein, und wählen Sie dann **OK** aus. Beispiel:

   ![Dialogfeld „Benutzerdefinierte VPN-Profilkonfiguration“](./media/Intune_Add_VPN_URI.png)

4.  Nachdem Sie alle erforderlichen URI-Einstellungen eingegeben haben, wählen Sie **OK** und dann auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.

## <a name="example-uri-settings"></a>Beispiel für URI-Einstellungen

Diese Einstellungen können verwendet werden, um eine benutzerdefinierte Konfiguration für ein VPN in einem fiktiven Unternehmen namens Contoso zu erstellen.
Details zu allen verfügbaren Einstellungen finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Natives Contoso-VPN (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Informationen zur Verwendung dieser Einstellungen und weitere Details zu ihrer Funktion finden Sie in der CSP-Dokumentation (Configuration Service Provider; Kryptografiedienstanbieter): https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>URI-Einstellungen für Android pro App VPN auf PulseSecure
### <a name="custom-uri-for-package-list"></a>BENUTZERDEFINIERTE URI FÜR DIE PAKETLISTE
-  Datentyp = String
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Wert = durch Trennzeichen getrennte Paketliste.
   - Trennzeichen: Semikolon (;), Doppelpunkt (:), Komma (,), senkrechter Strich (|)

Beispiele:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>BENUTZERDEFINIERTE URI FÜR MODUS (OPTIONAL)
- Datentyp = String
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Hinweise
> - Verwenden Sie den gleichen *Namen*, dem Sie dem benutzerdefinierten Profil zugewiesen haben.
> - Mögliche Werte: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Der Standardlist ist *GLOBAL*, wenn keine PackageList angegeben ist (Abwärtskompatibilität mit systemweiten Profilen)
> - Standardmäßig *WHITELIST*, wenn eine PackageList angegeben ist




