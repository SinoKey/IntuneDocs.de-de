---
title: Neuigkeiten in der Microsoft Intune-Vorschau | Intune in Azure (Vorschau) | Microsoft Docs
description: 'Intune in Azure (Vorschau): Erfahren Sie, welche Neuigkeiten die Vorschau von Intune in Azure bietet.'
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Neuigkeiten in der Vorschau von Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Im Laufe der öffentliche Vorschau werden weitere Features hinzugefügt, über die wir Sie hier informieren werden.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Januar 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Zuweisen von Branchen-Apps unabhängig vom Registrierungsstatus von Geräten <!--748823-->
Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn ein Benutzergerät nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren. Siehe [Was ist die App-Verwaltung?](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Lösen von Problemen, wenn iOS-Geräte inaktiv sind oder die Verwaltungskonsole nicht mit ihnen kommunizieren kann
Wenn Geräte von Benutzern keinen Kontakt mehr mit Intune haben, können Sie neue Schritte zur Problembehandlung bereitstellen, damit sie erneuten Zugriff auf Unternehmensressourcen gewinnen können. Weitere Informationen finden Sie unter [Geräte sind inaktiv oder die Verwaltungskonsole kann nicht mit ihnen kommunizieren](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Dezember 2016 (erste Version)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integration der Telekommunikationsausgaben in der öffentlichen Vorschau des Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Bereitstellen und Verwalten von Apps aus einem Store auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von branchenspezifischen Apps auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von per Volumenlizenz erworbenen Apps auf iOS- und Windows-Geräten
- Bereitstellen und Verwalten von Web-Apps auf Android-, iOS- und Windows-Geräten
- In iOS verwaltete App-Konfigurationsprofile
- Konfigurieren von App-Schutzrichtlinien und Bereitstellen von branchenspezifischen Apps auf Geräten, die nicht in Intune registriert sind
- VPN-Profile, VPN pro App, WLAN, E-Mail und Zertifikatprofile
- Konformitätsrichtlinien
- Bedingter Zugriff für Azure AD
- Bedingter Zugriff auf lokales Exchange
- Geräteregistrierung
- Rollenbasierte Zugriffssteuerung

## <a name="deprecated-features-in-the-azure-portal"></a>Veraltete Features im Azure-Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Unterstützung für die zeilenweise Überprüfung von Hardware-IDs
Das Azure-Portal unterstützt keine zeilenweise Überprüfung von Hardware-IDs für IMEI-Nummern und Apple-Seriennummern. In der klassischen Intune-Konsole können Sie Informationen aus einer durch Trennzeichen getrennten Datei (CSV) importieren und die vorhandenen Daten für einzelne Hardware-IDs überschreiben. Das Azure-Portal bietet eine optimierte Option, durch die automatisch die Daten für alle Hardware-IDs überschrieben oder neue Daten für vorhandene IDs ignoriert werden.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal nicht zeilenweise entscheiden, welche IMEI-Geräte (International Mobile Equipment Identity) aktualisiert werden sollen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Diese Änderung tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Unterstützung für Standardprofile für Unternehmensgeräteregistrierungen in Apple DEP
Das Azure-Portal unterstützt nicht das Standardprofil für Unternehmensgeräteregistrierungen für Geräteseriennummern in Apple DEP (Device Enrollment Programm). Diese Funktion, die in der klassischen Intune-Konsole zur Verfügung steht, wird nicht fortgeführt, damit nicht versehentlich Profile zugewiesen werden. Im Azure-Portal wird Seriennummern, die aus einem Apple DEP-Konto synchronisiert werden, zunächst keine Profil für die Unternehmensgeräteregistrierung zugewiesen.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal keine Standardprofilrichtlinie für alle Apple-Geräte festlegen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Dies tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.



<!--HONumber=Feb17_HO1-->


