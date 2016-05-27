---
# required metadata

title: Verwalten von firmeneigenen Geräten mit Microsoft Intune | Microsoft Intune
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
Organisations- oder firmeneigene Geräte (COD) können auf verschiedene Arten in die Verwaltung aufgenommen werden, je nach Gerät und Art des Kaufs.

## Firmeneigene iOS-Geräte
Dieser Registrierungsmethoden eignen sich für CYOD-Szenarien („Choose your own Device“), in denen die Organisation die Geräte der Benutzer erwirbt, jedoch die Verwaltung der Geräte beibehalten möchte. Wenn Ihre Organisation iOS-Geräte erworben hat, können Sie die Registrierung vorab konfigurieren, damit jedes Gerät von Moment der Inbetriebnahme durch den Benutzer verwaltet wird. Intune unterstützt die Registrierung mithilfe des [Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP)](ios-device-enrollment-program-in-microsoft-intune.md) oder des Tools Apple Configurator, das auf einem Mac-Computer für die [direkte](ios-direct-enrollment-in-microsoft-intune.md) Registrierung oder die Registrierung mit dem [Setup-Assistenten](ios-setup-assistant-enrollment-in-microsoft-intune.md) ausgeführt wird.

[Registrieren firmeneigener iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Geräteregistrierungsmanager
Mit Intune können Organisationen eine große Anzahl mobiler Geräte mit einem einzigen Benutzerkonto verwalten, dem so genannten Geräteregistrierungsmanager-Kontos. Nach dem Erstellen eines Geräteregistrierungsmanager-Kontos kann dieses Konto von einem Manager zum Registrieren von mehr als den standardmäßig zulässigen fünf Geräten verwendet werden, die ein normaler Benutzer registrieren darf. Das Registrieren von Geräten mit einem Geräteregistrierungsmanager funktioniert nur für Geräte, die nicht von einem bestimmten Benutzer verwendet. Diese Geräte eignen sich z. B. für POS- oder -Hilfsprogramm-Apps, sind aber ungeeignet für Benutzer, die Zugriff auf E-Mail oder Unternehmensressourcen benötigen.

[Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Angeben firmeneigener Geräte mit IMEI (International Mobile Equipment Identity)
Eindeutige IMEI-Nummern (International Mobile Equipment Identity) sind allgemeine Geräteeigenschaften für viele Hersteller von mobilen Geräten. Intune-Administratoren können IMEI-Nummern für Geräte importieren, die sich im Besitz des Unternehmens befinden. Wenn das Gerät von Intune verwaltet wird, kann es als firmeneigenes Gerät gekennzeichnet und mit der entsprechenden Richtlinie versehen werden.

[Angeben firmeneigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


