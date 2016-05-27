---
# required metadata

title: Registrieren von Geräten bei Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrieren von Geräten für die Verwaltung in Intune
Die Registrierung durch die Verwaltung mobiler Geräte (MDM) in Microsoft Intune dient dazu, Geräte in die Verwaltung aufzunehmen und den Zugriff auf Ressourcen zu ermöglichen. Auf welche Weise Sie die Geräte registrieren, hängt von Gerätetyp, Besitz und benötigtem Verwaltungsniveau ab. Szenarien mit „Bring your own Device“- (BYOD) und firmeneigenen Geräten (Company-Owned Device, COD) erfordern eine Registrierung. Organisationen, die Exchange ActiveSync verwenden, entweder lokal oder in der Cloud gehostet, können ein niedrigeres Verwaltungsniveau ohne Registrierungsanforderungen aktivieren. Windows-PCs können auch mit Intune-Clientsoftware verwaltet werden.

## Aktivieren der Geräteregistrierung  
 Durch die Registrierung können Benutzer von ihren persönlichen Geräten aus auf Unternehmensressourcen zugreifen, und Administrator können sicherstellen, dass diese Geräte Richtlinien zum Schutz von Unternehmensressourcen einhalten. Dies ist die beste Möglichkeit, BYOD-Szenarien mit Intune zu ermöglichen. Der Administrator muss die Registrierung in der Intune-Konsole aktivieren. Dazu kann es erforderlich sein, eine Vertrauensstellung mit dem Gerät einzurichten und Benutzern Lizenzen zuzuweisen. Das Gerät wird dann in der Regel vom Benutzer durch Eingabe der Anmeldeinformationen seines Geschäfts- oder Schulkontos registriert. Das Gerät empfängt anschließend die Richtlinie von Intune und erhält Zugriff auf Ressourcen.

[Vorbereiten der Registrierung von Geräten in Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrieren aller firmeneigenen Geräte
Firmeneigene Geräte (COD) können mit der Intune-Konsole verwaltet werden. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

[Registrieren aller firmeneigenen Geräte](manage-corporate-owned-devices.md)

## Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der MDM EAS-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet.



[Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Verwalten von Windows-PCs mit Intune  
Sie können Microsoft Intune auch verwenden, um Windows-PCs mit der Windows PC-Clientsoftware zu verwalten. Mit dem Intune-Client verwaltete PCs können:

 - Software- und Hardwareinventurberichte erstellen
 - Desktopanwendung installieren (z. B. EXE- und MSI-Dateien)
 - Firewalleinstellungen

Mit der Intune-Clientsoftware verwaltete Computer können nicht selektiv zurückgesetzt oder abgekoppelt werden und können viele der Intune Verwaltungsfunktionen wie z. B. den bedingten Zugriff, VPN- und WLAN-Einstellungen oder die Bereitstellung von Zertifikaten und E-Mail-Konfigurationen nicht nutzen.

[Verwalten von Windows-PCs mit Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


