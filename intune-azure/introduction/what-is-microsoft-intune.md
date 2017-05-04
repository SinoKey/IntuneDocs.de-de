---
title: "Einführung in Intune in der Vorschau des Azure-Portals"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Lernen Sie die Grundlagen der Vorschau von Intune im Azure-Portal kennen, und erfahren Sie, wie sie Ihnen beim Verwalten Ihrer Geräte helfen kann."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 92e07a49205ffaf287fc3aa2da6a6376b75fda4f
ms.lasthandoff: 04/24/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Einführung in die Vorschau von Microsoft Intune im Azure-Portal


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune wird in das Azure-Portal eingeführt. Dies bedeutet, dass sich die Workflows und Funktionalität, mit denen Sie vertraut sind, ändern werden.
Das neue Portal bietet Ihnen eine Vorschau der neuen und aktualisierten Funktionen im Azure-Portal, in dem Sie die mobilen Geräte, PCs und Apps Ihrer Organisation verwalten können.
Letztendlich werden alle Intune-Funktionen in Azure überführt, Sie können aber schon heute zahlreiche Intune-Aufgaben über das Azure-Portal ausführen. Da sich die neue Benutzeroberfläche noch in der Vorschau befindet, stehen einige Funktionen nicht noch im Portal zur Verfügung. Einzelheiten finden Sie im Abschnitt [Neuheiten](#what's-new).

> [!IMPORTANT]
> **Das neue Portal wird nicht noch angezeigt?**<br>
> Wir haben bereits begonnen, die Vorschau für einige Mandanten verfügbar zu machen. Vorhandene Mandanten werden zu Beginn des Kalenderjahrs 2017 migriert. Sie erhalten vor der Migration Ihres Mandanten eine Benachrichtigung im Office-Nachrichtencenter.


Sie finden in dieser Bibliothek, die während der Vorschauphase fortlaufend aktualisiert wird, neue Produktdokumentationen. Wenn Sie Vorschläge haben soll, hinterlassen Sie in den Kommentaren zum Thema Ihr Feedback. Wir freuen uns, von Ihnen zu hören.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Wichtige Funktionen der neuen Benutzeroberfläche:

- Eine integrierte Konsole für alle Komponenten von Enterprise Mobility + Security (EMS)
- Eine HTML-Konsole basierend auf Webstandards
- Microsoft Graph-API-Unterstützung zur Automatisierung vieler Aktionen
- Azure Active Directory-Gruppen (AD) für Kompatibilität zwischen all Ihren Azure-Anwendungen
- Unterstützung für die meisten modernen Webbrowser

Die Dokumentation zur klassischen Intune-Konsole finden Sie in [der Intune-Dokumentationsbibliothek](https://docs.microsoft.com/en-us/intune/).

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
Dieser Abschnitt enthält Informationen zu [Neuheiten](/intune-azure/introduction/whats-new), zu [bekannten Problemen](/intune-azure/introduction/known-issues-in-the-intune-preview), zum [Support](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) und zu den [ersten Schritte mit einer kostenlosen Testversion](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) von Intune.
### <a name="plan-and-design"></a>Planung und Entwurf
Informationen zum [Planen und Entwerfen](/intune-azure/plan-and-design/get-started) Ihrer Intune-Umgebung.
### <a name="device-enrollment"></a>Geräteregistrierung
[Erfahren Sie, wie Sie Ihre Geräte mit Intune verwalten](/intune-azure/enroll-devices/what-is).
### <a name="device-compliance"></a>Gerätekompatibilität
[Definieren Sie eine Konformitätsebene für Ihre Geräte, und erstellen Sie anschließend Berichte zu allen Geräten, die nicht konform sind](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="device-configuration"></a>Gerätekonfiguration
[Erfahren Sie etwas über die Profile, die Sie verwenden können, um Einstellungen und Funktionen auf den von Ihnen verwalteten Geräten zu konfigurieren](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="devices"></a>Geräte
[Lernen Sie die verwalteten Geräte im Inventar und in den Berichten kennen](/intune-azure/manage-devices/what-is).
### <a name="mobile-apps"></a>Mobile Apps
[So veröffentlichen, verwalten, konfigurieren und schützen Sie Apps](/intune-azure/manage-apps/what-is-app-management).
### <a name="conditional-access"></a>Bedingter Zugriff
[Beschränken Sie den Zugriff auf Exchange-Dienste basierend auf von Ihnen festgelegte Bedingungen](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="on-premises-access"></a>Lokaler Zugriff
[Konfigurieren Sie den Zugriff auf Exchange ActiveSync und Exchange lokal.](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Informieren Sie sich über die Benutzer der Geräte, die Sie verwalten, und organisieren Sie Ressourcen in Gruppen](/intune-azure/manage-users/what-is).
### <a name="groups"></a>Gruppen
[Erfahren Sie, wie Sie Azure Active Directory-Gruppen in Intune verwenden können.](/intune-azure/manage-users/get-started-with-groups)
### <a name="intune-roles"></a>Intune-Rollen
[Steuern Sie, welche Benutzer welche Intune-Aktionen ausführen dürfen, und für wen diese Aktionen gelten](/intune-azure/access-control/role-based-access-control). Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.
### <a name="software-updates"></a>Softwareupdates
[Erfahren Sie, wie Sie Softwareupdates für Windows 10-Geräte konfigurieren](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).



## <a name="whats-new"></a>Neuheiten

[Erfahren Sie, was in der Vorschauversion neu ist](/intune-azure/introduction/whats-new).

