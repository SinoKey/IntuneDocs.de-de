---
title: "Hinzufügen und Zuweisen von MTD-Apps zu Intune"
titleSuffix: Intune on Azure
description: "Hinzufügen von MTD-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie in zu Intune unter Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Hinzufügen und Zuweisen von Mobile Threat Defense-Apps (MTD) mit Intune

Sie können Intune verwenden, um MTD-Apps hinzuzufügen und bereitzustellen, damit Endbenutzer Benachrichtigungen über auf ihren mobilen Geräten erkannte Bedrohungen sowie eine Anleitung zur Behebung der Bedrohungen erhalten können.

Für iOS-Geräte benötigen Sie [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), damit Benutzer ihre Identitäten von Azure AD überprüfen lassen können. Sie benötigen zusätzlich die iOS-App-Konfigurationsrichtlinie, die die MTD-iOS-App anweist, Intune zu verwenden.

> [!TIP]
> Das Intune-Unternehmensportal arbeitet als Broker auf Android-Geräten, damit Benutzer ihre Identitäten von Azure AD überprüfen lassen können.

## <a name="before-you-begin"></a>Vorbereitung

-   Die unten beschriebenen Schritte müssen in der [Azure-Portal](https://portal.azure.com/) durchgeführt werden.

-   Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:

    -   [Hinzufügen von Apps in Microsoft Intune](apps-add.md)

    -   [Hinzufügen von iOS-Apps mit Konfigurationsrichtlinien in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

    -   [Zuweisen einer App mit Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Hinzufügen einer iOS-App-Konfigurationsrichtlinien](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-apps"></a>So fügen Sie Apps hinzu

### <a name="skycure-app-for-android"></a>Skycure-App für Android

- Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an. Verwenden Sie diese [Store-URL der Skycure-App](https://play.google.com/store/apps/details?id=com.skycure.skycure) in **Schritt 7**.

### <a name="skycure-app-for-ios"></a>Skycure-App für iOS

- Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an. Verwenden Sie diese [Store-URL der Skycure-App](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.

### <a name="microsoft-authenticator-app-for-ios"></a>Microsoft Authenticator-App für iOS

- Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an. Verwenden Sie diese [Store-URL der Microsoft Authenticator-App](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.

### <a name="lookout-for-work-android-app"></a>Lookout for Work-Android-App

- Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an. Verwenden Sie diese [Store-URL der Lookout for Work-Google-App](https://play.google.com/store/apps/details?id=com.lookout.enterprise) in **Schritt 7**.

### <a name="lookout-for-work-ios-app"></a>Lookout for Work-iOS-App

- Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an. Verwenden Sie diese [Store-URL der Lookout for Work-iOS-App](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Lookout for Work-App außerhalb des Apple Store

Sie müssen nun die Lookout for Work-App für iOS erneut signieren. Lookout verteilt die Lookout for Work-App für iOS außerhalb von iOS App Store. Bevor Sie die App verteilen, müssen Sie die App mit Ihrem iOS Enterprise Developer Certificate neu signieren.

Ausführliche Anweisungen zum erneuten Signieren der Lookout for Work-Apps für iOS finden Sie unter [iOS App Re-Signing Process (Erneute Signatur bei iOS-Apps)](https://personal.support.lookout.com/hc/articles/114094038714) auf der Lookout-Website.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Aktivieren der Azure AD-Authentifizierung für die Lookout for Work-iOS-App

Aktivieren Sie die Azure Active Directory-Authentifizierung für iOS-Benutzer, indem Sie folgendermaßen vorgehen:

1. Wechseln Sie zum [Azure-Portal](https://portal.sazure.com), melden Sie sich mit Ihren Anmeldeinformationen an, und navigieren Sie zur Seite „Anwendungen“.
  
2. Fügen Sie die **Lookout for Work iOS-App** als eine **native Clientanwendung** hinzu.

3. Ersetzen Sie **com.lookout.enterprise.yourcompanyname** mit der Kundenbundle-ID, die Sie beim Unterzeichnen der IPA ausgewählt haben.

4.  Hinzufügen von zusätzlichen Umleitungs-URI: **&lt;companyportal://code/>** gefolgt von einer URL-codierten Version Ihrer ursprünglichen URI-Umleitung.

5.  Fügen Sie **Delegierte Berechtigungen** zu Ihrer App hinzu.

    > [!NOTE] 
    > Weitere Informationen finden Sie unter [Konfigurieren Sie eine native Clientanwendung](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>Hinzufügen der IPA-Datei für Lookout for Work

- Laden Sie die neu signierte IPA-Datei hoch, wie im Thema [Hinzufügen von branchenspezifischen iOS-Apps in Microsoft Intune](lob-apps-ios.md) beschrieben. Sie müssen auch iOS 8.0 oder höher als die mindestens erforderliche Betriebssystemversion festlegen.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>So ordnen Sie die MTD-App einer iOS-App-Konfigurationsrichtlinie zu

### <a name="for-skycure"></a>Für Skycure

-   Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der Skycure-Verwaltungskonsole konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich in die klassische Intune-Konsole einloggen.

-   Die Skycure-Integrationsdatei muss zur Verwendung bereit sein. Dies ist die ZIP-Datei, die zuvor aus der Skycure-Verwaltungskonsole heruntergeladen wurde und die Datei **skycure\_configuration.plist** mit den Richtlinienparametern für die iOS-App-Konfiguration enthält.

- In den Anweisungen für [die Verwendung der iOS-App-Konfigurationsrichtlinien von Microsoft Intune](app-configuration-policies-use-ios.md) erfahren Sie, wie Sie die iOS-App-Konfigurationsrichtlinie für Skycure hinzufügen.
    - Verwenden Sie in Schritt 8 die Option **XML-Daten eingeben**, kopieren Sie den Inhalt aus der Datei **skycure_configuration.plist**, und fügen Sie den Inhalt in den Text der Konfigurationsrichtlinie ein.

Sie können auch den Inhalt von **skycure_configuration.plist** hieraus kopieren:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Für Lookout

- Erstellen Sie die iOS-App-Konfigurationsrichtlinie wie im Thema [zur Verwendung der iOS-App-Konfigurationsrichtlinie](app-configuration-policies-use-ios.md) beschrieben.

## <a name="to-assign-mtd-apps"></a>So fügen Sie MTD-Apps hinzu und weisen sie zu

- Anweisungen hierzu finden Sie im Thema [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md).

## <a name="next-steps"></a>Nächste Schritte

[Set up the Skycure integration with Intune (Einrichten der Skycure-Integration mit Intune)](skycure-mtd-connector-integration.md)
[Set up the Lookout integration with Intune (Einrichten der Lookout-Integration mit Intune)](lookout-mtd-connector-integration.md)
