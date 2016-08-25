---
title: "Benutzerdefinierte Konfigurationen für VPN-Profile | Microsoft Intune"
description: Verwenden Sie benutzerdefinierte Konfigurationen, um VPN-Profile in Intune zu erstellen.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 374a56612b5c2a4dfd65d920307d5a4deb709b9b
ms.openlocfilehash: e96daf7f10db82adf0f4f92412128fabbe652d51


---

# Benutzerdefinierte Konfigurationen für VPN-Profile

## Erstellen einer benutzerdefinierten Konfiguration
Sie können benutzerdefinierte Konfigurationen verwenden, um VPN-Profile in Intune zu erstellen. So erstellen Sie eine benutzerdefinierte Konfiguration:

   1. Wählen Sie in der Intune-Verwaltungskonsole **Richtlinie** > **Richtlinie hinzufügen** > *<Expand platform>* > **Benutzerdefinierte Konfiguration** > **Richtlinie erstellen** aus.
   2. Geben Sie einen Namen für die Richtlinie an.
   3. Wählen Sie für jede URI-Einstellung **Hinzufügen** aus, und geben Sie die erforderlichen Informationen an. Beispiel:

   ![Dialogfeld „Benutzerdefinierte VPN-Profilkonfiguration“](./media/Intune_Add_VPN_URI.png)

   4.  Nachdem Sie alle URI-Einstellungen eingegeben haben, wählen Sie **Richtlinie speichern** aus, und stellen Sie die Richtlinie anschließend bereit.

## Bereitstellen einer Konfigurationsrichtlinie

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie anschließend auf **Bereitstellung verwalten**.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie anschließend auf **Hinzufügen** &gt; **OK**.

    -   **So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Klicken Sie auf **Abbrechen**.

Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.

##Beispiel für URI-Einstellungen für eine benutzerdefinierte VPN-Profilkonfiguration
Hier folgen Beispieleinträge für URI-Werte zum Erstellen einer benutzerdefinierten Konfiguration für ein VPN in einem fiktiven Unternehmen namens Contoso. Weitere Informationen, wie den Datentyp für die einzelnen Einträge, finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

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

## URI-Einstellungen für Android pro App VPN auf PulseSecure
### BENUTZERDEFINIERTE URI FÜR DIE PAKETLISTE
-  Datentyp = String
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList
-  Wert = durch Trennzeichen getrennte Paketliste.
   - Trennzeichen: Semikolon (;), Doppelpunkt (:), Komma (,), senkrechter Strich (|)

Beispiele:
- com.android.chrome
- com.android.chrome;com.android.browser

### BENUTZERDEFINIERTE URI FÜR MODUS (OPTIONAL)
- Datentyp = String
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Hinweise
> - Verwenden Sie den gleichen *Namen*, dem Sie dem benutzerdefinierten Profil zugewiesen haben.
> - Mögliche Werte: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Der Standardlist ist *GLOBAL*, wenn keine PackageList angegeben ist (Abwärtskompatibilität mit systemweiten Profilen)
> - Standardmäßig *WHITELIST*, wenn eine PackageList angegeben ist


### Weitere Informationen:
(VPN-Verbindungen in Microsoft Intune)[vpn-connections-in-microsoft-intune.md]



<!--HONumber=Aug16_HO3-->


