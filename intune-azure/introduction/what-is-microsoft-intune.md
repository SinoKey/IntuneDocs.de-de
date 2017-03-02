---
title: "Einführung in Intune in der Vorschau des Azure-Portals"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Lernen Sie die Grundlagen der Vorschau von Intune im Azure-Portal kennen, und erfahren Sie, wie sie Ihnen beim Verwalten Ihrer Geräte helfen kann."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 851ed5e9967939a930d6d9c22a23d7c72a7b52a7
ms.openlocfilehash: f6f8babaca68fdb75ab6ff36d931f8dbd734acf0
ms.lasthandoff: 02/16/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Einführung in die Vorschau von Microsoft Intune im Azure-Portal


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune wird in das Azure-Portal eingeführt. Dies bedeutet, dass sich die Workflows und Funktionalität, mit denen Sie vertraut sind, ändern werden.
Das neue Portal bietet Ihnen eine Vorschau der neuen und aktualisierten Funktionen im Azure-Portal, in dem Sie die mobilen Geräte, PCs und Apps Ihrer Organisation verwalten können.
Alle Intune-Funktionen werden in Azure übernommen, Sie können aber bestimmte Intune-Aufgaben bereits heute im Azure-Portal erledigen. Da sich die neue Benutzeroberfläche noch in der Vorschau befindet, stehen einige Funktionen nicht noch im Portal zur Verfügung. Einzelheiten finden Sie im Abschnitt [Neuigkeiten in der Vorschau](#what's-new-in-the-preview).

> [!IMPORTANT]
> **Das neue Portal wird nicht noch angezeigt?**<br>
> Wir haben bereits begonnen, die Vorschau für einige Mandanten verfügbar zu machen. Vorhandene Mandanten werden zu Beginn des Kalenderjahrs 2017 migriert. Sie erhalten vor der Migration Ihres Mandanten eine Benachrichtigung im Office-Nachrichtencenter. Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


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

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Registrieren von Geräten
[Erfahren Sie, wie Sie Ihre Geräte mit Intune verwalten](/intune-azure/enroll-devices/what-is).
### <a name="devices--groups"></a>Geräte & Gruppen
[Lernen Sie die verwalteten Geräte im Inventar und in den Berichten kennen](/intune-azure/manage-devices/what-is).
### <a name="manage-users"></a>Verwalten von Benutzern
[Erfahren Sie etwas über die Benutzer der von Ihnen verwalteten Geräte](/intune-azure/manage-users/what-is).
### <a name="manage-apps"></a>Verwalten von Apps
[So veröffentlichen, verwalten, konfigurieren und schützen Sie Apps](/intune-azure/manage-apps/what-is-app-management).
### <a name="configure-devices"></a>Konfigurieren von Geräten
[Erfahren Sie etwas über die Profile, die Sie verwenden können, um Einstellungen und Funktionen auf den von Ihnen verwalteten Geräten zu konfigurieren](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="set-device-compliance"></a>Gerätekompatibilität festlegen
[Definieren Sie eine Konformitätsebene für Ihre Geräte, und erstellen Sie anschließend Berichte zu allen Geräten, die nicht konform sind](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="conditional-access"></a>Bedingter Zugriff
[Beschränken Sie den Zugriff auf Exchange-Dienste basierend auf von Ihnen festgelegte Bedingungen](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="access-control"></a>Zugriffssteuerung
[Steuern Sie, welche Benutzer welche Intune-Aktionen ausführen dürfen, und für wen diese Aktionen gelten](/intune-azure/access-control/role-based-access-control). Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.



## <a name="whats-new"></a>Neuheiten

[Erfahren Sie, was in der Vorschauversion neu ist](/intune-azure/introduction/whats-new).

