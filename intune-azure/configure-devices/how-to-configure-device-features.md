---
title: "Konfigurieren der Einstellungen für Gerätefunktionen in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune Funktionen auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: fddd4963ceea09b37ad4d8c739f437dbcf3b053e
ms.lasthandoff: 04/26/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Konfigurieren der Einstellungen für Gerätefunktionen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mit Geräteeinschränkungen können Sie Funktionen auf iOS- und macOS-Geräten wie AirPrint, Benachrichtigungen und freigegebene Gerätekonfigurationen steuern.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Gerätefunktionsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Gerätefunktionsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie die Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für Gerätefunktionen auswählen:
    - **iOS**
    - **macOS**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Gerätefunktionen** aus. 
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [AirPrint settings for iOS and MacOS](air-print-settings-for-ios-and-macos.md) (AirPrint-Einstellungen für iOS- und macOS-Geräte)
     - [AirPlay settings for iOS](airplay-settings-for-ios-devices.md) (AirPlay-Einstellungen für iOS-Geräte)
    - [Home screen layout settings for iOS](home-screen-settings-for-ios.md) (Einstellungen des Startbildschirmlayouts für iOS-Geräte)
    - [App notification settings for iOS](app-notification-settings-for-ios.md) (App-Benachrichtigungseinstellungen für iOS-Geräte)
    - [Shared device configuration settings for iOS](shared-device-settings-for-ios.md) (Konfigurationseinstellungen für freigegebene iOS-Geräte)

8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.




