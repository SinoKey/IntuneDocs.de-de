---
title: Konfigurieren von Intune-WLAN-Einstellungen | Intune in Azure (Vorschau) | Microsoft Docs
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune WLAN-Einstellungen auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: bc7d94f70c65f06d10fffa04788072e504a2d071
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>So konfigurieren Sie WLAN-Einstellungen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie WLAN-Profile in Microsoft Intune, um Benutzern und Geräten in Ihrer Organisation Einstellungen für Drahtlosnetzwerke bereitzustellen. Wenn Sie ein WLAN-Profil bereitstellen, erhalten Ihre Benutzer Zugriff auf Ihr Unternehmens-WLAN, ohne es selbst konfigurieren zu müssen.

Beispiel: Sie installieren ein neues WLAN mit dem Namen „Contoso Wi-Fi“ und möchten alle iOS-Geräte so einrichten, dass sie eine Verbindung mit diesem Netzwerk herstellen können. Gehen Sie dazu folgendermaßen vor:

1. Erstellen Sie ein WLAN-Profil mit den Einstellungen, die zum Verbinden mit dem Drahtlosnetzwerk „Contoso Wi-Fi“ erforderlich sind.
2. Weisen Sie das Profil einer Gruppe zu, die alle Benutzer von iOS-Geräten enthält.
3. Auf den Geräten der Benutzer erscheint das Netzwerk „Contoso Wi-Fi“ in der Liste der Drahtlosnetzwerke, und es kann bequem eine Verbindung mit diesem Netzwerk hergestellt werden.

WLAN-Profile unterstützen folgende Geräteplattformen:

- Android 4 und höher
- iOS 8.0 und höher
- macOS (Mac OS X 10.9 und höher)

Auf Geräten mit Windows 8.1, Windows 10 und Windows 10 Mobile können Sie eine WLAN-Konfiguration importieren, die zuvor von einem anderen Gerät exportiert wurde.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von WLAN-Profilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Erstellen eines Geräteprofils mit WLAN-Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das WLAN-Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie WLAN-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die WLAN-Einstellungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows 8.1 und höher (Profil importieren)**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Basis-WLAN** oder **Unternehmens-WLAN** aus.
    >[!TIP]
    >Mit **Basis-WLAN** können Sie grundlegende Eigenschaften wie den Netzwerknamen und die SSID angeben. Mit **Unternehmens-WLAN** können Sie detailliertere Informationen angeben, z.B. das Extensible Authentication Protocol (EAP), sofern dieses in Ihrem WLAN verwendet wird. Mit **WLAN (Import)** (für Windows 8.1 und Windows 10) können Sie WLAN-Einstellungen als XML-Datei importieren, die Sie zuvor von einem anderen Gerät exportiert haben.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](wi-fi-for-android.md)
    - [Einstellungen für iOS](wi-fi-for-ios.md)
    - [Einstellungen für macOS](wi-fi-for-macos.md)
    - [Einstellungen für Windows Phone 8.1](wi-fi-import-for-windows-8-1.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.


