---
title: "Auswählen, wie Windows-Geräte in Intune registriert werden"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie die Registrierung von Windows-Geräten in Microsoft Intune einrichten."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bdbc7ca68995e23295cf099ce73dfdcaeba37c
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Registrieren von iOS-Geräten in Intune

Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads und iPhones, was Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps ermöglicht.

Als Intune-Administrator können Sie die Registrierung für iOS-Geräte aktivieren. Sie können Benutzern erlauben, persönliche Geräte zu registrieren, was auch als BYOD-Registrierung („bring your own device“) bekannt ist. Sie können auch die Registrierung von unternehmenseigenen Geräten aktivieren.

## <a name="prerequisites-for-ios-enrollment"></a>Voraussetzungen für die iOS-Registrierung
Bevor Sie iOS-Geräte aktivieren können, schließen Sie die folgenden Schritte ab:
- [Einrichten von Intune:](setup-steps.md) Mit diesen Schritten wird Ihre Intune-Infrastruktur eingerichtet. Besonders für die Geräteregistrierung ist es erforderlich, dass Sie [die MDM-Autorität festlegen](mdm-authority-set.md).
- [Abrufen eines Apple-MDM-Push-Zertifikats:](apple-mdm-push-certificate-get.md) Apple benötigt ein Zertifikat, um die Verwaltung von iOS- und macOS-Geräten zu aktivieren.

Sobald diese Voraussetzungen abgeschlossen sind, können Benutzer die Unternehmensportal-App zur Registrierung ihrer persönlichen iOS-Geräte installieren, oder der Administrator kann die Verwaltung von firmeneigenen iOS-Geräten einrichten. Administratoren können auch [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) zuweisen, die viele Geräte mit einem einzelnen Verwaltungskonto registrieren können. Intune unterstützt die folgenden Methoden für die Registrierung unternehmenseigener iOS-Geräte:

## <a name="device-enrollment-program"></a>Geräteregistrierungsprogramm
Organisationen können iOS-Geräte über das Apple Device Enrollment Program (DEP) erwerben. Mit DEP können Sie drahtlos (Over The Air) ein Registrierungsprofil bereitstellen, das Geräte für die Verwaltung registriert. Erfahren Sie mehr über das [Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager ist Programm zum Kauf von Geräten und deren Registrierung für Schulen. Wie bei DEP können Sie ein Profil zum Registrieren von Geräten in der Verwaltung bereitstellen. Erfahren Sie mehr über [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Sie können iOS-Geräte mit Apple Configurator auf einem Mac-Computer registrieren. Um Geräte vorzubereiten, verbinden Sie sie über USB, und installieren Sie das Registrierungsprogramm. Sie können Geräte mit Apple Configurator auf zwei Arten registrieren:
- Registrierung per Setup-Assistent: Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück, bereitet es auf die Ausführung des Setup-Assistenten vor und installiert die Unternehmensrichtlinien für den neuen Benutzer des Geräts.
- Direkte Registrierung: Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode eignet sich für Geräte ohne Benutzeraffinität.

Erfahren Sie mehr über die [Apple Configurator-Registrierung](apple-configurator-setup-assistant-enroll-ios.md).
