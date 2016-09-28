---
title: "Registrieren von Geräten | Microsoft Intune"
description: "Die Registrierung durch die Verwaltung mobiler Geräte (MDM) dient dazu, Geräte in die Verwaltung aufzunehmen und den Zugriff auf Ressourcen zu ermöglichen."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: e6b182ebab1691c62e69cabaf4689ac7395ab31a
ms.openlocfilehash: 0995d3ced978f5213fdb0e9905f508b64a1e5c09


---

# Registrieren von Geräten für die Verwaltung in Intune
Sie können Geräte, einschließlich Windows PCs, registrieren, um die Verwaltung mobiler Geräte (MDM, Mobile Device Management) mit Microsoft Intune zu aktivieren. Dieses Thema beschreibt die verschiedenen Methoden zum Registrieren von mobilen Geräten in der Intune-Verwaltung. In welcher Weise Geräte registriert werden, hängt vom Gerätetyp, dem Besitz und dem erforderlichen Maß an Verwaltung ab. Bei der BYOD-Registrierung (Bring Your Own Device, private Geräte der Mitarbeiter) können die Benutzer ihre privaten Smartphones, Tablets oder PCs selbst registrieren. Die COD-Registrierung (Corporate-Owned Device, Firmeneigene Geräte) ermöglicht Verwaltungsszenarien wie das Remotezurücksetzen, gemeinsam verwendete Geräte oder Benutzeraffinität für ein Gerät.

Wenn Sie [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) verwenden, entweder lokal oder in der Cloud gehostet, können Sie eine einfache Intune-Verwaltung ohne Registrierung aktivieren. Auch Windows-PCs können mit [Intune-Clientsoftware](#manage-windows-pcs-with-intune) verwaltet werden.

## Übersicht über die Geräteregistrierungsmethoden

In der folgenden Tabelle werden die Registrierungsmethoden von Intune zusammen mit den von ihnen unterstützten Funktionen dargestellt. Diese Funktionen beinhalten:
- **Zurücksetzen** –Zurücksetzen des Geräts auf Werkseinstellungen, wobei alle Daten entfernt werden. [Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md)
- **Affinität** – Ordnet Geräte Benutzern zu. Für die Verwaltung mobiler Geräte (MAM, Mobile Application Management) und den bedingten Zugriff auf Unternehmensdaten erforderlich. [Benutzeraffinität](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)
- **Sperre** Hindert Benutzer daran, das Gerät aus der Verwaltung zu entfernen. Für iOS-Geräte ist der Modus „Betreut“ für die Sperre erforderlich. [Remotesperre](retire-devices-from-microsoft-intune-management.md#block-access-a-device)

**iOS-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen** |  **Affinität**    |   **Sperren** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |   Nein | [Mehr](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[Geräteregistrierungs-Manager (DEM)](#dem)**|   Nein |Nein |Nein  | [Mehr](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP (Device Enrollment Program)](#dep)**|   Ja |   Optional |  Optional|[Mehr](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB (Setup-Assistent)](#usb-sa)**| Ja |   Optional |  Nein| [Mehr](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB (direkt)](#usb-direct)**| Nein |    Nein  | Nein|[Mehr](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows- und Android-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen** |  **Affinität**    |   **Sperren** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |   Nein | [Mehr](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[Geräteregistrierungs-Manager (DEM)](#dem)**|   Nein |Nein |Nein  |[Mehr](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Eine Reihe von Fragen, die Sie beim Ermitteln der richtigen Methode unterstützen, finden Sie unter [Auswählen der Registrierungsart von Geräten](/intune/get-started/choose-how-to-enroll-devices1).

## BYOD
BYOD-Benutzer installieren die Unternehmensportal-App und registrieren ihr Gerät. Dies ermöglicht den Benutzern das Herstellen von Verbindungen mit dem Unternehmensnetzwerk und das Beitreten zur Domäne oder zu Azure Active Directory. Das Aktivieren der BYOD-Registrierung ist auf den meisten Plattformen eine Voraussetzung für viele COD-Szenarien. Weitere Informationen finden Sie unter [Voraussetzungen für die Geräteregistrierung](prerequisites-for-enrollment.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

## Firmeneigene Geräte
Firmeneigene Geräte (COD) können mit der Intune-Konsole verwaltet werden. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

[Registrieren aller firmeneigenen Geräte](manage-corporate-owned-devices.md)

### Geräteregistrierungs-Manager (DEM)
Der Geräteregistrierungs-Manager ist ein besonderes Intune-Konto, das zum Registrieren und Verwalten mehrere firmeneigener Geräte verwendet wird. Manager können das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### DEP (Device Enrollment Program)
Mit der Apple DEP-Verwaltung (Device Enrollment Program, Programm zur Geräteregistrierung) können Sie Richtlinien erstellen und „drahtlos“ auf iOS-Geräten bereitstellen, die mit DEP erworben wurden und verwaltet werden. Das Gerät wird beim ersten Einschalten durch den Benutzer registriert und führt dann den iOS-Setup-Assistenten aus. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Gesperrte Registrierung
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über das [Geräteregistrierungsprogramm](ios-device-enrollment-program-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### USB (Setup-Assistent)
USB-Verbindung, Registrierung mit dem Setup-Assistenten. Der Administrator erstellt eine Intune-Richtlinie und exportiert sie in Apple Configurator. Über USB angeschlossene, unternehmenseigene Geräte werden mit der Intune-Richtlinie vorbereitet. Der Administrator muss jedes Gerät manuell registrieren. Benutzer erhalten ihre Geräte und führen den Setup-Assistenten aus, um ihr Gerät zu registrieren. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über die [Registrierung über den Setup-Assistenten mit Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### USB (direkt)
Direkte Registrierung. Der Administrator erstellt eine Intune-Richtlinie und exportiert sie in Apple Configurator. Über USB angeschlossene, unternehmenseigene Geräte werden direkt registriert, ohne dass ein Zurücksetzen auf Werkseinstellungen erforderlich ist. Der Administrator muss jedes Gerät manuell registrieren. Geräte werden als benutzerlose Geräte verwaltet. Sie werden nicht gesperrt oder überwacht und unterstützen nicht den bedingten Zugriff, die Erkennung von Jailbreaks und die Verwaltung mobiler Geräte. Erfahren Sie mehr über die [direkte Registrierung mit Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

## Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der MDM EAS-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet.

[Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Verwalten von Windows-PCs mit Intune  
Sie können Microsoft Intune auch verwenden, um Windows-PCs mit der Intune-Clientsoftware zu verwalten. Mit dem Intune-Client verwaltete PCs können:

 - Software- und Hardwareinventurberichte erstellen
 - Desktopanwendung installieren (z. B. EXE- und MSI-Dateien)
 - Firewalleinstellungen

Mit der Intune-Clientsoftware verwaltete PCs können nicht zurückgesetzt werden und können viele der Intune Verwaltungsfunktionen wie z. B. den bedingten Zugriff, VPN- und WLAN-Einstellungen oder die Bereitstellung von Zertifikaten und E-Mail-Konfigurationen nicht nutzen.

[Verwalten von Windows-PCs mit Intune](manage-windows-pcs-with-microsoft-intune.md)

##  Unterstützte Geräteplattformen

Intune kann folgende Geräteplattformen verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Nächste Schritte
- [Voraussetzungen für die Geräteregistrierung](prerequisites-for-enrollment.md)
- [Verwalten firmeneigener Geräte](manage-corporate-owned-devices.md)
- [Unterstützte mobile Geräte und Computer](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Sep16_HO3-->


