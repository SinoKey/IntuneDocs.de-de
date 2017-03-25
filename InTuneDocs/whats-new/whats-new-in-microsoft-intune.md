---
title: Neuheiten | Microsoft-Dokumentation
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 2a602b351cf7f345bd56f20394943ea25f2d2060
ms.lasthandoff: 03/15/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Neuerungen in Microsoft Intune – März 2017
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Neue Benutzeroberfläche für die Unternehmensportal-App für Android <!--621622-->

Die Unternehmensportal-App für Android aktualisiert ihre Benutzeroberfläche für ein moderneres Erscheinungsbild und höhere Benutzerfreundlichkeit. Wichtige Updates sind:

- Farben: Die IT-Abteilung kann die Färbung der Kopfzeilen der Registerkarte „Unternehmensportal“ dem Branding gemäß festlegen.
- Apps: Auf der Registerkarte **Apps** wurden die Schaltflächen **Empfohlene Apps** und **Alle Apps** aktualisiert.
- Suche: Auf der Registerkarte **Apps** ist die Schaltfläche **Suche** nun eine unverankerte interaktive Schaltfläche.
- Navigation in Apps: Die Ansicht **Alle Apps** enthält die Registerkartenansicht **Featured** (Highlights), **Alle** und **Kategorien**, um die Navigation zu vereinfachen.
- Unterstützung: Die Registerkarten **Meine Geräte** und **IT kontaktieren** wurden aktualisiert, um die Lesbarkeit zu verbessern.

Ausführlichere Informationen zu diesen Änderungen finden Sie unter [Aktualisierungen für die Benutzeroberfläche für Endbenutzer-Apps in Intune](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->

Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Signierungsskript für das Windows 10-Unternehmensportal <!--941642-->

Wenn Sie die Windows 10-Unternehmensportal-App herunterladen und querladen möchten, steht Ihnen nun ein Skript zur Vereinfachung und Optimierung des App-Signierungsprozesses für Ihre Organisation zur Verfügung.   Das herunterladbare Skript sowie Informationen zu dessen Verwendung finden Sie bei TechNet unter [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Microsoft Intune-Signierungsskript für das Windows 10-Unternehmensportal). Weitere Informationen zu dieser Ankündigung finden Sie im Blog des Intune-Supportteams unter [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Aktualisieren Ihrer Windows 10-Unternehmensportal-App).


## <a name="notices"></a>Benachrichtigungen

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Verbesserte Unterstützung für Android-Benutzer in China<!--720444-->

Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte Apps von chinesischen Marktplätzen beziehen. Das Unternehmensportal unterstützt diesen Workflow durch Umleiten von Android-Benutzern in China, damit sie das Unternehmensportal und Outlook-Apps von lokalen App-Stores herunterladen können. Dies verbessert die Benutzerfreundlichkeit, wenn Richtlinien für bedingten Zugriff aktiviert sind, sowohl für die mobile Geräteverwaltung als auch die mobile Anwendungsverwaltung. Das Unternehmensportal und Outlook-Apps für Android sind in den folgenden chinesischen App-Stores verfügbar:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Bewährte Methode: Sicherstellen, dass die Unternehmensportal-Apps auf dem neuesten Stand sind <!--879465-->

Im Dezember 2016 haben wir ein Update veröffentlicht, das die Erzwingung der mehrstufigen Authentifizierung (multi-factor authentication, MFA) für eine Gruppe von Benutzern ermöglicht, wenn diese ein Gerät unter iOS, Android, Windows 8.1 (oder höher) oder Windows Phone 8.1 (oder höher) registrieren. Für dieses Feature werden bestimmte Basisversionen der Unternehmensportal-App für Android (ab v5.0.3419.0) und iOS (ab v2.1.17) benötigt.

Intune wird von Microsoft kontinuierlich verbessert, indem die Konsole und die Unternehmensportal-Apps für alle unterstützten Plattformen um neue Funktionen erweitert werden. Microsoft veröffentlicht deshalb nur Korrekturen für Probleme, die in der jeweils aktuellen Version der Unternehmensportal-App vorliegen. Wir empfehlen daher die Verwendung der jeweils neuesten Version der Unternehmensportal-Apps, um optimale Ergebnisse zu erzielen.

>[!Tip]
> Stellen Sie sicher, dass die Benutzer auf ihren Geräten die automatische Aktualisierung von Apps über den entsprechenden App Store konfiguriert haben. Wenn Sie die Android-Unternehmensportal-App über eine Netzwerkfreigabe bereitgestellt haben, können Sie die neueste Version aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140) herunterladen.

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams nun für MAM unter iOS und Android verfügbar

Microsoft hat die allgemeine Verfügbarkeit von Microsoft Teams angekündigt. Die aktualisierten Microsoft Teams-Apps für iOS und Android verfügen nun über Funktionen für die mobile App-Verwaltung (Mobile App Management, MAM) mit Intune. Ihre Teams profitieren dadurch von einer flexiblen geräteübergreifenden Arbeitsweise, und Gespräche sowie Unternehmensdaten sind in jeder Phase bestens geschützt. Ausführlichere Informationen finden Sie in der [Microsoft-Teams-Ankündigung](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) des Enterprise Mobility and Security-Blogs.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Neuigkeiten in der öffentlichen Vorschau der neuen Intune-Administratoroberfläche auf Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/intune-azure/introduction/whats-new) an.

> [!Note]
> Wir veröffentlichen gerade die aktuellen Monatsupdates für die Vorschau des Azure-Portals. Aufgrund der Rolloutmethode des Intune-Diensts stehen die Änderungen jedoch möglicherweise nicht sofort zur Verfügung.  Mehrere Komponenten des Diensts müssen nacheinander aktualisiert werden, damit die neuen Portalfeatures verfügbar werden. Änderungen an der Vorschau des Azure-Portals werden im Laufe des Monats eingeführt. Die Liste mit allen Änderungen finden Sie unter [Neuigkeiten in der Vorschau von Microsoft Intune](/intune-azure/introduction/whats-new).

## <a name="whats-coming"></a>Was steht an?

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->

Apple hat angekündigt, dass sie ab Frühjahr 2017 bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwingen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuigkeiten in der Azure-Vorschau](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Neuheiten – Archiv](whats-new-archive.md)

