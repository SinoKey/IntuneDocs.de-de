---
title: "Schützen von Geräten | Microsoft Intune"
description: "Erfahren Sie mehr über die Methoden, mit denen Intune Ihnen helfen kann, Ihre Geräte vor nicht autorisiertem Zugriff und anderen Bedrohungen zu schützen."
keywords: 
author: Robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 53201c36e7a210c1c62d3ed3183093ed8e63dc53


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

## Umgehung der Aktivierungssperre auf iOS-Geräten
Die Aktivierungssperre ist eine Funktion, mit der Geräte von Benutzern geschützt werden, indem die Eingabe der Apple ID und des Kennworts gefordert wird, bevor das Gerät gelöscht oder reaktiviert werden kann. Dies kann jedoch zu Problemen führen, z.B. wenn der Benutzer das Unternehmen verlässt, ohne die Sperre wieder aufzuheben. Mit [Umgehung der iOS-Aktivierungssperre](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) kann die Sperre von überwachten iOS-Geräten umgangen werden, sodass sie neu zugewiesen oder gelöscht werden können.

## Schützen von mit dem Intune-Client verwalteten Windows-PCs
Intune unterstützt auch Sicherheitsrichtlinien für Windows-PCs, die Sie nicht registrieren, sondern über die Intune-Computerclientsoftware verwalten. Erfahren Sie, wie diese Richtlinien Sie beim Schützen Ihrer Windows-PCs unterstützen: [Verwenden von Richtlinien zum Schutz von Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


