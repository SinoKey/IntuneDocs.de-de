---
title: "Schützen von Unternehmensdaten durch Datenverschlüsselung | Microsoft Intune"
description: "Dieser Leitfaden hilft Ihnen dabei, Ihr Unternehmen vor Datenverlust zu schützen, indem durch die Verwendung einer Richtlinie in mobilen Apps eine Kennung sowie die Datenverschlüsselung erzwungen wird."
keywords: "Verschlüsselung, PIN, Daten"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ms.reviewer: pchacon
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7d4f7d48e14a7d4f6a19cf3c459406ce241647a
ms.openlocfilehash: 0dd683017028dc594fc2326df7f8592c706843a2


---

# Erste Schritte: Schützen von Unternehmensdaten durch Datenverschlüsselung
Microsoft Intune kann Ihnen dabei helfen, den Verlust von Daten aus mobilen Office-Apps auf unterschiedlichste Weise zu verhindern, z.B.:
- Durch Verschlüsseln von Unternehmensdaten mit der höchsten Geräteverschlüsselungsstufe, die von iOS und Android bereitgestellt wird.
- Auf iOS- und Android-Geräten, die aufgrund von Datenschutzanforderungen oder rechtlichen Anforderungen nicht bei einer Lösung für die Verwaltung mobiler Geräte registriert werden können.

Microsoft Intune kann Ihnen auch dabei helfen, den Verlust von Daten aus mobilen Office-Apps zu verhindern, sowie Office 365-Daten (O365) zu sichern, ohne mobile iOS- oder Android-Geräte bei einer vollständigen Verwaltung mobiler Geräte registrieren zu müssen. Dies gilt auch, wenn Sie für die verwalteten mobilen Geräte eine Drittanbieterlösung für die Verwaltung mobiler Geräte verwenden. 

## Ist dieses Schnellstarthandbuch für mich geeignet?
Dieses Schnellstarthandbuch stellt eine gute Ressource für Sie dar, wenn Sie die folgenden Voraussetzungen erfüllen:
- Sie verwenden bzw. verfügen bereits über O365-Lizenzen, die Sie verwenden möchten, und Sie verwalten mobile Office-Apps.
- Sie planen, mobile Office-Apps unter iOS oder Android zu verwenden. 
- Sie verwenden eine beliebige Lösung für die Verwaltung mobiler Geräte (von Microsoft oder einem Drittanbieter). Wenn Sie aufgrund gesetzlicher Vorschriften keine Lösung für die Verwaltung mobiler Geräte verwenden können, können Sie diesen Leitfaden verwenden. 

> [!NOTE] 
> Windows stellt für mobile Office-Apps noch keine unterstützte Plattform dar. Die Verwaltung mobiler Anwendungen ohne Registrierung ist bisher nicht kompatibel mit Exchange oder lokalem SharePoint. Sie können nur Daten schützen, die in Online-Versionen gehostet werden.

Dieser Leitfaden hilft Ihnen dabei, Ihr Unternehmen vor Datenverlust zu schützen, indem eine Kennung sowie die Datenverschlüsselung erzwungen wird. Dies erfolgt durch die Verwendung von Richtlinien in mobilen Apps, die Ihre Mitarbeiter für den Zugriff auf sensible Daten verwenden, ohne dass eine vollständige Registrierung bei einer Geräteverwaltungslösung erforderlich ist. Microsoft Intune ermöglicht Ihnen das Festlegen von MAM-Richtlinien (mobile application management, Verwaltung mobiler Anwendungen) in mobilen Office-Apps für [iOS](https://products.office.com/en-us/mobile/office-mobile-apps-for-ios) und [Android](https://products.office.com/en-us/mobile/office-mobile-apps-for-android). Dadurch werden O365-Daten geschützt, ohne dass Benutzer ihre Geräte in einer MDM-Lösung (mobile device management, Verwaltung mobiler Geräte) registrieren müssen, wobei zudem gleichzeitig eine hervorragende Endbenutzerfreundlichkeit der mobilen Office-Apps bewahrt wird. 

## Wie gehe ich dabei vor?
1.  [Lesen Sie, wie Sie App-Daten schützen können](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) 
2.  [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 
3.  [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) 

## Zusätzliche Informationen:
- [Erfahren Sie mehr über die Endbenutzererfahrung für MAM-fähige Apps mit Microsoft Intune.](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Wählen Sie aus, wie Sie Apps für die mobile Anwendungsverwaltung mit Microsoft Intune vorbereiten.](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- [Lassen Sie sich die Liste der Microsoft Intune-Anwendungspartner anzeigen.](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)



<!--HONumber=Oct16_HO3-->


