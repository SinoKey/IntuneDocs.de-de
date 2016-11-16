---
title: "Registrieren von Geräten | Microsoft Intune"
description: "Die Registrierung durch die Verwaltung mobiler Geräte (MDM) dient dazu, Geräte in die Verwaltung aufzunehmen und den Zugriff auf Ressourcen zu ermöglichen."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d51f34dea3463bec83ea39cdfb79c7bedf9e3926
ms.openlocfilehash: 0b60e7a7a921762e682185af273bb94f24441a0c


---

# <a name="enroll-devices-for-management-in-intune"></a>Registrieren von Geräten für die Verwaltung in Intune
Sie können Geräte, einschließlich Windows PCs, registrieren, um die Verwaltung mobiler Geräte (MDM, Mobile Device Management) mit Microsoft Intune zu aktivieren. Dieses Thema beschreibt die verschiedenen Methoden zum Registrieren von mobilen Geräten in der Intune-Verwaltung. Auf welche Weise Sie Ihre Geräte registrieren, hängt von Gerätetyp, Besitz und benötigtem Verwaltungsniveau ab. Bei der BYOD-Registrierung (Bring Your Own Device, private Geräte der Mitarbeiter) können die Benutzer ihre privaten Smartphones, Tablets oder PCs selbst registrieren. Die COD-Registrierung (Corporate-Owned Device, Firmeneigene Geräte) ermöglicht Verwaltungsszenarien wie das Remotezurücksetzen, gemeinsam verwendete Geräte oder Benutzeraffinität für ein Gerät.

Wenn Sie [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) verwenden, entweder lokal oder in der Cloud gehostet, können Sie eine einfache Intune-Verwaltung ohne Registrierung aktivieren. Auch Windows-PCs können mit [Intune-Clientsoftware](#manage-windows-pcs-with-intune) verwaltet werden.

## <a name="overview-of-device-enrollment-methods"></a>Übersicht über die Geräteregistrierungsmethoden

In der folgenden Tabelle werden die Registrierungsmethoden von Intune zusammen mit den von ihnen unterstützten Funktionen dargestellt. Diese Funktionen beinhalten:
- **Zurücksetzen** –Zurücksetzen des Geräts auf Werkseinstellungen, wobei alle Daten entfernt werden. Weitere Informationen finden Sie auf der Seite [Abkoppeln von Geräten von der Intune-Verwaltung](retire-devices-from-microsoft-intune-management.md).
- **Affinität** – Ordnet Geräte Benutzern zu. Für die Verwaltung mobiler Geräte (MAM, Mobile Application Management) und den bedingten Zugriff auf Unternehmensdaten erforderlich. Weitere Informationen finden Sie auf der Seite [Registrieren firmeneigener iOS-Geräte in Microsoft Intune](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices).
- **Sperre** – Hindert Benutzer daran, das Gerät aus der Verwaltung zu entfernen. Für iOS-Geräte ist der Modus „Betreut“ für die Sperre erforderlich. Weitere Informationen finden Sie unter [Geräteschutz durch Remotesperre und Zurücksetzen der Kennung](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**iOS-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen** |  **Affinität**    |   **Sperren** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |   Nein | [Weitere Informationen](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nein |Nein |Nein  | [Weitere Informationen](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Ja |   Optional |  Optional|[Weitere Informationen](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB (Setup-Assistent)](#usb-sa)**| Ja |   Optional |  Nein| [Weitere Informationen](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB (direkt)](#usb-direct)**| Nein |    Nein  | Nein|[Weitere Informationen](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen** |  **Affinität**    |   **Sperren** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Ja|   Ja |   Nein | [Weitere Informationen](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nein |Nein |Nein  |[Weitere Informationen](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Android-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen** |  **Affinität**    |   **Sperren** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |   Nein | [Weitere Informationen](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nein |Nein |Nein  |[Weitere Informationen](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Eine Reihe von Fragen, die Sie beim Ermitteln der richtigen Methode unterstützen, finden Sie unter [Auswählen der Registrierungsart von Geräten](/intune/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>BYOD
BYOD-Benutzer installieren die Unternehmensportal-App und registrieren ihr Gerät. Dadurch können Benutzer Verbindungen mit dem Unternehmensnetzwerk herstellen und zur Domäne oder zu Azure Active Directory beitreten. Für die meisten Plattformen müssen Sie BYOD-Registrierung für viele COD-Szenarios ermöglichen. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwaltung von mobilen Geräten in Intune](prerequisites-for-enrollment.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

## <a name="corporateowned-devices"></a>Firmeneigene Geräte
Firmeneigene Geräte (Corporate-owned devices, COD) können mithilfe der Intune-Konsole verwaltet werden. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

Weitere Informationen finden Sie unter [Registrieren firmeneigener Geräte bei Microsoft Intune](manage-corporate-owned-devices.md).

### <a name="dem"></a>Geräteregistrierungs-Manager (DEM)
Der Geräteregistrierungs-Manager ist ein besonderes Intune-Konto, das zum Registrieren und Verwalten mehrere firmeneigener Geräte verwendet wird. Manager können das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP (Device Enrollment Program)
Mit der Apple DEP-Verwaltung (Device Enrollment Program, Programm zur Geräteregistrierung) können Sie Richtlinien erstellen und „drahtlos“ auf iOS-Geräten bereitstellen, die mit DEP erworben wurden und verwaltet werden. Das Gerät wird beim ersten Einschalten durch den Benutzer registriert und führt dann den iOS-Setup-Assistenten aus. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Gesperrte Registrierung
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über das [Geräteregistrierungsprogramm](ios-device-enrollment-program-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### <a name="usbsa"></a>USB (Setup-Assistent)
Über USB angeschlossene, unternehmenseigene Geräte werden mit der Intune-Richtlinie vorbereitet. Der Administrator erstellt für die Registrierung mit dem Einrichtungsassistenten diese Intune-Richtlinie und exportiert sie in Apple Configurator. Der Administrator muss jedes Gerät manuell registrieren. Benutzer erhalten ihre Geräte und führen den Setup-Assistenten aus, um ihr Gerät zu registrieren. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über die [Registrierung über den Setup-Assistenten mit Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### <a name="usbdirect"></a>USB (direkt)
Der Administrator erstellt für die direkte Registrierung eine Intune-Richtlinie und exportiert sie in Apple Configurator. Über USB angeschlossene, unternehmenseigene Geräte werden direkt registriert, ohne dass ein Zurücksetzen auf Werkseinstellungen erforderlich ist. Der Administrator muss jedes Gerät manuell registrieren. Geräte werden als benutzerlose Geräte verwaltet. Sie werden nicht gesperrt oder überwacht und unterstützen nicht den bedingten Zugriff, die Erkennung von Jailbreaks oder die Verwaltung mobiler Geräte. Erfahren Sie mehr über die [direkte Registrierung mit Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der MDM EAS-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet.

Weitere Informationen finden Sie unter [Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Aktivieren der Windows PC-Verwaltung mit Intune  
Sie können Microsoft Intune auch verwenden, um Windows-PCs mit der Intune-Clientsoftware zu verwalten. Mit dem Intune-Client verwaltete PCs können:

 - Software- und Hardwareinventurberichte erstellen
 - Desktopanwendung installieren (z. B. EXE- und MSI-Dateien)
 - Verwalten von Firewall-Einstellungen

PCs, die mit der Intune-Clientsoftware verwaltet werden, können nicht vollständig zurückgesetzt werden, obwohl das selektive Zurücksetzen verfügbar ist. Mit dem Intune-Softwareclient verwaltete PCs können viele der Intune Verwaltungsfunktionen wie z.B. den bedingten Zugriff, VPN- und WLAN-Einstellungen oder die Bereitstellung von Zertifikaten und E-Mail-Konfigurationen nicht nutzen.

Weitere Informationen finden Sie unter [Verwalten von Windows-PCs mit der Intune-PC-Clientsoftware](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Unterstützte Geräteplattformen

Intune kann folgende Geräteplattformen verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Nächste Schritte
- [Voraussetzungen für die Geräteregistrierung](prerequisites-for-enrollment.md)
- [Verwalten firmeneigener Geräte](manage-corporate-owned-devices.md)
- [Unterstützte mobile Geräte und Computer](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Nov16_HO2-->


