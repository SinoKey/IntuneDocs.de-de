---
title: Bereitstellen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie | Microsoft-Dokumentation
description: Stellen Sie Skycure-Apps, die Microsoft Authenticator-App und die iOS-Konfigurationsrichtlinie an die klassische Intune-Konsole bereit.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19c8ca7bbfe19649585d63ce2c0c96a8f57b3739
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Bereitstellen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Vorbereitung

-   Die unten beschriebenen Schritte müssen in der [klassischen Intune-Konsole](https://manage.microsoft.com/) durchgeführt werden.

-   Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der Skycure-Verwaltungskonsole konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich in die klassische Intune-Konsole einloggen.

-   Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:

    -   [Bereitstellen von Apps in Microsoft Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Bereitstellen von iOS-Apps mit Konfigurationsrichtlinien](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>So stellen Sie Skycure-Apps, die Microsoft Authenticator-App und die iOS-App-Konfigurationsrichtlinie bereit

1.  Wählen Sie in der klassischen Intune-Konsole **Apps** &gt; **Apps** zum Anzeigen der Liste von Apps, die Sie verwalten können.

2.  Wählen Sie die folgenden Apps aus:

    a.  Microsoft Authenticator

    b.  Skycure-App für Android

    c.  Skycure-App für iOS

       ![Klassische Intune-Konsole, alle bereitzustellenden Apps](../media/mtp/skycure-deploy-app-1.png)

3.  Wählen Sie **Manage Deployments** (Bereitstellungen verwalten), wählen Sie die Azure AD-Sicherheitsgruppe mit den Skycure-Benutzern aus, und klicken Sie dann auf **Weiter**.

4.  Wählen Sie auf der Seite **Bereitstellungsaktion** in der Dropdownliste **Genehmigung** die Option **Erforderliche Installation** aus, und klicken Sie dann auf **Weiter**.

    ![Klassische Intune-Konsole, Bereitstellungsaktion](../media/mtp/skycure-deploy-app-2.png)

5.  Wählen Sie auf der Seite **VPN profile** (VPN-Profil) in der Dropdownliste **VPN-Richtlinie** die Option **None** (Keine) aus, und klicken Sie dann auf **Weiter**.

6.  Wählen Sie auf der Seite **Konfiguration mobiler Apps** aus der Dropdownliste **Richtlinie für die App-Konfiguration** die zuvor erstellte iOS-App-Konfigurationsrichtlinie aus, und klicken Sie dann auf **Fertigstellen**.

    ![Klassische Intune-Konsole, Mobile App-Konfiguration](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Nächste Schritte

[Einrichten der Skycure-Integration in Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
