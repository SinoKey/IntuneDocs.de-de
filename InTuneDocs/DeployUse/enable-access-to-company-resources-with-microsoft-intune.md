---
title: Aktivieren des Zugriffs auf Unternehmensressourcen | Microsoft Intune
description: "Die WLAN-, VPN- und E-Mail-Profile greifen ineinander, um Ihre Benutzer beim Zugriff auf die Dateien und Ressourcen, die sie benötigen, zu unterstützen."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 9448b5fd9121a3bce33b947c79fee7290d2a43f9


---

# Aktivieren des Zugriffs auf Unternehmensressourcen mit Microsoft Intune
Die WLAN-, VPN- und E-Mail-Profile von Microsoft Intune greifen ineinander, um Ihre Benutzer beim Zugriff auf die Dateien und Ressourcen, die sie für ihre Arbeit benötigen, zu unterstützen, unabhängig davon, wo sie gespeichert sind. Dieser Zugriff wird mithilfe von Zertifikatprofilen gesichert.

## [WLAN-Profile](wi-fi-connections-in-microsoft-intune.md) und unterstützte Plattformen

Bereitstellen von Einstellungen für drahtlose Netzwerke für Ihre Benutzer. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit dem Unternehmensnetzwerk.
#### Unterstützte Plattformen

|Windows 8.1 und höher|Windows Phone 8.1 und höher|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Ja (Sie können ein Windows-WLAN-Profil importieren)|Ja (Sie können OMA-URI konfigurieren) |Ja|Ja|Ja|

## [VPN-Profile](vpn-connections-in-microsoft-intune.md) und unterstützte Plattformen
Stellen Einstellungen für ein virtuelles privates Netzwerk (VPN) für Benutzer bereit. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit Ressourcen im Unternehmensnetzwerk.

|Windows 8.1 und höher|Windows Phone 8.1 und höher|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Ja|Ja|Ja|Ja|Ja|

## [E-Mail-Profile](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) und unterstützte Plattformen
Erstellen, Bereitstellen und Überwachen von nativen E-Mail-Clienteinstellungen auf den Geräten in Ihrer Organisation.

|Windows 8.1 und höher|Windows Phone 8.1 und höher|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Nein|Ja|Ja|Nein|Ja|
> [!NOTE]
> [Dieser Beitrag im Intune-Teamblog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) enthält Informationen zum Konfigurieren von Windows Phone 8.1-WLAN-Profilen mithilfe von OMA-URI.

## [Zertifikatprofile](secure-resource-access-with-certificate-profiles.md) und unterstützte Plattformen
Ermöglichen den sicheren Zugriff auf Unternehmensressourcen einschließlich Drahtlosnetzwerken und VPN-Verbindungen.

|Windows 8.1 und höher|Windows Phone 8.1 und höher|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Ja|Ja|Ja|Ja|Ja|



<!--HONumber=Jul16_HO3-->


