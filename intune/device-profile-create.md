---
title: "Erstellen von Intune-Gerätekonfigurationsprofilen"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie Intune-Gerätekonfigurationsprofile erstellen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5c23d33bde16ada61b6164bb560a30b81cab0020
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Erstellen von Gerätekonfigurationsprofilen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
2. Wählen Sie auf dem Blatt mit der Profilliste **Profil erstellen** aus.
3. Geben Sie auf dem Blatt **Profil erstellen** folgende Elemente an:
    - **Name:** Geben Sie einen aussagekräftigen Namen für das neue Profil ein.
    - **Beschreibung:** Geben Sie eine Beschreibung für das Profil ein (optional).
    - **Plattform:** Wählen Sie den Plattformtyp für das Profil aus, das Sie erstellen möchten.
    - **Profiltyp:** Wählen Sie den Profiltyp aus, den Sie erstellen möchten. Die Liste der verfügbaren Typen variiert je nach der ausgewählten Plattform.
    - **Einstellungen:** In den folgenden Themen finden Sie Informationen zu den Einstellungen für die einzelnen Profiltypen:
        -  [Gerätefunktionseinstellungen](device-features-configure.md)
        -  [Einstellungen für Geräteeinschränkungen](device-restrictions-configure.md)
        -  [E-Mail-Einstellungen](email-settings-configure.md)
        -  [VPN-Einstellungen](vpn-settings-configure.md)
        -  [WLAN-Einstellungen](wi-fi-settings-configure.md)
        -  [Einstellungen für Windows 10-Editionsupgrades](edition-upgrade-configure-windows-10.md)
        -  [Zertifikateinstellungen](certificates-configure.md)
        -  [Windows Information Protection-Einstellungen](windows-information-protection-configure.md)
        -  [Education-Einstellungen](education-settings-configure.md)
        -  [Benutzerdefinierte Einstellungen](custom-settings-configure.md)

    ![Erstellen von Geräteprofilen](./media/create-device-profile.png)
4. Wählen Sie nach dem Konfigurieren der Einstellungen auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.


### <a name="next-steps"></a>Nächste Schritte
Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen mit Microsoft Intune](device-profile-assign.md).
