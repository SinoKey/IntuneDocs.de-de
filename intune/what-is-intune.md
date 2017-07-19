---
title: "Einführung in Intune im Azure-Portal"
titleSuffix: Intune on Azure
description: "Lernen Sie die Grundlagen von Intune im Azure-Portal kennen, und erfahren Sie, wie es Ihnen beim Verwalten Ihrer Geräte helfen kann."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae42ab64945982fedc2d6858e2f3eca8fbed334c
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Einführung in Microsoft Intune im Azure-Portal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune befindet sich nun im Azure-Portal. Dies bedeutet, dass die gewohnten Workflows und Funktionen jetzt anders sind.
Das neue Portal bietet neue und aktualisierte Funktionen im Azure-Portal, in dem Sie die mobilen Geräte, PCs und Apps Ihrer Organisation verwalten können.

> [!IMPORTANT]
> **Das neue Portal wird noch nicht angezeigt?**<br>
> Vorhandene Mandanten werden in die neue Umgebung migriert. Vor der Migration Ihres Mandanten wird im Office-Nachrichtencenter eine Benachrichtigung angezeigt.
>
> Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor Apple-Registrierungsworkflows in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht bekanntgegeben. Wenn Sie mit Ihrem vorhandenen Konto nicht auf das Azure-Portal zugreifen können, empfehlen wir das Erstellen eines Testkontos.
>
> Schauen Sie sich die Liste potenzieller Hindernisse unter https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/ an.


In dieser Bibliothek finden Sie Informationen zum neuen Portal, die ständig aktualisiert werden. Wenn Sie Vorschläge haben soll, hinterlassen Sie in den Kommentaren zum Thema Ihr Feedback. Wir freuen uns, von Ihnen zu hören.

Wichtige Funktionen der neuen Benutzeroberfläche:

- Eine integrierte Konsole für alle Komponenten von Enterprise Mobility + Security (EMS)
- Eine HTML-Konsole basierend auf Webstandards
- Microsoft Graph-API-Unterstützung zur Automatisierung vieler Aktionen
- Azure Active Directory-Gruppen (AD) für Kompatibilität zwischen all Ihren Azure-Anwendungen
- Unterstützung für die meisten modernen Webbrowser

Die Dokumentation zur klassischen Intune-Konsole finden Sie in [der Intune-Dokumentationsbibliothek](https://docs.microsoft.com/intune-classic/).

## <a name="before-you-start"></a>Vorbereitung

Um Intune im Azure-Portal verwenden zu können, benötigen Sie ein Administrator- und ein Mandantenkonto für Intune. [Registrieren Sie sich für ein Konto](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), wenn Sie noch keines haben.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Unterstützte Webbrowser für das Azure-Portal

Das Azure-Portal kann auf die meisten modernen PCs, Macs und Tablets ausgeführt werden. Mobiltelefone werden nicht unterstützt.
Zurzeit werden die folgenden Browser unterstützt:

- Microsoft Edge (neueste Version)
- Microsoft Internet Explorer 11
- Safari (neueste Version, nur auf Mac)
- Chrome (neueste Version)
- Firefox (neueste Version)

Aktuelle Informationen zu den unterstützten Browsern finden Sie im [Azure-Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Inhalt dieser Bibliothek

Die Dokumentation orientiert sich am Layout des Intune-Portals, damit Sie die gewünschten Informationen einfacher finden.

![Azure-Portal-Workloads](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Einführung und erste Schritte
Dieser Abschnitt enthält [einführende Informationen](introduction-intune.md) für die ersten Schritte mit Intune.
### <a name="plan-and-design"></a>Planung und Entwurf
Informationen zum [Planen und Entwerfen](/intune-classic/plan-design/introduction) Ihrer Intune-Umgebung.
### <a name="device-enrollment"></a>Geräteregistrierung
[Erfahren Sie, wie Sie Ihre Geräte mit Intune verwalten](device-enrollment.md).
### <a name="device-compliance"></a>Gerätekompatibilität
[Definieren Sie eine Konformitätsebene für Ihre Geräte, und erstellen Sie anschließend Berichte zu allen Geräten, die nicht konform sind](device-compliance.md).
### <a name="device-configuration"></a>Gerätekonfiguration
[Erfahren Sie etwas über die Profile, die Sie verwenden können, um Einstellungen und Funktionen auf den von Ihnen verwalteten Geräten zu konfigurieren](device-profiles.md).
### <a name="devices"></a>Geräte
[Lernen Sie die verwalteten Geräte im Inventar und in den Berichten kennen](device-management.md).
### <a name="mobile-apps"></a>Mobile Apps
[So veröffentlichen, verwalten, konfigurieren und schützen Sie Apps](app-management.md).
### <a name="conditional-access"></a>Bedingter Zugriff
[Beschränken Sie den Zugriff auf Exchange-Dienste basierend auf von Ihnen festgelegte Bedingungen](conditional-access.md).
### <a name="on-premises-access"></a>Lokaler Zugriff
[Konfigurieren Sie den Zugriff auf Exchange ActiveSync und Exchange lokal.](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Informieren Sie sich über die Benutzer der Geräte, die Sie verwalten, und organisieren Sie Ressourcen in Gruppen](users-add.md).
### <a name="groups"></a>Gruppen
[Erfahren Sie, wie Sie Azure Active Directory-Gruppen in Intune verwenden können.](groups-get-started.md)
### <a name="intune-roles"></a>Intune-Rollen
[Steuern Sie, welche Benutzer welche Intune-Aktionen ausführen dürfen, und für wen diese Aktionen gelten](role-based-access-control.md). Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.
### <a name="software-updates"></a>Softwareupdates
[Erfahren Sie, wie Sie Softwareupdates für Windows 10-Geräte konfigurieren](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Was gibt es Neues?

[Erfahren Sie mehr zu den Neuerungen in Intune](whats-new.md).
