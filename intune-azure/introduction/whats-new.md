---
title: Neuigkeiten in der Microsoft Intune-Vorschau | Intune in Azure (Vorschau) | Microsoft Docs
description: Erfahren Sie, welche Neuigkeiten die Vorschau von Intune Azure bietet
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9852fdb9d1bfeede4931f0ead2fa0898dfcacb0b
ms.openlocfilehash: a05c7464b3f2fbca467d44218904671529320dda
ms.lasthandoff: 02/15/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Neuigkeiten in der Vorschau von Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Im Laufe der öffentliche Vorschau werden weitere Features hinzugefügt, über die wir Sie hier informieren werden.

## <a name="february-2017"></a>Februar 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Einschränken der Registrierung von Mobilgeräten <!--747600, 795782-->
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.

* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.  
* Für iOS und Android gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Anzeigen aller Aktionen auf verwalteten Geräten <!--677150-->
Ein neuer Bericht über __Geräteaktionen__ zeigt, wer Remoteaktionen wie das Zurücksetzen auf Werkseinstellungen auf Geräten ausgeführt hat sowie den Status dieser Aktion. Weitere Informationen finden Sie unter [Was ist die Geräteverwaltung?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->
Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Anzeigen von Gerätekategoriern <!--814654-->
Sie können nun die Gerätekategorie als Spalte in der Geräteliste anzeigen. Sie können die Kategorie auch im Abschnitt „Eigenschaften“ des Blatts „Geräteeigenschaften“ bearbeiten. Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps). 

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

