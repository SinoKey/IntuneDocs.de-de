---
# required metadata

title: Verwalten unternehmenseigener Geräte | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrieren firmeneigener Geräten bei Microsoft Intune
Organisations- bzw. unternehmenseigene Geräte können je nach Gerät und Art des Kaufs sowie den geschäftlichen Anforderungen auf verschiedene Arten in die Verwaltung aufgenommen werden.

## Firmeneigene iOS-Geräte
Dieser Registrierungsmethoden eignen sich für CYOD-Szenarien („Choose your own Device“), in denen die Organisation die Geräte der Benutzer erwirbt, jedoch die Verwaltung der Geräte beibehalten möchte. Wenn Ihre Organisation iOS-Geräte erworben hat, können Sie die Registrierung vorab konfigurieren, damit jedes Gerät von Moment der Inbetriebnahme durch den Benutzer verwaltet wird. Intune unterstützt die Registrierung mithilfe des [Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP)](ios-device-enrollment-program-in-microsoft-intune.md) oder des Tools Apple Configurator, das auf einem Mac-Computer für die [direkte](ios-direct-enrollment-in-microsoft-intune.md) Registrierung oder die Registrierung mit dem [Setup-Assistenten](ios-setup-assistant-enrollment-in-microsoft-intune.md) ausgeführt wird.

[Registrieren firmeneigener iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Geräteregistrierungsmanager
Mit Intune können Organisationen eine große Anzahl mobiler Geräte mit einem einzigen Benutzerkonto verwalten, dem so genannten Geräteregistrierungsmanager-Kontos. Nach dem Erstellen eines Geräteregistrierungsmanager-Kontos kann dieses Konto von einem Manager zum Registrieren von mehr als den standardmäßig zulässigen fünf Geräten verwendet werden, die ein normaler Benutzer registrieren darf. Das Registrieren von Geräten mit einem Geräteregistrierungsmanager funktioniert nur für Geräte, die nicht von einem bestimmten Benutzer verwendet. Diese Geräte eignen sich z. B. für POS- oder -Hilfsprogramm-Apps, sind aber ungeeignet für Benutzer, die Zugriff auf E-Mail oder Unternehmensressourcen benötigen.

[Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## International Mobile Equipment Identity (IMEI)
Eindeutige IMEI-Nummern (International Mobile Equipment Identity) sind allgemeine Geräteeigenschaften für viele Hersteller von mobilen Geräten. Intune-Administratoren können IMEI-Nummern für Geräte importieren, die sich im Besitz des Unternehmens befinden. Wenn das Gerät von Intune verwaltet wird, kann es als firmeneigenes Gerät gekennzeichnet und mit der entsprechenden Richtlinie versehen werden.

[Angeben firmeneigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Übersicht über Registrierungsmethoden für unternehmenseigene Geräte

Die folgende Tabelle zeigt Registrierungsmethoden für unternehmenseigene Geräte samt ihren Vorteilen.

**iOS-Registrierungsmethoden**

| **Methode** |  **[Zurücksetzen](#Reset)** |   **[Affinität](#Affinity)**   |   **[Gesperrt](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nein|    Ja |   Nein |
|**[Geräteregistrierungs-Manager (DEM)](#DEM)**|   Nein |Nein |Nein  |
|**[DEP (Device Enrollment Program)](#DEP)**|   Ja |   Opt |   Opt|
|**[USB (Setup-Assistent)](#USB-SA)**| Ja |   Opt |   Nein|
|**[USB (direkt)](#USB-Direct)**| Nein |    Nein  | Nein|

**Windows- und Android-Registrierungsmethoden**

| **Methode** |  **[Zurücksetzen](#Wipe)** | **[Benutzer](#User)**   |   **[Gesperrt](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nein|    Ja |   Nein |
|**[Geräteregistrierungs-Manager (DEM)](#DEM)**|   Nein |Nein |Nein  |

**Registrierungsmethoden für unternehmenseigene Geräte**

### BYOD
„Bring Your Own Device (eigenes Gerät nutzen).“ Benutzer installieren die Unternehmensportal-App und registrieren ihr Gerät. Beim Registrieren eines Geräts im Unternehmensportal erfolgt eine Arbeitsplatzeinbindung des Geräts. Für das Registrieren von iOS-Geräten im Unternehmensportal ist eine Apple ID erforderlich. BYOD erfordert keine zusätzliche Konfiguration für unternehmenseigene Geräte. Siehe die Schritte zum [Einrichten der Geräteverwaltung](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### Geräteregistrierungs-Manager (DEM)
Geräteregistrierungs-Manager. Der Administrator erstellt DEM-Konten. Manager können anschließend das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### DEP (Device Enrollment Program)
Apple-Geräteregistrierungsprogramm. Der Administrator erstellt eine Richtlinie, die auf iOS-Geräten drahtlos bereitgestellt wird, die über das Geräteregistrierungsprogramm erworben wurden und verwaltet werden. Das Gerät wird registriert, wenn der Benutzer den iOS-Setup-Assistenten ausführt. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Gesperrte Registrierung
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über das [Geräteregistrierungsprogramm](ios-device-enrollment-program-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### USB (Setup-Assistent)
USB-Verbindung, Registrierung mit dem Setup-Assistenten. Der Administrator erstellt eine Intune-Richtlinie und exportiert sie in Apple Configurator. Über USB angeschlossene Geräte werden mit der Intune-Richtlinie vorbereitet. Der Administrator muss jedes Gerät manuell registrieren. Benutzer erhalten ihre Geräte und führen den Setup-Assistenten aus, um ihr Gerät zu registrieren. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  - Bedingter Zugriff
  - Erkennung von Jailbreaks
  - Mobile Anwendungsverwaltung

Erfahren Sie mehr über die [Registrierung über den Setup-Assistenten mit Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### USB (direkt)
Direkte Registrierung. Der Administrator erstellt eine Intune-Richtlinie und exportiert sie in Apple Configurator. Über USB angeschlossene Geräte werden direkt registriert, ohne dass ein Zurücksetzen auf Werkseinstellungen erforderlich ist. Der Administrator muss jedes Gerät manuell registrieren. Geräte werden als benutzerlose Geräte verwaltet. Sie werden nicht gesperrt oder überwacht und unterstützen nicht den bedingten Zugriff, die Erkennung von Jailbreaks und die Verwaltung mobiler Geräte. Erfahren Sie mehr über die [direkte Registrierung mit Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

**Verhalten für unternehmenseigene Mobilgeräte**

### Zurücksetzen
Gibt an, ob für die Registrierung des Geräts eine Zurücksetzung auf die Werkseinstellungen erforderlich ist, bei der alle Daten vom Gerät entfernt werden und das Gerät in den ursprünglichen Zustand zurückversetzt wird.
([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### Affinität
Gibt an, ob die Registrierungsmethode „Benutzeraffinität“ unterstützt, was heißt, dass ein Gerät einem bestimmten Benutzer zugeordnet wird. „Opt“-Geräte können mit oder ohne Benutzeraffinität registriert werden. Benutzeraffinität ist erforderlich, um Folgendes zu unterstützen:
  - MAM-Apps (Mobile Application Management, Verwaltung mobiler Anwendungen)
  - Bedingten Zugriff auf E-Mail- und Unternehmensdaten
  - Unternehmensportal-App

([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))

### Sperren
Gibt an, ob das Gerät gesperrt werden kann, um zu verhindern, dass der Benutzer die Intune-Richtlinie entfernt, was dem Entfernen des Geräts aus der Verwaltung entspricht. iOS-Geräte müssen im Modus „Überwacht“ ausgeführt werden, damit sie gesperrt werden können.
([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods)) ([Zurück zur Tabelle](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO3-->


