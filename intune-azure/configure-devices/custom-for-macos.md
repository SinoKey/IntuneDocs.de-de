---
title: "Benutzerdefinierte Intune-Einstellungen für macOS-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten macOS-Profil verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 113572430f0ef82c9a6fa533e3d6fc17b86119cb


---

# <a name="custom-settings-for-macos-devices-in-intune-azure-preview"></a>Benutzerdefinierte Einstellungen für macOS-Geräte in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie das benutzerdefinierte macOS-Profil von Microsoft Intune, um Einstellungen, die Sie mit dem [Apple Configurator-Tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) erstellt haben, auf macOS-Geräten bereitzustellen. Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren. Sie können dieses Konfigurationsprofil anschließend in ein benutzerdefiniertes macOS-Profil von Intune importieren und die Einstellungen Benutzern und Geräten in Ihrer Organisation zuweisen.

Diese Funktion ermöglicht die Bereitstellung von macOS-Einstellungen, die nicht mit anderen Intune-Profiltypen konfigurierbar sind.


1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](how-to-configure-custom-settings.md).
2. Geben Sie auf dem Blatt **Profil erstellen** Folgendes an:

- **Name des benutzerdefinierten Konfigurationsprofils:** Geben Sie einen Namen für die Richtlinie an, der auf dem Gerät und in Intune-Status angezeigt wird.
- **Konfigurationsprofildatei:** Suchen Sie das mit Apple Configurator erstellte Konfigurationsprofil.
Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der macOS-Version auf den Geräten kompatibel sind, für die Sie die benutzerdefinierte macOS-Richtlinie bereitstellen. Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie auf der [Apple Developer-Website](https://developer.apple.com/) nach der **Referenz zu Konfigurationsprofilen** und der **Referenz zum Protokoll für die Verwaltung mobiler Geräte**.

Die importierte Datei wird im Bereich **Dateiinhalt** des Blatts angezeigt.



<!--HONumber=Feb17_HO1-->


