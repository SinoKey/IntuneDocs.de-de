---
title: "Benutzerdefinierte Einstellungen für macOS-Geräte"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten macOS-Profil verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 84902bb0e7ea67b388debd8bd7992d396d981a7b
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Benutzerdefinierte Einstellungen für macOS-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie das benutzerdefinierte macOS-Profil von Microsoft Intune, um Einstellungen, die Sie mit dem [Apple Configurator-Tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) erstellt haben, auf macOS-Geräten bereitzustellen. Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren. Sie können dieses Konfigurationsprofil anschließend in ein benutzerdefiniertes macOS-Profil von Intune importieren und die Einstellungen Benutzern und Geräten in Ihrer Organisation zuweisen.

Diese Funktion ermöglicht die Bereitstellung von macOS-Einstellungen, die nicht mit anderen Intune-Profiltypen konfigurierbar sind.


1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](how-to-configure-custom-settings.md).
2. Geben Sie auf dem Blatt **Profil erstellen** Folgendes an:

- **Name des benutzerdefinierten Konfigurationsprofils:** Geben Sie einen Namen für die Richtlinie an, der auf dem Gerät und in Intune-Status angezeigt wird.
- **Konfigurationsprofildatei:** Suchen Sie das mit Apple Configurator erstellte Konfigurationsprofil.
Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der macOS-Version auf den Geräten kompatibel sind, für die Sie die benutzerdefinierte macOS-Richtlinie bereitstellen. Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie auf der [Apple Developer-Website](https://developer.apple.com/) nach der **Referenz zu Konfigurationsprofilen** und der **Referenz zum Protokoll für die Verwaltung mobiler Geräte**.

Die importierte Datei wird im Bereich **Dateiinhalt** des Blatts angezeigt.

