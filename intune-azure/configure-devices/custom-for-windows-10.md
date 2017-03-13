---
title: "Benutzerdefinierte Intune-Einstellungen für Windows 10-Geräte"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Windows 10-Profil verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 647415914fb0f44807eff7baf7a56ea3a382f027
ms.lasthandoff: 02/18/2017


---

# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Benutzerdefinierte Geräteeinstellungen für Windows 10-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Stellen Sie mithilfe des **benutzerdefinierten** Profils von Microsoft Intune für Windows 10 und Windows 10 Mobile OMA-URI-Einstellungen (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Geräten zu steuern. Windows 10 stellt viele Einstellungen über die [Richtlinienkonfigurationsdienst-Anbieter (Policy Configuration Service Provider; Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) zur Verfügung.

1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](how-to-configure-custom-settings.md).
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.
3. Klicken Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** auf **Hinzufügen**, um einen neuen Wert hinzuzufügen. Sie können auch auf **Exportieren** klicken, um eine Liste aller konfigurierten Werte in einer durch Trennzeichen getrennten Wertedatei (CSV) anzuzeigen.
4. Geben Sie für jede OMA-URI-Einstellung, die Sie hinzufügen möchten, die folgenden Informationen ein. Verwenden Sie die Liste in diesem Thema, um weitere Informationen zu den Einstellungen zu erhalten, die Sie verwenden können:
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
5. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.
Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="example"></a>Beispiel
Im folgenden Screenshot ist die Einstellung **Connectivity/AllowVPNOverCellular** aktiviert. Dadurch kann ein Windows 10-Gerät eine VPN-Verbindung über ein Mobilfunknetz öffnen.

> ![Beispiel für eine benutzerdefinierte Richtlinie mit VPN-Einstellungen](./media/custom-policy-example.png)


## <a name="policy-settings"></a>Richtlinieneinstellungen

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
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop und Mobile<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0** – Upgrade nicht zurückstellen (Current Branch, CB, beibehalten – Standard)<br>**1** – Zurückstellen von Updates und Upgrades ermöglichen (Gerät befolgt CBB- Regeln, Current Branch for Business)<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop und Mobile<br>**Beschreibung**: Richtlinie zum Zurückstellen von Softwareupdates für bis zu 4 Wochen<br />**Datentyp:** Ganzzahl<br />**Werte:**<br> **0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**4**: Anzahl von Wochen für das Zurückstellen von Softwareupdates.<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop und Mobile<br>**Beschreibung**: Richtlinie zum Zurückstellen von Featureupgrades für bis zu 8 Monate<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**8**: Anzahl von Monaten für das Zurückstellen von Featureupgrades.<br />Details hierzu finden Sie in den folgenden Abschnitten:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop und Mobile<br>**Beschreibung**: Mit dieser Einstellung wird der Empfang von Updates und Upgrades auf einem Gerät für bis zu 5 Wochen unterbrochen.<br />**Datentyp:** Ganzzahl<br />**Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**: Updates und Upgrades anhalten (läuft nach 5 Wochen ab)|

## <a name="windows-defender-settings"></a>Windows Defender-Einstellungen

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

## <a name="edge-browser-settings"></a>Edge-Browsereinstellungen

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

