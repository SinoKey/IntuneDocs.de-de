---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e88c14ad77d8fe1b4c0fe2e7676d126e6288146
ms.openlocfilehash: bcd77b751c2059131558e1cbfeebd4d3f71086e5


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Neuerungen in Microsoft Intune – November 2016
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## <a name="new-capabilities"></a>Neue Funktionen

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

<!--### New Microsoft Intune Company Portal App for Windows 10 Devices
Microsoft is releasing a new Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike - while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.-->

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



<!--HONumber=Nov16_HO3-->


