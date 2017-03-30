---
title: "Hinzufügen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie | Microsoft-Dokumentation"
description: "Fügen Sie Skycure-Apps, die Microsoft Authenticator-App und die iOS-Konfigurationsrichtlinie der klassischen Intune-Konsole hinzu."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 2910bcc6b4b34da8c50899cac21d7c9ec926e9ec
ms.lasthandoff: 03/21/2017


---

# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Hinzufügen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sie müssen Intune verwenden, um die Skycure-Apps hinzuzufügen und bereitzustellen, damit Endbenutzer Benachrichtigungen über auf ihren mobilen Geräten erkannte Bedrohungen sowie eine Anleitung zur Behebung der Bedrohungen erhalten können.

Außerdem benötigen Sie [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), damit Benutzer ihre Identität von Azure AD überprüfen lassen können, und die iOS-App-Konfigurationsrichtlinie, die signalisiert, dass die Skycure iOS-App Intune und Azure AD Single Sign-On (SSO) verwenden soll, damit Benutzer nicht bei jeder Anmeldung in der Skycure-App Benutzername und Kennwort eingeben müssen.

## <a name="before-you-begin"></a>Vorbereitung

-   Die unten beschriebenen Schritte müssen in der [klassischen Intune-Konsole](https://manage.microsoft.com/) abgeschlossen werden.

-   Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der Skycure-Verwaltungskonsole konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich in die klassische Intune-Konsole einloggen.

-   Die Skycure-Integrationsdatei muss zur Verwendung bereit sein. Dies ist die ZIP-Datei, die zuvor aus der Skycure-Verwaltungskonsole heruntergeladen wurde und die Datei **skycure\_configuration.plist** mit den Richtlinienparametern für die iOS-App-Konfiguration enthält.

-   Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:

    -   [Hinzufügen von Apps mit Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/add-apps)

    -   [Hinzufügen von iOS-Apps mit Konfigurationsrichtlinien in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-the-skycure-app-for-android"></a>So fügen Sie die Skycure-App für Android hinzu

1.  Wählen Sie in der klassischen Intune-Konsole die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.

2.  Wählen Sie auf der Seite **Softwaresetup** die Option **Externer Link** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Skycure-App für Android-URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) ein.

    ![Intune-Softwareherausgeber, URL angeben](../media/mtp/skycure-add-apps-1.png)

3.  Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.

    ![Intune-Softwareherausgeber, Softwarebeschreibung](../media/mtp/skycure-add-apps-2.png)

4.  Klicken Sie auf **Hochladen** und dann auf **Schließen**.

## <a name="to-add-the-skycure-app-for-ios"></a>So fügen Sie die Skycure-App für iOS hinzu

1.  Wählen Sie in der klassischen Intune-Konsole die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.

2.  Wählen Sie auf der Seite **Softwaresetup** die Option **Verwaltete iOS-App aus dem App Store** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Skycure-App für iOS-URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) ein.

    ![Intune-Softwareherausgeber, verwaltete iOS-App](../media/mtp/skycure-add-apps-3.png)

3.  Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.

    ![Intune-Softwareherausgeber, Optionen](../media/mtp/skycure-add-apps-4.png)

4.  Wählen Sie auf der Seite **Anforderungen** unter **Typ des mobilen Geräts** die Option **Any** (Beliebig) aus, und klicken Sie dann auf **Weiter**.

5.  Klicken Sie auf **Hochladen** und dann auf **Schließen**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>So fügen Sie die Microsoft Authenticator-App für iOS hinzu

1.  Wählen Sie in der klassischen Intune-Konsole die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.

2.  Wählen Sie auf der Seite **Softwaresetup** die Option **Verwaltete iOS-App aus dem App Store** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Microsoft Authenticator-App für iOS-URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) ein.

    ![Intune-Softwareherausgeber, verwaltete iOS-App 2](../media/mtp/skycure-add-apps-5.png)

3.  Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.

    ![Intune-Softwareherausgeber, verwaltete iOS-App 3](../media/mtp/skycure-add-apps-6.png)

4.  Wählen Sie auf der Seite **Anforderungen** unter **Typ des mobilen Geräts** die Option **Any** (Beliebig) aus, und klicken Sie dann auf **Weiter**.

5.  Klicken Sie auf **Hochladen** und dann auf **Schließen**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Hinzufügen der Skycure iOS-App-Konfigurationsrichtlinie

1.  Wählen Sie in der klassischen Intune-Konsole **Richtlinie** &gt; **Übersicht &gt; Richtlinie hinzufügen** aus.

2.  Erweitern Sie in der Liste der Richtlinien den Eintrag **iOS**, wählen Sie **Richtlinie zur Konfiguration mobiler Apps (iOS 8.0 und höher)** und dann **Richtlinie erstellen** aus.

    ![iOS-App-Konfigurationsrichtlinie](../media/mtp/skycure-add-apps-7.png)

3.  Geben Sie im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für iOS-Apps an.

    a.  Öffnen Sie die Datei **skycure\_configuration.plist** mit einem Text-Editor wie Editor, kopieren Sie den Inhalt und fügen Sie ihn in den Text unter **Richtlinie zur Konfiguration mobiler Apps** ein, und wählen Sie **Überprüfen** und dann **Richtlinie speichern** aus.

       ![iOS-App-Konfigurationsrichtlinie 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Nächste Schritte

[Bereitstellen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie](https://docs.microsoft.com/intune/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
