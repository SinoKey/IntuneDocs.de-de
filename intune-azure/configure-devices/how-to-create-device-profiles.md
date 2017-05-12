---
title: "Erstellen von Intune-Gerätekonfigurationsprofilen | Intune in Azure (Vorschau)"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Intune-Gerätkonfigurationsprofile erstellen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 74a905ed2ba9ec04ae14df96fcd3f6b6caf1241c
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Erstellen von Gerätekonfigurationsprofilen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
2. Wählen Sie auf dem Blatt mit der Profilliste **Profil erstellen** aus.
3. Geben Sie auf dem Blatt **Profil erstellen** Folgendes an:
    - **Name:** Geben Sie einen aussagekräftigen Namen für das neue Profil ein.
    - **Beschreibung:** Geben Sie eine Beschreibung für das Profil ein (optional).
    - **Plattform:** Wählen Sie den Plattformtyp für das Profil aus, das Sie erstellen möchten.
    - **Profiltyp:** Wählen Sie den Profiltyp aus, den Sie erstellen möchten. Die Liste der verfügbaren Typen variiert je nach der ausgewählten Plattform.
    - **Einstellungen:** In den folgenden Themen finden Sie Informationen zu den Einstellungen für die einzelnen Profiltypen:
        -  [Gerätefunktionseinstellungen](how-to-configure-device-features.md)
        -  [Einstellungen für Geräteeinschränkungen](how-to-configure-device-restrictions.md)
        -  [E-Mail-Einstellungen](how-to-configure-email-settings.md)
        -  [VPN-Einstellungen](how-to-configure-vpn-settings.md)
        -  [WLAN-Einstellungen](how-to-configure-wi-fi-settings.md)
        -  [Einstellungen für Windows 10-Editionsupgrades](how-to-configure-windows-10-edition-upgrade.md)
        -  [Zertifikateinstellungen](how-to-configure-certificates.md)
        -  [Windows Information Protection-Einstellungen](how-to-configure-windows-information-protection.md)
        -  [Education-Einstellungen](how-to-configure-education-settings.md)
        -  [Benutzerdefinierte Einstellungen](how-to-configure-custom-settings.md)

    ![Erstellen von Geräteprofilen](./media/create-device-profile.png)
4. Wählen Sie nach dem Konfigurieren der Einstellungen auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.


### <a name="next-steps"></a>Nächste Schritte
Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen mit Microsoft Intune](how-to-assign-device-profiles.md).

