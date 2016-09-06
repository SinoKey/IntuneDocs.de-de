---
title: Mehrstufige Authentifizierung mit Azure AD | Microsoft Intune
description: "Anfordern der mehrstufigen Authentifizierung in Azure AD für die Geräteregistrierung."
keywords: 
author: nbigman
manager: angerobe
ms.date: 08/17/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: e7c680c43b8c9120755ec3c652cf7ec1cbcc3472
ms.openlocfilehash: d65846b09ac33fa18db037a6a2c05963607ef53f


---

# Mehrstufige Authentifizierung für Microsoft Intune

Intune integriert die mehrstufige Authentifizierung (MFA) von Azure AD, damit Sie Ihre Unternehmensressourcen über die Geräteregistrierung sichern können. MFA erfordert zusätzlich zu Benutzernamen und Kennwörtern weitere Authentifizierungsfaktoren, wie z.B eine Bestätigung per SMS. Dies wird für Geräte unter iOS, Android, Windows 8.1 oder höher und Windows Phone 8.1 oder höher unterstützt.

> [!NOTE]
>
> In älteren Versionen von Configuration Manager (vor Release 1610) wird in der Configuration Manager-Verwaltungskonsole noch immer die MFA-Einstellung angezeigt. MFA kann nicht über die Configuration Manager-Verwaltungskonsole konfiguriert werden. Konfigurieren Sie MFA wie in diesem Thema beschrieben.

### Konfigurieren von Intune für das Anfordern der mehrstufigen Authentifizierung bei der Geräteregistrierung
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



<!--HONumber=Aug16_HO4-->


