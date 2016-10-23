---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Neues in Microsoft Intune – Oktober 2016
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Neuheiten

### Bedingter Zugriff für die mobile Anwendungsverwaltung
Sie können den Zugriff auf Exchange Online einschränken, sodass der Zugriff nur durch Apps erfolgen kann, die wie Outlook Richtlinien zur Intune-Verwaltung von mobilen Anwendungen unterstützen. [Dieses neue Feature](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) stellt die perfekte Ergänzung von Intune-MAM-Richtlinien (Mobile App Management) dar, da Sie nun den Zugriff auf integrierte E-Mail-Clients oder andere Apps, die nicht mit den Intune-MAM-Richtlinien konfiguriert wurden, blockieren können. Dadurch wird sichergestellt, dass Ihre Benutzer mithilfe von Apps auf die Daten Ihrer Organisation zugreifen, die mithilfe von Intune MAM geschützt werden können. Sie können in die Verwaltung von mobilen Apps mithilfe von Intune im Azure-Portal einsteigen. Suchen Sie auf dem Blatt „Einstellungen“ nach dem neuen Abschnitt „Bedingter Zugriff“.

### Bedingter Zugriff für Windows-PCs
Sie können jetzt über die Intune-Verwaltungskonsole Richtlinien für bedingten Zugriff erstellen, um den Zugriff von Windows-PCs auf [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) und [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) zu blockieren. Sie können auch Richtlinien für bedingten Zugriff erstellen, um den Zugriff auf Office-Desktop- und universelle Anwendungen zu blockieren.

### Unterstützung für Android for Work
Intune ist jetzt Teil des Android for Work-Programms. Wir werden in diesem Monat mit der Einführung der Unterstützung für Android for Work-Funktionen in Intune beginnen.
[Lesen Sie die Ankündigung von Microsoft zur Intune-Unterstützung für Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Die folgenden Intune-Themen sind neu oder wurden mit Informationen zu Android for Work aktualisiert:

Für IT-Experten:
- [Einrichten von Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Beschränken des E-Mail-Zugriffs auf Exchange Online- und neue Exchange Online Dedicated-Umgebungen mit Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Beschränken des E-Mail-Zugriffs auf lokale Exchange- und ältere Exchange Online Dedicated-Umgebungen mit Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Einstellungen für Kompatibilitätsrichtlinien für Android for Work-Geräte in Microsoft Intune](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [How to deploy Android for Work apps (Bereitstellen von Android for Work-Apps)](/intune/deploy-use/android-for-work-apps)
- [Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work-Richtlinieneinstellungen in Microsoft Intune](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Für Endbenutzer:
- [Was geschieht beim Erstellen eines Arbeitsprofils?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Erstellen eines Arbeitsprofils und Registrieren Ihres Geräts bei Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Lookout-Integration zum Schutz von iOS-Geräten
Im Oktober integriert Microsoft die Mobile Threat Protection-Lösung von Lookout, um mobile iOS-Geräte durch die Erkennung von Schadsoftware, gefährlichen Apps usw. auf Geräten zu schützen. Mithilfe der Lösung von Lookout können Sie die Bedrohungsstufe bestimmen und konfigurieren. Sie können in Intune eine Regel der Kompatibilitätsrichtlinie erstellen, um die Gerätekonformität auf der Grundlage der Risikobewertung durch Lookout zu bestimmen. Mithilfe von Richtlinien für den bedingten Zugriff können Sie den Zugriff auf Unternehmensressourcen auf der Basis des Kompatibilitätsstatus des Geräts zulassen oder blockieren.

Endbenutzer nicht kompatibler iOS-Geräte werden zur Registrierung aufgefordert und müssen die Lookout for Work-App auf ihren Geräten installieren, die App aktivieren und in der Lookout for Work-Anwendung gemeldete Bedrohungen beheben, um auf Unternehmensdaten zugreifen zu können. Hier erhalten Sie Informationen zum [Konfigurieren und Bereitstellen von Lookout for Work-Apps](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Intune App Wrapping Tool für Android
Sie können Ihre Apps mit dem Intune App Wrapping Tool für die Verwendung von Intune-MAM-Richtlinien (Verwaltung mobiler Anwendungen) aktivieren. Die Unterstützung für Intune-MAM-Richtlinien ohne Registrierung des Geräts ist nun verfügbar.

### Verwalten von Druckvorgängen von mit MAM-Richtlinien verwalteten Apps
Sie können jetzt verhindern, dass über Apps, die über MAM-Richtlinien verfügen, Unternehmensdaten gedruckt werden. Diese Einstellung ist im [Azure-Portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) verfügbar und wird sowohl auf [iOS](/Intune/deploy-use/ios-mam-policy-settings)- als auch [Android](/Intune/deploy-use/android-mam-policy-settings)-Geräten unterstützt.
<!--TFS 1014328-->

## Benachrichtigungen

### Kompatibilität von Android Samsung KNOX mit Intune
Bestimmte Modelle des Telefons Samsung Galaxy Ace können nicht von Intune als Samsung KNOX-Geräte verwaltet werden. Wenn Sie diese Geräte in Intune registrieren, werden sie stattdessen als Android-Standardgeräte verwaltet.

Folgende Modellnummern sind betroffen:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Weder Sie noch Ihre Endbenutzer müssen weitere Schritte unternehmen. Weitere Informationen finden Sie auf der [Samsung KNOX](https://www.samsungknox.com)-Website.

### Unternehmensportal-App für Windows 8 ist veraltet; Unterstützung für Windows Phone 8- und Windows RT-Plattformen wird beendet
Ab Oktober 2016 wird Microsoft Intune die Unterstützung für das Windows 8-Unternehmensportal beenden. Microsoft Intune wird auch die Unterstützung für die Windows Phone 8- und Windows RT-Plattformen beenden. Die Registrierung oder Aktualisierung von Windows Phone 8- oder Windows RT-Geräten wird daher nicht mehr möglich sein.

Bereits registrierte Windows Phone 8-, Windows RT- und Windows 8-Geräte können weiterhin verwaltet werden. Aktualisieren Sie Windows Phone 8- und Windows 8-Geräte auf Windows Phone 8.1 und Windows 8.1, und nutzen Sie die entsprechenden Windows Phone 8.1- und Windows 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte verteilen zu können.

Ab November 2016 wird die Unterstützung für das Windows Phone 8-Unternehmensportal beendet.
<!--TFS 1255391-->

## Was steht an?

### Neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte
Microsoft veröffentlicht ein neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte. Diese App, die das neue universelle Windows 10-Format nutzt, bietet dem Benutzer eine aktualisierte Benutzeroberfläche innerhalb der App und identische Oberflächen auf allen Windows 10-Geräten – sowohl PCs als auch mobilen Geräten – sowie all die Funktionen, die er heute bereits verwendet.

Mit der neuen App können Benutzer auch zusätzliche Plattformfunktionen wie einmaliges Anmelden (SSO) und die zertifikatbasierte Authentifizierung auf Windows 10-Geräten nutzen. Die App wird als Upgrade der vorhandenen Windows 8.1- und Windows Phone 8.1-Unternehmensportalinstallationen im Windows Store zur Verfügung gestellt. Weitere Informationen finden Sie unter [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorherige Versionen von Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


