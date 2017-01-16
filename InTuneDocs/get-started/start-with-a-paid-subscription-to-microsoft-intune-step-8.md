---
title: "Aktivieren der Geräteregistrierung | Microsoft-Dokumentation"
description: "Legen Sie die MDM-Autorität fest, und aktivieren Sie die Registrierung für iOS-, Windows-, Android- und Mac-Geräte."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 654c5b65a9fde6742f3682b1fd5ba6c056d0d45b


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>Registrieren mobiler Geräte und Installieren einer App

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Um die Verwaltung mobiler Geräte mit Intune einzurichten, müssen Sie zunächst die *Autorität für die Verwaltung mobiler Geräte* (Mobile Device Management, MDM) festlegen, die den Dienst identifiziert, der Ihrem Konto zugeordnete Geräte verwalten kann. In diesem Leitfaden wird vorausgesetzt, dass Sie nicht den System Center Configuration Manager, sondern den Intune-Dienst verwenden. Nachdem die MDM-Autorität festgelegt wurde, können Sie die Verwaltung für Geräteplattformen aktivieren und Ihre Geräte mit der Unternehmensportal-App registrieren.

## <a name="enable-device-enrollment"></a>Aktivieren der Geräteregistrierung

1. **Festlegen von Intune als MDM-Autorität**
    Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Verwaltung** > **Verwaltung mobiler Geräte**. Wählen Sie dann unter **Aufgaben** die Option **MDM-Autorität festlegen**.  

2. Klicken Sie im Dialogfeld „MDM-Autorität“ auf **Ja**.

    ![Verwaltungskonsole – MDM auf „Intune“ festlegen](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Auswählen der Registrierungsmethode für Geräte

Intune kann je nach Unternehmensanforderungen Geräte in unterschiedlicher Weise verwalten. Zu den verfügbaren Registrierungsszenarien gehören beispielsweise BYOD (Bring Your Own Device), unternehmenseigene Geräte, CYOD (Choose Your Own Device) und Geräte im Kioskmodus.

Führen Sie diese Schritte zum [Auswählen der Registrierungsmethode für Geräte](choose-how-to-enroll-devices1.md) aus.

## <a name="enable-mdm-for-your-device-platform"></a>Aktivieren von MDM für Ihre Geräteplattform
Die Registrierung muss für iOS-, Mac- und Android for Work-Geräte aktiviert werden, indem eine Beziehung zwischen dem Plattformanbieter und Ihrem Intune-Mandanten eingerichtet wird. Für Windows- und Android-Geräte sind keine zusätzlichen Schritte erforderlich, aber für Windows-Geräte können Sie die Geräteregistrierung für Ihre Benutzer vereinfachen, indem Sie einen besonderen DNS-Registrierungseintrag erstellen.

Aktivieren Sie die Geräteregistrierung für die Geräteplattform, die Sie verwalten möchten. Je nach Plattform sind andere Anforderungen relevant:

-  [iOS und Mac OS](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Windows-PC](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Windows 10 Mobile und Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Sobald die Registrierung aktiviert wurde, können Benutzer die Unternehmensportal-App auf ihr Gerät herunterladen und den Vorgang zur Geräteregistrierung durchführen.

### <a name="enable-company-owned-device-enrollment"></a>Aktivieren der Registrierung für unternehmenseigene Geräte
Sie können auch verschiedene Szenarien für die [Registrierung unternehmenseigener Geräte](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) unterstützen, darunter:
- [Apple-Geräteregistrierungsprogramm](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Registrierung über den Setup-Assistenten für Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Registrierung über den Setup-Assistenten für Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Geräteregistrierungs-Manager](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Nächste Schritte
Gratulation! Sie haben den letzten Schritt der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen. Ihre anfängliche Konfiguration ist jetzt abgeschlossen, und Sie können in Betracht ziehen, weitere MDM-Funktionen zu aktivieren.

>[!div class="step-by-step"]

>[&larr; **Registrieren von Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Aufgaben nach der Konfiguration** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Dec16_HO2-->


