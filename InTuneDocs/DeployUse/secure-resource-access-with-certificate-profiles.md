---
title: Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
author: Nbigman
---
# Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen in Microsoft Intune
Wenn Sie Zugriff auf Unternehmensressourcen über ein VPN, Wi-Fi oder e-Mail-Profile aktivieren, müssen Sie die Option zum Sichern, dass der Zugriff mit einem Zertifikat auf jedem Benutzergerät installiert. So funktioniert es:

 
1.   Zuerst installieren Sie ein Stammzertifikat (oder einer Zwischenzertifizierungsstelle) auf jedem Gerät, damit das Gerät die Legitimität von Ihrer Zertifizierungsstelle erkennt. Dazu mit erstellen und Bereitstellen einer **Profil des vertrauenswürdigen Zertifikats**. Wenn Sie dieses Profil bereitstellen, die Geräte, die Sie mit Intune verwalten anfordern und erhalten das Stammzertifizierungsstellen-Zertifikat. Die **Profil des vertrauenswürdigen Zertifikats** für Geräte unter iOS 7.1 und höher, Mac OS X 10.9 und höher, Android 4.0 und höher und Windows Phone 8.1 und höher verfügbar ist. Sie müssen für jede Plattform ein eigenes Profil erstellen.

2.   Im nächsten Schritt stellen Sie jedes Gerät ein Zertifikat für die Authentifizierung von e-Mail, VPN, anzufordern und Wi-Fi-Zugriff. Für Android 4.0 und höher und Windows 10 (Desktop und Mobile) und höher, erstellen und Bereitstellen der **PKCS #12 (. PFX) Certificate Profile**. Verwenden der **SCEP-Zertifikatprofil** für iOS 7.1 und höher, Mac OS X 10.9 und höher, Android 4.0 und höher und Windows Phone 8.1 und höher. Sie müssen für jede Plattform ein eigenes Profil erstellen. Wenn Sie das Profil erstellen ordnen Sie es der **vertrauenswürdiges stammzertifikatprofil** die Sie bereits erstellt haben.

## Nächste Schritte
- [Konfigurieren der Zertifikatinfrastruktur](Configure-certificate-infrastructure.md)
- [Konfigurieren von zertifikatprofilen für Intune](Configure-Intune-certificate-profiles.md)
> [!NOTE]           
> -    Wenn Sie eine Unternehmenszertifizierungsstelle verfügen, müssen Sie eines erstellen. 
>- Wenn Sie sich entscheiden, müssen basierend auf Ihrer Geräteplattformen, das Profil vereinfacht Certificate Enrollment Protocol (SCEP) verwenden Sie auch einen Server Network Device Enrollment Service (NDES) konfigurieren.
>-  Gibt an, ob SCEP verwendet werden sollen oder oder. PFX-Profile, müssen Sie zum Herunterladen und Konfigurieren des Microsoft Intune-Zertifikatconnectors.
> Diese Konfiguration wird in diesem Thema beschriebenen [Zertifikatinfrastruktur konfigurieren](Configure-certificate-infrastructure.md).

<!--HONumber=Mar16_HO2-->


