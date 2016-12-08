---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Neuerungen in Microsoft Intune – November 2016
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte__ Microsoft hat eine neue [Microsoft Intune-Unternehmensportal-App für Windows 10-Geräte](https://www.microsoft.com/store/apps/9wzdncrfj3pz) veröffentlicht. Diese App, die das neue universelle Windows 10-Format nutzt, bietet dem Benutzer eine aktualisierte Benutzeroberfläche innerhalb der App und identische Oberflächen auf allen Windows 10-Geräten – sowohl PCs als auch mobilen Geräten – sowie all die Funktionen, die er heute bereits verwendet.

Mit der neuen App können Benutzer auch zusätzliche Plattformfunktionen wie einmaliges Anmelden (SSO) und die zertifikatbasierte Authentifizierung auf Windows 10-Geräten nutzen. Die App wird als Upgrade der vorhandenen Windows 8.1- und Windows Phone 8.1-Unternehmensportalinstallationen im Windows Store zur Verfügung gestellt. Weitere Informationen finden Sie unter [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Update auf Intune und Android for Work__

> Wenn Ihre Intune-Gruppen zur neuen Azure AD-Gruppenoberfläche migriert wurden, können Sie Apps nur als __Verfügbar__ bereitstellen, während Sie Android for Work-Apps mit der Aktion __Erforderlich__ bereitstellen können.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Das Intune App SDK Cordova-Plug-In unterstützt nun MAM ohne Registrierung
App-Entwickler können das Intune App SDK Cordova-Plug-In jetzt verwenden, um MAM-Funktionalität ohne Geräteregistrierung in Ihren auf Cordova basierenden Apps für Android und iOS zu aktivieren. Sie finden das Intune App SDK Cordova-Plug-in [hier](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Unterstützung für MAM durch die Intune App SDK-Xamarin-Komponente jetzt ohne Registrierung
App-Entwickler können die Intune App SDK Xamarin-Komponente verwenden, um MAM-Funktionalität ohne Geräteregistrierung in Ihren auf Xamarin basierenden Apps für Android und iOS zu aktivieren. Sie finden die Intune App SDK Xamarin-Komponente [hier](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Benachrichtigungen

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Kein signiertes Windows Phone 8-Unternehmensportal zum Hochladen des Symantec-Signaturzertifikats mehr erforderlich
Zum Hochladen des Symantec-Signaturzertifikats ist keine signierte Windows Phone 8-Unternehmensportal-App mehr erforderlich. Das Zertifikat kann einzeln hochgeladen werden.

## <a name="deprecations"></a>Veraltete Funktionen

### <a name="support-for-the-windows-phone-8-company-portal"></a>Unterstützung für das Windows Phone 8-Unternehmensportal
Die Unterstützung für das Windows Phone 8-Unternehmensportal wird jetzt beendet. Die Unterstützung für Windows Phone 8- und WinRT-Plattformen wurde im Oktober 2016 beendet. Die Unterstützung für das Windows Phone 8-Unternehmensportal wurde ebenfalls im Oktober 2016 beendet.


### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorherige Releases von Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


