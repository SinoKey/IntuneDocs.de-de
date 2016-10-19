---
title: Early Edition | Microsoft Intune
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Anstehende Neuerungen in Microsoft Intune – Oktober
Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Informieren Sie sich regelmäßig über neue Updates der anstehenden Neuerungen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Verwalten von Druckvorgängen von mit MAM-Richtlinien verwalteten Apps
Sie können jetzt verhindern, dass über Apps, die über MAM-Richtlinien verfügen, Unternehmensdaten gedruckt werden. Diese Einstellung ist im [Azure-Portal](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) verfügbar und wird sowohl auf [iOS](..deployuse/ios-mam-policy-settings)- als auch [Android](..deployuse/android-mam-policy-settings)-Geräten unterstützt.
<!--TFS 1014328-->

### Neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte
Microsoft veröffentlicht ein neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte. Diese App, die das neue universelle Windows 10-Format nutzt, bietet dem Benutzer eine aktualisierte Benutzeroberfläche innerhalb der App und identische Oberflächen auf allen Windows 10-Geräten – sowohl PCs als auch mobilen Geräten – sowie all die Funktionen, die er heute bereits verwendet.

Mit der neuen App können Benutzer auch zusätzliche Plattformfunktionen wie einmaliges Anmelden (SSO) und die zertifikatbasierte Authentifizierung auf Windows 10-Geräten nutzen. Die App wird als Upgrade der vorhandenen Windows 8.1- und Windows Phone 8.1-Unternehmensportalinstallationen im Windows Store zur Verfügung gestellt.
<!--TFS 1016502-->

### Unterstützung für Android for Work

Intune ist jetzt Teil des [Android for Work-Programms](https://enterprise.google.com/android/partners/). Wir werden in diesem Monat mit der Einführung der Unterstützung für Android for Work-Funktionen in Intune beginnen.

[Lesen Sie die Ankündigung von Microsoft zur Intune-Unterstützung für Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Kompatibilität von Android Samsung KNOX mit Intune

Bestimmte Modelle des Telefons Samsung Galaxy Ace können nicht von Intune als Samsung KNOX-Geräte verwaltet werden. Wenn Sie diese Geräte in Intune registrieren, werden sie stattdessen als Android-Standardgeräte verwaltet.
Folgende Modellnummern sind betroffen:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Weder Sie noch Ihre Endbenutzer müssen weitere Schritte unternehmen.
Weitere Informationen finden Sie auf der [Samsung KNOX](https://www.samsungknox.com)-Website.

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Unternehmensportal-App für Windows 8 ist veraltet; Unterstützung für Windows Phone 8- und Windows RT-Plattformen wird beendet
Ab Oktober 2016 wird Microsoft Intune die Unterstützung für das Windows 8-Unternehmensportal beenden. Microsoft Intune wird auch die Unterstützung für die Windows Phone 8- und Windows RT-Plattformen beenden. Die Registrierung oder Aktualisierung von Windows Phone 8- oder Windows RT-Geräten wird daher nicht mehr möglich sein.

Bereits registrierte Windows Phone 8-, Windows RT- und Windows 8-Geräte können weiterhin verwaltet werden. Aktualisieren Sie Windows Phone 8- und Windows 8-Geräte auf Windows Phone 8.1 und Windows 8.1, und nutzen Sie die entsprechenden Windows Phone 8.1- und Windows 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte verteilen zu können.

Ab November 2016 wird die Unterstützung für das Windows Phone 8-Unternehmensportal beendet.
<!--TFS 1255391-->

### Bedingter Zugriff für die mobile Anwendungsverwaltung
Sie können jetzt eine Richtlinie für bedingten Zugriff erstellen, um den Zugriff von mobilen Anwendungen auf [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) und [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md) zu blockieren. Sie können die integrierten E-Mail-Clients und -Apps blockieren, die nicht mit dem Intune App SDK für MAM aktiviert wurden.  Dazu erstellen Sie im Azure-Portal eine Richtlinie für bedingten Zugriff und geben die Anwendungen an, die Zugriff auf Exchange Online und SharePoint Online haben sollen.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Lookout-Integration zum Schutz von iOS-Geräten
Im Oktober integriert Microsoft die Mobile Threat Protection-Lösung von Lookout, um mobile iOS-Geräte durch die Erkennung von Schadsoftware, gefährlichen Apps usw. auf Geräten zu schützen. Mithilfe der Lösung von Lookout können Sie die Bedrohungsstufe bestimmen und konfigurieren. Sie können in Intune eine Regel der Kompatibilitätsrichtlinie erstellen, um die Gerätekonformität auf der Grundlage der Risikobewertung durch Lookout zu bestimmen. Mithilfe von Richtlinien für den bedingten Zugriff können Sie den Zugriff auf Unternehmensressourcen auf der Basis des Kompatibilitätsstatus des Geräts zulassen oder blockieren.

Endbenutzer nicht kompatibler iOS-Geräte werden zur Registrierung aufgefordert und müssen die Lookout for Work-App auf ihren Geräten installieren, die App aktivieren und in der Lookout for Work-Anwendung gemeldete Bedrohungen beheben, um auf Unternehmensdaten zugreifen zu können.
<!--TFS 1319493-->

### Intune App SDK und App Wrapping Tool für Android
Sie können Ihre Apps mit dem Intune App Wrapping Tool oder dem Intune App SDK für die Verwendung von Intune-MAM-Verwaltungsrichtlinien (mobile Anwendungsverwaltung) aktivieren. Folgende neue Updates werden für das App Wrapping Tool und das SDK bereitgestellt:

* Unterstützung für Android N
* Unterstützung für Intune-MAM-Richtlinien ohne Registrierung des Geräts
* Unterstützung für Xamarin-basierte Android-Apps

Unter dem folgenden Link können Sie MAM ohne Geräteregistrierung und Xamarin-Unterstützung in der öffentlichen Vorschau des Android App Wrapping Tools testen: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Oct16_HO1-->


