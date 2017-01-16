---
title: Mehrstufige Authentifizierung mit Azure AD | Microsoft-Dokumentation
description: "Anfordern der mehrstufigen Authentifizierung in Azure AD für die Geräteregistrierung."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Mehrstufige Authentifizierung für Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune integriert die mehrstufige Authentifizierung (MFA) von Azure AD, damit Sie Ihre Unternehmensressourcen über die Geräteregistrierung sichern können. MFA erfordert zusätzlich zu Benutzernamen und Kennwörtern weitere Authentifizierungsfaktoren, wie z.B eine Bestätigung per SMS. Dies wird für Geräte unter iOS, Android, Windows 8.1 oder höher und Windows Phone 8.1 oder höher unterstützt.

> [!NOTE]
>
> Dies ist die neue Oberfläche für die MFA in Intune. Die ältere Oberfläche, von der Kunden gerade migriert werden, wird unter [Schützen von Windows-Geräten mit mehrstufiger Authentifizierung](protect-windows-devices-with-multi-factor-authentication.md) beschrieben.
>
> In älteren Versionen von Configuration Manager (vor Release 1610) wird in der Configuration Manager-Verwaltungskonsole noch immer die MFA-Einstellung angezeigt. MFA kann nicht über die Configuration Manager-Verwaltungskonsole konfiguriert werden. Konfigurieren Sie MFA wie in diesem Thema beschrieben.

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurieren von Intune für das Anfordern der mehrstufigen Authentifizierung bei der Geräteregistrierung
Um MFA bei der Registrierung des Geräts anzufordern, gehen Sie folgendermaßen vor:

1. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Microsoft Azure-Portal](https://manage.windowsazure.com) an.
2. Wählen Sie Ihren Mandanten.
2. Wählen Sie die Registerkarte **Anwendungen**. Sie sehen eine Liste der Dienste, für die Sie Azure AD-Sicherheitsfeatures konfigurieren können.
3. Wählen Sie **Microsoft Intune-Registrierung**.
4. Wählen Sie **Konfigurieren** aus. 
5. Unter **Mehrstufige Authentifizierung und standortbasierte Zugriffsregeln** haben Sie folgende Möglichkeiten:
    
    -  Aktivieren der Zugriffsregeln
    -  Auswählen, ob die Regeln für alle Benutzer oder für bestimmte Azure AD-Sicherheitsgruppen gelten sollen
    -  Anfordern der mehrstufigen Authentifizierung für die Registrierung aller Geräte
    -  Anfordern der mehrstufigen Authentifizierung für die Registrierung, wenn sich das Gerät nicht am Arbeitsplatz befindet
    -  Wählen Sie **Zugriff auf Unternehmensressourcen blockieren**, um die Registrierung eines Geräts zu verhindern, wenn es nicht mit dem Unternehmensnetzwerk verbunden ist. 
4. Sie können auch auf den Link klicken, um **Ihre Firmennetzwerkadresse zu definieren oder zu bearbeiten** und die Anforderungen der Geräteregistrierung an die Netzwerkkonnektivität zu konfigurieren.

> [!IMPORTANT]
> 
> Konfigurieren Sie keine **gerätebasierten Zugriffsregeln** für die Microsoft Intune-Registrierung.



<!--HONumber=Dec16_HO3-->


