---
# required metadata

title: Schützen von Geräten | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Schützen von Geräten mit Microsoft Intune
Nachdem Sie die Verwaltung Ihrer Geräte über Intune eingerichtet haben, sollten Sie sicherstellen, dass sie vor nicht autorisierten Zugriffen und anderen Bedrohungen geschützt sind. Hier finden Sie einige der Funktionen von Intune, mit deren Hilfe Sie diese Ziele erreichen können.

> [!TIP]
> Dieses Thema beschreibt nicht alle Möglichkeiten, die Intune Ihnen zum Sichern Ihrer Geräte bietet. Sie können Intune-Richtlinien verwenden, um eine Vielzahl von Sicherheitseinstellungen für Ihre Geräte zu konfigurieren, wie beispielsweise Kennwörter, Verschlüsselungseinstellungen und Hardwarefunktionen wie Bluetooth und Gerätekamera. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Zurücksetzen von Kennungen, wenn Geräte für ihre Benutzer gesperrt sind
Da der erste Schritt zum Schutz von Unternehmensdaten auf mobilen Geräten darin besteht, eine Kennung abzufragen, damit das Gerät verwendet werden kann, müssen Sie mitunter eine [Kennung zurücksetzen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) oder einem Mitarbeiter hierbei helfen, entweder indem Sie die Kennung entfernen oder remote eine vorübergehende Kennung festlegen. Sie können nach einem Verlust oder Diebstahl ein [Gerät auch remote sperren](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

## Hinzufügen einer zusätzlichen Schutzebene für Windows-Geräte
Die [mehrstufige Authentifizierung](protect-windows-devices-with-multi-factor-authentication.md) (Multi-Factor Authentication, MFA) ist eine sicherere Methode der Authentifizierung der Benutzer von Windows- und Windows Phone-Geräten im Netzwerk.  Bei der mehrstufigen Authentifizierung müssen Benutzer ihre Identität zusätzlich zu Benutzername und Kennwort über einen Telefonanruf oder eine SMS bestätigen.

## Steuern der Microsoft Passport-Einstellungen auf Windows-Geräten
Intune ermöglicht die Integration in [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dies ist eine alternative Anmeldemethode für Windows 10 und höher, die Active Directory oder ein Azure Active Directory-Konto verwendet, um ein Kennwort, eine Smartcard oder eine virtuelle Smartcard zu ersetzen.

## Schützen von mit dem Intune-Client verwalteten Windows-PCs
Intune unterstützt auch Sicherheitsrichtlinien für Windows-PCs, die Sie nicht registrieren, sondern über die Intune-Computerclientsoftware verwalten. Erfahren Sie, wie diese Richtlinien Sie beim Schützen Ihrer Windows-PCs unterstützen: [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Verwenden von Richtlinien zum Schützen von Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird).


<!--HONumber=May16_HO2-->


