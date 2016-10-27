---
title: "Einstellungen für Windows 10-Richtlinien | Microsoft Intune"
description: "Verwenden Sie die in diesem Thema aufgeführten Richtlinieneinstellungen, um integrierte und benutzerdefinierte Einstellungen für registrierte Windows 10 Desktop- und Windows 10-Mobilgeräte zu konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# Intune-Richtlinieneinstellungen für Windows 10-Geräte in Microsoft Intune

Dieses Thema enthält Informationen zum Verständnis der Intune-Richtlinieneinstellungen, die Sie zum Verwalten von Windows 10-Geräten verwenden können. Lesen Sie dieses Thema zusammen mit den Verfahren in [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), um integrierte und benutzerdefinierte Einstellungen für registrierte Windows 10-Desktop- und Windows 10 Mobile-Geräte zu konfigurieren. Diese Richtlinien können nicht für PCs verwendet werden, auf denen die [Intune-PC-Clientsoftware](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune) ausgeführt wird.

Zwei Richtlinientypen stehen zur Verfügung:

- **Benutzerdefinierte Richtlinie** – Stellen Sie mithilfe der **benutzerdefinierten Richtlinie** von Microsoft Intune für Windows 10 und Windows 10 Mobile Einstellungen für OMA-URI (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Geräten zu steuern. Windows 10 stellt viele Einstellungen über die [Richtlinienkonfigurationsdienst-Anbieter (Policy Configuration Service Provider; Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) zur Verfügung.
- **Allgemeine Konfigurationsrichtlinie** – Verwenden Sie diesen Richtlinientyp, wenn Sie Einstellungen aus der integrierten Liste auswählen möchten, die in Microsoft Intune enthalten ist.

## Benutzerdefinierte Richtlinieneinstellungen

Geben Sie die folgenden Einstellungen in einer benutzerdefinierten Richtlinie an:

## &nbsp;&nbsp;&nbsp;Allgemein

Geben Sie einen Namen und optional eine Beschreibung für diese Richtlinie ein, damit Sie sie in der Intune-Konsole besser identifizieren können.

## &nbsp;&nbsp;&nbsp;OMA-URI-Einstellungen

Geben Sie für jede OMA-URI-Einstellung, die Sie hinzufügen möchten, die folgenden Informationen ein. Lesen Sie den Abschnitt [Windows 10-URI-Einstellungen](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) in diesem Thema, um weitere Informationen zu den Einstellungen zu erhalten, die Sie verwenden können: 

- **Einstellungsname** – Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.
- **Beschreibung der Einstellung** – Geben Sie optional eine Beschreibung für die Einstellung ein.
- **Datentyp** – Wählen Sie aus:
    - **Zeichenfolge**
    - **Zeichenfolge (XML)**
    - **Datum und Uhrzeit**
    - **Ganze Zahl**
    - **Gleitkomma**
    - **Boolesch**
- **OMA-URI (Groß-/Kleinschreibung beachten)** – Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.
- **Wert** – Geben Sie den Wert an, der mit der von Ihnen eingegebenen OMA-URI verknüpft werden soll.

### Beispiel
Im folgenden Screenshot ist die Einstellung **Connectivity/AllowVPNOverCellular** aktiviert. Dadurch kann ein Windows 10-Gerät eine VPN-Verbindung über ein Mobilfunknetz öffnen.

> ![Beispiel für eine benutzerdefinierte Richtlinie mit VPN-Einstellungen](./media/custom-policy-example.png)

## – Windows 10-URI-Einstellungen
Verwenden Sie diesen Abschnitt, um Informationen zu den OMA-URI-Einstellungen zu erhalten, die Sie mit einer **benutzerdefinierten Windows 10-Richtlinie** konfigurieren können.

## &nbsp;&nbsp;&nbsp;Richtlinie

|Name der Richtlinie und URI|Details|
|---------------|------------|-----------|
|**Automatische Aktualisierung zulassen**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|nur Desktop<br>**Datentyp:** Ganzzahl<br />**Werte:** **0** - **5** (Standard: **1**)|
|**Installationstag planen**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|nur Mobile<br>**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Täglich (Standard)<br>**1** – Sonntag<br>**2** – Montag<br>**3** – Dienstag<br>**4** – Mittwoch<br>**5** – Donnerstag<br>**6** – Freitag<br>**7** – Samstag|
|**Installationszeit planen**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** - **23** Uhr (**0** ist Mitternacht) (Standard: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Der Benutzer kann den Timer für die Kennwort-Toleranzperiode nicht festlegen. Der Wert wird auf „immer“ festgelegt.<br>**1** – Der Benutzer kann den Timer für den Kennwort-Verlängerungszeitraum festlegen (Standard).|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – **WLAN-Verbindung nicht zulassen**.<br>**1** – **WLAN-Verbindung zulassen** (Standard)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop und Mobile<br>**Datentyp:** Ganzzahl<br />**Werte:** **0** – Internetfreigabe nicht zulassen, **1** – Internetfreigabe zulassen (Standard)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – WLAN-Verbindung außerhalb von MDM-Bereitstellung nicht zulässig.<br>**1** – Hinzufügen von neuen Netzwerk-SSIDs über die bereits mit MDM bereitgestellten hinaus zulässig (Standard)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop und Mobile<br>**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Nicht zulässig (nur Enterprise-Einstellung)<br>**1** – Beschränkt<br>**2** – Vollständig (Standard)<br>**3** – Vollständig und Diagnoseinformationen|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Nicht zulässig<br>**1** – Nur Einstellungen (Standard)<br>**2** – Einstellungen und Experimente|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Anti-Diebstahl-Modus nicht zulassen<br>**1** – Benutzereinstellung (Standard)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – VPN über Mobiltelefon nicht zulässig<br>**1** – VPN kann beliebige Verbindung einschließlich Mobiltelefon verwenden (Standard).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Nicht zulassen, dass der Benutzer Bluetooth aktiviert.<br>**1** – Reserviert. Der Benutzer kann Bluetooth aktivieren und konfigurieren (wird in Windows Phone 8.1 für MDM, EAS, Windows 10 Desktop oder Windows 10 Mobile nicht unterstützt).<br>**2** – Zulässig. Der Benutzer kann Bluetooth aktivieren und konfigurieren (Standard).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – Kein Roaming zulassen **1** – Roaming zulassen (Standard)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0**, **1** (Standard)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0**, **1** (Standard)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** (Standard), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Nicht zulassen<br>Offenes erweitertes Wörterbuch ist deaktiviert.<br>Ein Benutzer kann nicht:<br>– Ein neues offenes erweitertes Wörterbuch hinzufügen<br />– Eine neue Konfigurationsdatei für die Suchintegration hinzufügen<br>– Die Cloudkandidat-Funktion verwenden<br>– Von Benutzer registriertes Wort senden<br>**1** – Zulassen<br>Offenes erweitertes Wörterbuch kann hinzugefügt und als Standard verwendet werden. Darüber hinaus kann die Suchintegrationsfunktion als Standard verwendet werden.<br>Ein Benutzer kann:<br>Die Cloudkandidat-Funktion verwenden.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Fehlerkonvertierungsprotokollierung deaktiviert.<br>**1** – Fehlerkonvertierungsprotokollierung aktiviert (Standard)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS-Zeichen werden gefiltert.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br />**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS0208-Zeichen werden gefiltert.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS0208- oder EUDC-Zeichen werden gefiltert.|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Strikte, höchste Filterung nicht jugendfreier Inhalte<br>**1** – Moderate Filterung nicht jugendfreier Inhalte (gültige Suchergebnisse werden nicht gefiltert – Standard)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**Anfängliche Größe erzwingen**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Benutzer kann Größe ändern (Standard).<br>**1** – Nicht-Vollbild erzwingen<br>**2** – Vollbild erzwingen|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Upgrade nicht zurückstellen (Current Branch, CB, beibehalten – Standard)<br>**1** – Zurückstellen von Updates und Upgrades ermöglichen (Gerät befolgt CBB- Regeln, Current Branch for Business)<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop und Mobile<br>**Beschreibung**: Richtlinie zum Zurückstellen von Softwareupdates für bis zu 4 Wochen<br />**Datentyp:** Ganzzahl<br />**Werte:**<br> **0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**4**: Anzahl von Wochen für das Zurückstellen von Softwareupdates.<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop und Mobile<br>**Beschreibung**: Richtlinie zum Zurückstellen von Featureupgrades für bis zu 8 Monate<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**8**: Anzahl von Monaten für das Zurückstellen von Featureupgrades.<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop und Mobile<br>**Beschreibung**: Mit dieser Einstellung wird der Empfang von Updates und Upgrades auf einem Gerät für bis zu 5 Wochen unterbrochen.<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**: Updates und Upgrades anhalten (läuft nach 5 Wochen ab)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|Name der Richtlinie und URI|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Alle Dateien überwachen (Standard)<br>**1** – Eingehende Dateien überwachen<br>**2** – Ausgehende Dateien überwachen|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** - **90** – Gibt an, wie lange Schadsoftware gespeichert wird.<br>**Standard** **0** – Bleibt immer im Quarantäneordner und wird nicht automatisch entfernt|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**1** – Schnellüberprüfung (Standard)<br>**2** – Vollständige Überprüfung|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Täglich (Standard)<br>**1** – Montag<br>**2** – Dienstag<br>**3** – Mittwoch<br>**4** – Donnerstag<br>**5** – Freitag<br>**6** – Samstag<br>**7** – Sonntag<br>**8** – Keine geplante Überprüfung|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – 12:00 Uhr<br>**60** – 1:00 Uhr<br>**120** – 2:00 Uhr (Standard)<br>**180** – 3:00 Uhr<br>**240** – 4:00 Uhr<br>**300** – 5:00 Uhr<br>**360** – 6:00 Uhr<br>**420** – 7:00 Uhr<br>**480** – 8:00 Uhr<br>**540** – 9:00 Uhr<br>**600** – 10:00 Uhr<br>**660** – 11:00 Uhr<br>**720** – 12:00 Uhr<br>**780** – 13:00 Uhr<br>**840** – 14:00 Uhr<br>**900** – 15:00 Uhr<br>**960** – 16:00 Uhr<br>**1020** – 17:00 Uhr<br>**1080** – 18:00 Uhr<br>**1140** – 19:00 Uhr<br>**1200** – 20:00 Uhr<br>**1260** – 21:00 Uhr<br>**1320** – 22:00 Uhr<br>**1381** – Wartungsfenster|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|nur Desktop<br>**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – 12:00 Uhr<br>**60** – 1:00 Uhr<br>**120** – 2:00 Uhr (Standard)<br>**180** – 3:00 Uhr<br>**240** – 4:00 Uhr<br>**300** – 5:00 Uhr<br>**360** – 6:00 Uhr<br>**420** – 7:00 Uhr<br>**480** – 8:00 Uhr<br>**540** – 9:00 Uhr<br>**600** – 10:00 Uhr<br>**660** – 11:00 Uhr<br>**720** – 12:00 Uhr<br>**780** – 13:00 Uhr<br>**840** – 14:00 Uhr<br>**900** – 15:00 Uhr<br>**960** – 16:00 Uhr<br>**1020** – 17:00 Uhr<br>**1080** – 18:00 Uhr<br>**1140** – 19:00 Uhr<br>**1200** – 20:00 Uhr<br>**1260** – 21:00 Uhr<br>**1320** – 22:00 Uhr<br>**1380** – 23:00 Uhr|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** - **100** (Standard: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|nur Desktop<br />**Datentyp:** Ganzzahl<br>**Werte:** **0** – nicht zulässig (Standard), **1** – zulässig|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig (Standard), **1** – zulässig|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte** **0** – nicht zulässig, **1** – zulässig (Standard) – Wird auch ausgeführt, falls RTP aktiviert und zulässig ist|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Bei Intervall keine Signaturen überprüfen<br>**1** – Signaturen stündlich überprüfen<br>**2** – Alle 2 Stunden überprüfen, usw.<br>**24** – Täglich überprüfen<br>**Standardwert:** 8 – Alle 8 Stunden überprüfen|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – nicht zulässig, **1** – zulässig (Standard)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Immer bestätigen (Standard)<br>**1** – Sichere Beispiele automatisch senden<br>**2** – Nie senden<br>**3** – Alle Beispiele automatisch senden|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|nur Desktop<br />**Datentyp:** Zeichenfolge<br />**Werte:**<br>*&lt;Liste der durch Semikolon getrennten Erweiterungen&gt;* Beispiel: **obj;lib**<br>**Standard:** Keine Erweiterungen ausgeschlossen|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|nur Desktop<br />**Datentyp:** Zeichenfolge<br />**Werte:**<br />*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br />Beispiel: **c:\test;c:\test1.exe**<br />**Standardwert:** Keine Pfade ausgeschlossen|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|nur Desktop<br />**Datentyp:** Zeichenfolge<br />**Werte:**<br>*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br>Beispiel: **c:\test.exe;c:\test1.exe**<br>**Standardwert:** Keine Prozesse ausgeschlossen|

## &nbsp;&nbsp;&nbsp;Edgebrowser

|Name der Richtlinie und URI|Details|
|---------------|------------|-----------|
|**Browser zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|nur Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0**: Browserverwendung nicht möglich, **1**: Browserverwendung möglich (Standard)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0**: Keine Vorschläge anzeigen **1**: Vorschläge anzeigen (Standard)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0**: Deaktiviert (Intranetsites im Microsoft Edge-Browser öffnen – Standard)<br>**1**: Aktiviert (Intranetsites in Internet Explorer öffnen)|
|**Nicht verfolgen (Do not track) zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – Deaktiviert (DNT nicht gesendet – Standard); **1** – Aktiviert (DNT senden)|
|**SmartScreen konfigurieren**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte**: **0** – Nicht zulassen; **1** – Zulassen (Standard)|
|**Popups zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – Popups blockieren (Standard), **1** – Popups zulassen|
|**Cookies zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Cookies von allen Websites zulassen (Standard)<br>**1** – Cookies anderer Anbieter blockieren<br>**2** – Alle Cookies blockieren|
|**Speichern von Kennwörtern zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Kennwort-Manager deaktiviert <br>**1** – Kennwort-Manager aktiviert|
|**AutoAusfüllen zulassen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|nur Desktop<br />**Datentyp:** Ganzzahl<br />**Werte:** **0** – Deaktiviert (Standard), **1** – Aktiviert|
|**Websiteliste für den Unternehmensmodus konfigurieren**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|nur Desktop<br />**Datentyp:** Zeichenfolge<br />**Werte:<br>**0** – Nicht konfiguriert<br>**1** – Websiteliste für den Unternehmensmodus von Internet Explorer verwenden, sofern konfiguriert (Standard)<br>**2** – Speicherort für die Websiteliste für den Unternehmensmodus angeben|

## Allgemeine Konfigurationsrichtlinieneinstellungen

Verwenden Sie die **allgemeine Microsoft Intune-Konfigurationsrichtlinie** für Windows 10, um integrierte Einstellungen für registrierte Windows 10 Desktop- und Windows 10 Mobile-Geräte zu konfigurieren. 

## &nbsp;&nbsp;&nbsp;Kennwort

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|
|**Anfordern eines Kennworts zum Entsperren von Geräten**|-|
|**Erforderlicher Kennworttyp**|Gibt an, ob das Kennwort nur numerisch sein muss oder alphanumerisch|
|**Erforderlicher Kennworttyp** - **Minimale Anzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele dieser Sätze im Kennwort enthalten sein müssen.|
|**Minimale Kennwortlänge**|Gilt nur für Windows 10 Mobile|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Für Geräte mit Microsoft 10: Wenn auf dem Gerät BitLocker aktiviert ist, wird in den BitLocker-Wiederherstellungsmodus gewechselt, sobald die Anzahl der von Ihnen angegebenen Anmeldeversuche fehlgeschlagen ist. Wenn BitLocker nicht für dieses Gerät aktiviert ist, wird diese Einstellung nicht angewendet.<br>Für Geräte mit Windows 10 Mobile: Das Gerät wird zurückgesetzt, sobald die Anzahl der von Ihnen angegebenen Anmeldeversuche fehlgeschlagen ist.|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Gibt den Zeitraum an, für den sich das Gerät im Leerlauf befinden muss, bevor der Bildschirm gesperrt wird.|
|**Kennwortablauf (Tage)**|Gibt die Zeitspanne an, nach der das Kennwort für das Gerät geändert werden muss.|
|**Kennwortverlauf speichern**|Gibt an, ob Sie verhindern möchten, dass der Endbenutzer zuvor verwendete Kennwörter erstellt.|
|**Kennwortverlauf speichern** - **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|
|**Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt**|Ist diese Einstellung aktiviert, muss der Benutzer ein Kennwort zum Entsperren des Geräts eingeben. (Nur Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Verschlüsselung

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|
|**Verschlüsselung auf mobilem Gerät anfordern**|Ermöglicht die Verschlüsselung auf Zielgeräten.<br>(Nur Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;System

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|
|**Bildschirmaufnahme zulassen**|Ermöglicht dem Benutzer, den Bildschirm des Geräts als Bild zu erfassen. (Nur Windows 10 Mobile)|
|**Manuelles Aufheben der Registrierung zulassen**|Ermöglicht dem Benutzer das manuelle Löschen des Unternehmensbereichskontos vom Gerät.|
|**Manuelle Installation des Stammzertifikats zulassen**|Betrifft Windows 10 Mobile|
|**Senden von Diagnose- und Verwendungsdaten an Microsoft zulassen**|Folgende Werte sind möglich:<br><br>**Nein**: Keine Daten werden an Microsoft gesendet.<br>**Einfach** – begrenzte Informationen werden an Microsoft gesendet<br>**Erweitert** – Erweiterte Diagnosen werden an Microsoft gesendet<br>**Vollständig (empfohlen)**: Das Gerät sendet die gleichen Daten wie mit **Erweitert** sowie zusätzliche Daten über den Gerätezustand.|


## &nbsp;&nbsp;&nbsp;Konto und Synchronisierung

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|---------------------|
|**Microsoft-Konto erlauben**|Ermöglicht dem Benutzer, das Gerät einem Microsoft-Konto zuzuordnen.|
|**Manuelles Hinzufügen von Nicht-Microsoft-Konten zulassen**|Ermöglicht dem Benutzer, dem Gerät E-Mail-Konten hinzuzufügen, die nicht mit einem Microsoft-Konto verknüpft sind.|
|**Synchronisierung von Einstellungen für Microsoft-Konten zulassen**|Ermöglicht das Synchronisieren der mit einem Microsoft-Konto verknüpften Geräte- und App-Einstellungen zwischen Geräten.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|
|**Webbrowser zulassen**|Ermöglichen Sie die Verwendung des Microsoft Edge-Webbrowsers auf dem Gerät.<br>(Nur Windows 10 Mobile)|
|**Suchvorschläge auf der Adressleiste zulassen**|Ermöglicht dem Suchmodul, Websites während der Eingabe von Suchausdrücken vorzuschlagen.|
|**Senden von Intranetdatenverkehr an Internet Explorer zulassen**|Ermöglicht Benutzern, Intranetwebsites in Internet Explorer zu öffnen.<br>(Nur Windows 10 Desktop)|
|**Nicht verfolgen (Do not track) zulassen**|Konfiguriert den Microsoft Edge-Browser zum Senden von DNT-Headern (Do Not Track, nicht nachverfolgen) an Websites, die Benutzer besuchen.|
|**SmartScreen aktivieren**|-|
|**Active Scripting zulassen**|Ermöglicht die Ausführung von Skripts wie JavaScript im Microsoft Edge-Browser.|
|**Popups zulassen**|Gilt nur für Windows 10 Desktop|
|**Cookies zulassen**|-|
|**AutoAusfüllen zulassen**|Ermöglicht Benutzern, die Einstellungen für AutoVervollständigen im Browser zu ändern.<br>(Nur Windows 10 Desktop)|
|**Kennwort-Manager zulassen**|Aktivieren oder deaktivieren Sie den Microsoft Edge-Kennwort-Manager.|
|**Ort der Standortliste für Enterprise-Modus**|Gibt an, wo Sie die Liste der Websites finden, die im Unternehmensmodus geöffnet werden. Benutzer können diese Liste nicht bearbeiten.<br>(Nur Windows 10 Desktop)|

## &nbsp;&nbsp;&nbsp;Apps

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|---------------------|
|**App Store zulassen**|Gilt nur für Windows 10 Mobile|



## &nbsp;&nbsp;&nbsp;Mobilfunk

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|---------------------|
|**Datenroaming zulassen**|Ermöglicht beim Zugriff auf Daten das Roaming zwischen Netzwerken.|
|**VPN über Mobilfunk zulassen**|Steuert, ob das Gerät auf VPN-Verbindungen zugreifen kann, wenn es mit einem Mobilfunknetz verbunden ist.|
|**VPN-Roaming über Mobilfunk zulassen**|Steuert, ob das Gerät beim Roaming in einem Mobilfunknetz auf VPN-Verbindungen zugreifen kann.|

## &nbsp;&nbsp;&nbsp;Hardware

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|
|**Kamera zulassen**|-|
|**Wechselspeichermedien zulassen**|Gibt an, ob externe Speichergeräte wie SD-Karten mit dem Gerät verwendet werden können.|
|**WLAN zulassen**|Gilt nur für Windows 10 Mobile|
|**Internetfreigabe zulassen**|Ermöglicht die gemeinsame Nutzung der Internetverbindung auf dem Gerät.|
|**Manuelle WLAN-Konfiguration zulassen**|Steuert, ob die Benutzer eigene WLAN-Verbindungen konfigurieren dürfen oder ob nur über WLAN-Profile konfigurierte Verbindungen verwendet werden dürfen.<br>(Nur Windows 10 Mobile)|
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Ermöglicht automatische Verbindungen des Geräts mit unverschlüsselten WLAN-Hotspots und das automatische Akzeptieren der Geschäftsbedingungen für die Verbindung.|
|**Geolocation zulassen**|Gibt an, ob das Gerät Ortungsdienstinformationen verwenden kann.|
|**NFC zulassen**|Ermöglicht die Verwendung von NFC-Funktionen (Near Field Communications) auf dem Gerät.|
|**Bluetooth zulassen**|-|
|**Sichtbaren Modus für Bluetooth zulassen**|Ermöglicht die Erkennung dieses Geräts durch andere Bluetooth-Geräte.|
|**Bluetooth-Werbung zulassen**|Ermöglicht Geräten dem Empfang von Werbung über Bluetooth.|
|**Handyzurücksetzung zulassen**|Steuert, ob Benutzer ihre Geräte auf Werkseinstellungen zurücksetzen dürfen.|
|**USB-Verbindung zulassen**|Steuert, ob die Geräte über eine USB-Verbindung auf externe Speichergeräte zugreifen können.|
|**Diebstahlschutzmodus zulassen**|Konfigurieren Sie, ob der Windows-Diebstahlschutzmodus aktiviert ist.|

## &nbsp;&nbsp;&nbsp;Features

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|----------------------|---------------------|
|**Kopieren und Einfügen zulassen**|Gilt nur für Windows 10 Mobile|
|**Sprachaufzeichnung zulassen**|Gilt nur für Windows 10 Mobile|
|**Cortana zulassen**|Aktivieren oder deaktivieren Sie den Cortana-Sprach-Assistenten.|
|**Info-Center-Benachrichtigungen zulassen**|Aktivieren oder deaktivieren Sie Wartungscenterbenachrichtigungen auf dem Gerätesperrbildschirm.<br>(Nur Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Alle Einstellungen gelten für nur Windows 10 Desktop.

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|-|-|
|**Echtzeitüberwachung zulassen**|Ermöglicht die Echtzeitüberwachung auf Schadsoftware, Spyware und andere unerwünschte Software.|
|**Verhaltensüberwachung zulassen**|Ermöglicht Defender, Geräte auf bestimmte bekannte Muster verdächtiger Aktivitäten zu überprüfen.|
|**Netzwerkinspektionssystem aktivieren**|Das Netzwerkinspektionssystem (NIS) trägt zum Schutz von Geräten vor netzwerkbasierten Sicherheitslücken bei, indem die Signaturen bekannter Sicherheitsrisiken aus dem Endpoint Protection-Center von Microsoft verwendet werden, um schädlichen Datenverkehr zu erkennen und zu blockieren.|
|**Alle Downloads werden überprüft**|Steuert, ob Defender alle aus dem Internet heruntergeladenen Dateien überprüft.|
|**Skriptüberprüfung zulassen**|Ermöglicht Defender die Überprüfung von Skripts, die in Internet Explorer verwendet werden.|
|**Datei- und Programmaktivität überwachen**|Aktivieren Sie diese Einstellung, um Defender die Überwachung der Datei- und Programmaktivität auf Geräten zu ermöglichen.|
|**Tage für Nachverfolgung behandelter Schadsoftware**|Ermöglicht Defender die fortgesetzte Nachverfolgung behandelter Schadsoftware für die angegebene Anzahl von Tagen, damit Sie zuvor betroffene Geräte manuell überprüfen können. Wenn Sie die Anzahl von Tagen auf **0** festlegen, bleibt Schadsoftware im Quarantäneordner und wird nicht automatisch entfernt. |
|**Zugriff auf die Clientbenutzeroberfläche zulassen**|Steuert, ob die Benutzeroberfläche von Windows Defender für Endbenutzer ausgeblendet ist.<br>Wenn diese Einstellung geändert wird, wird die Änderung wirksam, wenn der Endbenutzer-PC das nächste Mal neu gestartet wird.|
|**Eine tägliche Schnellüberprüfung planen**|Ermöglicht Ihnen die Planung einer Schnellüberprüfung, die täglich zum ausgewählten Zeitpunkt erfolgt.|
|**Systemüberprüfung planen**|Sie können eine vollständige Überprüfung oder eine Schnellüberprüfung des Systems planen, die regelmäßig am ausgewählten Tag und zur ausgewählten Zeit auftritt.|
|**Prozessornutzung während der Überprüfung begrenzen auf**|Ermöglicht die Begrenzung des Umfangs an CPU, der bei Überprüfungen genutzt werden darf (von **1** bis **100**).|
|**Archivdateien überprüfen**|Ermöglicht Defender die Überprüfung von Archivdateien wie ZIP- oder CAB-Dateien.|
|**Scannen von E-Mail-Nachrichten**|Ermöglicht Defender das Überprüfen von E-Mail-Nachrichten beim Eingang auf dem Gerät.|
|**Wechseldatenträger überprüfen**|Ermöglicht Defender das Überprüfen von Wechseldatenträgern wie USB-Sticks.|
|**Zugeordnete Netzwerklaufwerke überprüfen**|Ermöglicht Defender das Überprüfen von Dateien auf zugeordneten Netzwerklaufwerken.<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|
|**Dateien überprüfen, die in freigegebenen Netzwerkordnern geöffnet wurden**|Ermöglicht Defender das Überprüfen von Dateien auf freigegebenen Netzlaufwerken (z. B. solche, auf die über einen UNC-Pfad zugegriffen wird).<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|
|**Intervall zum Aktualisieren von Signaturen**|Geben Sie das Intervall an, in dem Defender auf neue Signaturdateien prüfen soll.|
|**Cloudschutz zulassen**|Lassen Sie zu, oder verhindern Sie, dass Microsoft Active Protection Service Informationen über Schadsoftwareaktivitäten von den von Ihnen verwalteten Geräten erhält. Diese Informationen werden verwendet, um den Dienst in der Zukunft zu verbessern.|
|**Beim Senden von Beispielen beim Benutzer nachfragen**|Steuert, ob die Dateien automatisch an Microsoft gesendet werden, die möglicherweise von Microsoft genauer analysiert werden müssen, um festzustellen, ob sie schädlich sind.|
|**Erkennung möglicherweise unerwünschter Anwendungen**|Mit dieser Einstellung können registrierte Windows-Desktopgeräte gegen die Ausführung von Software geschützt werden, die von Windows Defender als möglicherweise unerwünscht eingestuft wird. Sie können verhindern, dass diese Anwendungen ausgeführt werden, oder den Überwachungsmodus verwenden, um zu melden, wenn eine möglicherweise unerwünschte Anwendung installiert wird.|
|**Von der Überprüfung oder dem Echtzeitschutz auszuschließende Dateien und Ordner**|Fügen Sie Dateien und Ordner wie **C:\Pfad** oder **%ProgramFiles%\Pfad\Dateiname.exe** der Ausschlussliste hinzu. Diese Dateien und Ordner werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|
|**Dateierweiterungen, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Dateierweiterungen wie **JPG** oder **TXT** der Ausschlussliste hinzu. Dateien mit diesen Erweiterungen werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|
|**Prozesse, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Prozesse des Typs **.exe**, **.com** oder **.scr** der Ausschlussliste hinzu. Diese Prozesse werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.| 


## &nbsp;&nbsp;&nbsp;Updates

|Name der Einstellung|Erforderliche zusätzliche Informationen (wo erforderlich)|
|----------------|---------------|
|**Automatische Updates zulassen**|Aktivieren Sie diese Einstellung, um automatische Updates zuzulassen. Konfigurieren Sie dann eine der folgenden Einstellungen, um das Updateverhalten zu steuern:<br />**Download benachrichtigen**<br />**Automatische Installation während der Wartung**<br />**Automatische Installation und Neustart während der Wartung**<br />**Zur festgelegten Zeit automatisch installieren und neu starten** **Hinweis**: Wenn diese Option ausgewählt ist, können Sie auch die folgenden Einstellungen konfigurieren: **Benachrichtigung für Endbenutzer unterdrücken** und **Installationstag für geplante Updates definieren**.<br>(Nur Windows 10 Desktop)|
|**Features der Vorabversion zulassen**|Bietet Microsoft die Möglichkeit, Einstellungen und Features der Vorabversion für Windows 10-Geräte bereitzustellen. Sie können auswählen, ob nur Einstellungen oder alle Einstellungen und Features der Vorabversion installiert werden sollen.|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


