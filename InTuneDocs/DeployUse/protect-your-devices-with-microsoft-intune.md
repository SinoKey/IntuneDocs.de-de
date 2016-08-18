---
title: "Schützen von Geräten | Microsoft Intune"
description: "Erfahren Sie mehr über die Methoden, mit denen Intune Ihnen helfen kann, Ihre Geräte vor nicht autorisiertem Zugriff und anderen Bedrohungen zu schützen."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Schützen von Geräten mit Microsoft Intune
Nachdem Sie die Verwaltung Ihrer Geräte über Intune eingerichtet haben, sollten Sie sicherstellen, dass sie vor nicht autorisierten Zugriffen und anderen Bedrohungen geschützt sind. Hier finden Sie einige der Funktionen von Intune, mit deren Hilfe Sie diese Ziele erreichen können.

> [!TIP]
> Dieses Thema beschreibt nicht alle Möglichkeiten, die Intune Ihnen zum Sichern Ihrer Geräte bietet. Sie können Intune-Richtlinien verwenden, um eine Vielzahl von Sicherheitseinstellungen für Ihre Geräte zu konfigurieren, wie beispielsweise Kennwörter, Verschlüsselungseinstellungen und Hardwarefunktionen wie Bluetooth und Gerätekamera. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Zurücksetzen von Kennungen, wenn Geräte für ihre Benutzer gesperrt sind
Der erste Schritt zum Schutz von Unternehmensdaten auf mobilen Geräten besteht darin, für das Gerät die Verwendung einer Kennung zu verlangen. Manchmal müssen Sie [eine Kennung zurücksetzen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) oder einem Mitarbeiter bei diesem Schritt helfen, entweder, indem Sie die Kennung entfernen oder remote eine temporäre Kennung festlegen. Sie können nach einem Verlust oder Diebstahl ein [Gerät auch remote sperren](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

## Hinzufügen einer zusätzlichen Schutzebene für Windows-Geräte
Die [mehrstufige Authentifizierung](protect-windows-devices-with-multi-factor-authentication.md) (Multi-Factor Authentication, MFA) ist eine sicherere Methode der Authentifizierung der Benutzer von Windows- und Windows Phone-Geräten im Netzwerk. Bei der mehrstufigen Authentifizierung müssen Benutzer ihre Identität zusätzlich zu Benutzername und Kennwort über einen Telefonanruf oder eine SMS bestätigen.

## Steuern der Microsoft Passport-Einstellungen auf Windows-Geräten
Intune wird auf zwei Arten in [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) integriert: Das ist eine alternative Anmeldemethode für Windows 10 und höher. Microsoft Passport for Work verwendet Active Directory oder ein Azure Active Directory-Konto, um ein Kennwort, eine Smartcard oder eine virtuelle Smartcard zu ersetzen.

## Umgehung der Aktivierungssperre auf iOS-Geräten
Die Aktivierungssperre ist eine Funktion, mit der Geräte von Benutzern geschützt werden, indem die Eingabe der Apple ID und des Kennworts gefordert wird, bevor das Gerät gelöscht oder reaktiviert werden kann. Dies kann jedoch zu Problemen führen, z. B. wenn der Benutzer das Unternehmen verlässt, ohne die Sperre wieder aufzuheben. Mit [Umgehung der iOS-Aktivierungssperre](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) kann die Sperre von überwachten iOS-Geräten umgangen werden, sodass sie neu zugewiesen oder gelöscht werden können.

## Schützen von mit dem Intune-Client verwalteten Windows-PCs
Intune unterstützt auch Sicherheitsrichtlinien für Windows-PCs, die Sie nicht registrieren, sondern über die Intune-Computerclientsoftware verwalten. Erfahren Sie, wie diese Richtlinien Sie beim Schützen Ihrer Windows-PCs unterstützen: [Verwenden von Richtlinien zum Schutz von Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Aug16_HO2-->


