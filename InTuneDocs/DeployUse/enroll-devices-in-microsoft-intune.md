---
title: "Registrieren von Geräten | Microsoft Intune"
description: "Die Registrierung durch die Verwaltung mobiler Geräte (MDM) dient dazu, Geräte in die Verwaltung aufzunehmen und den Zugriff auf Ressourcen zu ermöglichen."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: 41c21da7c95ef15f817aa344aa5b2d6479b65922


---

# Registrieren von Geräten für die Verwaltung in Intune
Die Registrierung durch die Verwaltung mobiler Geräte (MDM) in Microsoft Intune dient dazu, Geräte in die Verwaltung aufzunehmen und den Zugriff auf Ressourcen zu ermöglichen. Auf welche Weise Sie die Geräte registrieren, hängt von Gerätetyp, Besitz und benötigtem Verwaltungsniveau ab. Szenarien mit „Bring your own Device“- (BYOD) und firmeneigenen Geräten (Company-Owned Device, COD) erfordern eine Registrierung. Organisationen, die Exchange ActiveSync verwenden, entweder lokal oder in der Cloud gehostet, können ein niedrigeres Verwaltungsniveau ohne Registrierungsanforderungen aktivieren. Windows-PCs können auch mit Intune-Clientsoftware verwaltet werden.

###  Unterstützte Geräteplattformen

Intune kann folgende Geräteplattformen verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Festlegen der Autorität zur Verwaltung mobiler Geräte
Die MDM-Autorität definiert den Verwaltungsdienst, der über die Berechtigung zum Verwalten einer Gruppe von Geräten verfügt. Die Optionen für die MDM-Autorität umfassen Intune selbst und Configuration Manager mit Intune. Wenn Sie Configuration Manager als Verwaltungsautorität festlegen, kann kein anderer Dienst für die Verwaltung mobiler Geräte verwendet werden.

>[!IMPORTANT]
> Sie sollten sorgfältig überlegen, ob Sie mobile Geräte nur mit Intune (Onlinedienst) oder mit System Center Configuration Manager mit Intune (lokale Softwarelösung in Verbindung mit dem Onlinedienst) verwalten möchten. Nachdem Sie die Autorität für die Verwaltung mobiler Geräte festgelegt haben, kann sie nicht mehr geändert werden.

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) die Optionen **Verwaltung** &gt; **Verwaltung mobiler Geräte** aus.

2.  Klicken Sie in der Liste **Aufgaben** auf **Autorität für die Verwaltung mobiler Geräte festlegen**. Das Dialogfeld **MDM-Autorität festlegen** wird geöffnet.

    ![Dialogfeld „MDM-Autorität festlegen“](../media/intune-mdm-authority.png)

3.  Intune erfordert eine Bestätigung, dass es als MDM-Autorität verwendet werden soll. Aktivieren Sie das Kontrollkästchen, und wählen Sie dann **Ja** aus, um Microsoft Intune zum Verwalten mobiler Geräte zu verwenden.

## Konfigurieren des Intune-Unternehmensportals

Im Intune-Unternehmensportal können Benutzer auf Unternehmensdaten zugreifen, häufige Aufgaben wie das Registrieren von Geräten und das Installieren von Apps ausführen und sich über Unterstützungsmöglichkeiten durch Ihre IT-Abteilung informieren.

> [!TIP]
> Wenn Sie das Unternehmensportal anpassen, gelten die Konfigurationen sowohl für die Unternehmensportalwebsite als auch für die Unternehmensportal-Apps.

Durch Anpassen des Unternehmensportals können Sie Ihren Endbenutzern eine vertraute und hilfreiche Benutzeroberfläche bereitstellen. Melden Sie sich zu diesem Zweck einfach als Mandanten- oder Dienstadministrator bei der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) an, wählen Sie **Verwaltung** &gt; **Unternehmensportal** aus, und konfigurieren Sie die Einstellungen für das Unternehmensportal.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

## Übersicht über die Geräteregistrierungsmethoden

Die folgende Tabelle zeigt Registrierungsmethoden für unternehmenseigene Geräte samt ihren Vorteilen.

**iOS-Registrierungsmethoden**

| **Methode** |  **[Zurücksetzen](#Wipe)** | **[Affinität](#Affinity)**   |   **[Gesperrt](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nein|    Ja |   Nein |
|**[Geräteregistrierungs-Manager (DEM)](#DEM)**|   Nein |Nein |Nein  |
|**[DEP (Device Enrollment Program)](#DEP)**|   Ja |   Opt |   Opt|
|**[USB (Setup-Assistent)](#USB-SA)**| Ja |   Opt |   Nein|
|**[USB (direkt)](#USB-Direct)**| Nein |    Nein  | Nein|

**Windows- und Android-Registrierungsmethoden**

| **Methode** |  **[Zurücksetzen](#Wipe)** | **[Affinität](#Affinity)**   |   **[Gesperrt](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nein|    Ja |   Nein |
|**[Geräteregistrierungs-Manager (DEM)](#DEM)**|   Nein |Nein |Nein  |

**Registrierungsmethoden für unternehmenseigene Geräte**

### BYOD
„Bring Your Own Device (eigenes Gerät nutzen).“ Benutzer installieren die Unternehmensportal-App und registrieren ihr Gerät. Beim Registrieren eines Geräts im Unternehmensportal erfolgt eine Arbeitsplatzeinbindung des Geräts. Für das Registrieren von iOS-Geräten im Unternehmensportal ist eine Apple ID erforderlich. BYOD erfordert keine zusätzliche Konfiguration für unternehmenseigene Geräte. Siehe die Schritte zum [Einrichten der Geräteverwaltung](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### Geräteregistrierungs-Manager (DEM)
Geräteregistrierungs-Manager. Der Administrator erstellt Geräteregistrierungs-Managerkonten zum Verwalten von unternehmenseigenen Geräten. Manager können anschließend das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### DEP (Device Enrollment Program)
Apple-Geräteregistrierungsprogramm. Der Administrator erstellt eine Richtlinie, die für unternehmenseigene iOS-Geräte über eine drahtlose Verbindung bereitgestellt wird, die über das Programm zur Geräteregistrierung erworben und verwaltet werden. Das Gerät wird registriert, wenn der Benutzer den iOS-Setup-Assistenten ausführt. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
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

**Verhalten für unternehmenseigene Mobilgeräte**

### Zurücksetzen
Gibt an, ob für die Registrierung des Geräts eine Zurücksetzung auf die Werkseinstellungen erforderlich ist, bei der alle Daten vom Gerät entfernt werden und das Gerät in den ursprünglichen Zustand zurückversetzt wird.
[Deaktivieren von Geräten](retire-devices-from-microsoft-intune-management.md) ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### Affinität
Gibt an, ob die Registrierungsmethode „Benutzeraffinität“ unterstützt, was heißt, dass ein Gerät einem bestimmten Benutzer zugeordnet wird. „Opt“-Geräte können mit oder ohne Benutzeraffinität registriert werden. Benutzeraffinität ist erforderlich, um Folgendes zu unterstützen:
  - MAM-Apps (Mobile Application Management, Verwaltung mobiler Anwendungen)
  - Bedingten Zugriff auf E-Mail- und Unternehmensdaten
  - Unternehmensportal-App

[Benutzeraffinität](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### Sperren
Gibt an, ob das Gerät gesperrt werden kann, um zu verhindern, dass der Benutzer die Intune-Richtlinie entfernt, was dem Entfernen des Geräts aus der Verwaltung entspricht. iOS-Geräte müssen im Modus „Überwacht“ ausgeführt werden, damit sie gesperrt werden können.
([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

## Aktivieren der Geräteregistrierung  
 Durch die Registrierung können Benutzer von ihren persönlichen Geräten aus auf Unternehmensressourcen zugreifen, und Administrator können sicherstellen, dass diese Geräte Richtlinien zum Schutz von Unternehmensressourcen einhalten. Dies ist die beste Möglichkeit, BYOD-Szenarien mit Intune zu ermöglichen. Der Administrator muss die Registrierung in der Intune-Konsole aktivieren. Dazu kann es erforderlich sein, eine Vertrauensstellung mit dem Gerät einzurichten und Benutzern Lizenzen zuzuweisen. Das Gerät wird dann in der Regel vom Benutzer durch Eingabe der Anmeldeinformationen seines Geschäfts- oder Schulkontos registriert. Das Gerät empfängt anschließend die Richtlinie von Intune und erhält Zugriff auf Ressourcen.

[Vorbereiten der Registrierung von Geräten in Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrieren aller firmeneigenen Geräte
Firmeneigene Geräte (COD) können mit der Intune-Konsole verwaltet werden. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

[Registrieren aller firmeneigenen Geräte](manage-corporate-owned-devices.md)

## Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der MDM EAS-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet.

[Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Verwalten von Windows-PCs mit Intune  
Sie können Microsoft Intune auch verwenden, um Windows-PCs mit der Windows PC-Clientsoftware zu verwalten. Mit dem Intune-Client verwaltete PCs können:

 - Software- und Hardwareinventurberichte erstellen
 - Desktopanwendung installieren (z. B. EXE- und MSI-Dateien)
 - Firewalleinstellungen

Mit der Intune-Clientsoftware verwaltete Computer können nicht selektiv zurückgesetzt oder abgekoppelt werden und können viele der Intune Verwaltungsfunktionen wie z. B. den bedingten Zugriff, VPN- und WLAN-Einstellungen oder die Bereitstellung von Zertifikaten und E-Mail-Konfigurationen nicht nutzen.

[Verwalten von Windows-PCs mit Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->


