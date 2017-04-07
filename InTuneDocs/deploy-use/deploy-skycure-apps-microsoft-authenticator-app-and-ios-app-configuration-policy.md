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
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 9f09a070ec120064bdd64bfb05a39ec9e484606c
ms.lasthandoff: 03/21/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Bereitstellen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Vorbereitung

-   Die unten beschriebenen Schritte müssen in der [klassischen Intune-Konsole](https://manage.microsoft.com/) abgeschlossen werden.

-   Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der Skycure-Verwaltungskonsole konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich in die klassische Intune-Konsole einloggen.

-   Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:

    -   [Bereitstellen von Apps in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Bereitstellen von iOS-Apps mit Konfigurationsrichtlinien](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

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

[Einrichten der Skycure-Integration mit Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

