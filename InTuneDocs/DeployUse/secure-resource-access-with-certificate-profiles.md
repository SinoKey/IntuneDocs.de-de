---
title: "Zertifikatsprofile für den Ressourcenzugriff | Microsoft Intune"
description: "Sichern von VPN-, WLAN- und E-Mail-Zugriff mit einem Zertifikat, das auf jedem Benutzergerät installiert ist."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 98c32f924b60734d9a592ebdd7e00429dc32af26


---

# Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune
Wenn Sie den Zugriff auf Unternehmensressourcen über VPN, WLAN oder E-Mail-Profile aktivieren, können Sie diesen Zugriff mit einem auf jedem Benutzergerät installierten Zertifikat absichern. Gehen Sie dazu folgendermaßen vor:

1. Stellen Sie sicher, dass die richtige Zertifikatinfrastruktur eingerichtet ist, wie unter [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) oder [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md) beschrieben.

2. Installieren Sie ein Stammzertifikat (oder eine Zwischenzertifizierungsstelle) auf jedem Gerät, damit das Gerät die Rechtmäßigkeit Ihrer Zertifizierungsstelle erkennt. Dazu mit erstellen Sie ein **vertrauenswürdiges Zertifikatprofil** und stellen es bereit. Wenn Sie dieses Profil bereitstellen, wird das Stammzertifikat von den Geräten, die Sie mit Intune verwalten, angefordert und empfangen. Sie müssen für jede Plattform ein eigenes Profil erstellen. Das **vertrauenswürdige Zertifikatprofil** ist für folgende Plattformen verfügbar:
 -  iOS 7.1 und höher
 -  Mac OS X 10.9 und höher
 -  Android 4,0 und höher
 -  Windows 8.1 und höher
 -  Windows Phone 8.1 und höher

3. Im nächsten Schritt richten Sie jedes Gerät so ein, dass es ein Zertifikat für die Authentifizierung des E-Mail-, VPN- und WLAN-Zugriffs anfordert, wie unter [Konfigurieren von Intune-Zertifikatprofilen](configure-intune-certificate-profiles.md) beschrieben. Sie können ein **PKCS #12-Zertifikatprofil (.PFX)** oder ein **SCEP-Zertifikatprofil ** für Geräte auf diesen Plattformen erstellen und bereitstellen:

-  Android 4,0 und höher
-  iOS 7.1 und höher
-  Windows 10 (Desktop und Mobile) und höher

Verwenden Sie das **SCEP-Zertifikatprofil** für diese Plattformen:
-   Mac OS X 10.9 und höher
-   Windows Phone 8.1 und höher

Sie müssen für jede Plattform ein eigenes Profil erstellen. Nachdem Sie das Profil erstellt haben, ordnen Sie es dem bereits erstellten **vertrauenswürdigen Stammzertifikatprofil** zu.

> [!NOTE]           
> -    Wenn Sie über keine Unternehmenszertifizierungsstelle verfügen, müssen Sie eine erstellen.
>- Wenn Sie sich basierend auf Ihren Geräteplattformen entschließen, das Simple Certificate Enrollment-Protokoll (SCEP) zu verwenden, müssen Sie auch einen NDES-Server (Network Device Enrollment Service, Registrierungsdienst für Netzwerkgeräte) konfigurieren.
>-  Ganz gleich, ob Sie SCEP- oder .PFX-Profile verwenden möchten, müssen Sie den Microsoft Intune-Zertifikatconnector herunterladen und konfigurieren.
> Alle diese Konfigurationen werden in [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) und [Konfigurieren der Zertifikatinfrastruktur](configure-certificate-infrastructure-for-pfx.md) beschrieben.

### Nächste Schritte
- [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurieren von Intune-Zertifikatprofilen](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO4-->


