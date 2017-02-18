---
title: Bereitstellen der Lookout for Work-App | Microsoft-Dokumentation
description: "Konfigurieren und Bereitstellen von Lookout for Work-Apps für Android."
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: a7c1a2b7ec1719a47c36e1fe09d1deccd0eed1b1


---

# <a name="configure-and-deploy-lookout-for-work-apps"></a>Konfigurieren und Bereitstellen von Lookout for Work-Apps

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In diesem Artikel wird die Konfiguration und Bereitstellung der Lookout for Work-App für Android- und iOS-Geräte beschrieben.

## <a name="android-google-play-store-app"></a>Android (Google Play Store-App)

1.    Wechseln Sie in der [Microsoft Intune-Administratorkonsole](https://manage.microsoft.com) zu **Apps**, und wählen Sie **Apps hinzufügen** aus.
2.    Wählen Sie auf der Seite **Softwaresetup** des Herausgebers **Externer Link** aus, und geben Sie die folgende URL an: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Klicken Sie nicht auf das Feld, das einen verwalteten Browser vorschreibt.

3.    Geben Sie auf der Seite **Softwarebeschreibung** die folgenden Informationen ein:
  * **Herausgeber:** Lookout Mobile Security
  * **Name:**   Lookout for Work
  * **Beschreibung:** Lookout bietet optimalen Schutz vor mobilen Bedrohungen, um die Sicherheit Ihres Geräts zu gewährleisten. Wenn die Lookout-App auf einem Gerät installiert ist, schützt die App das Gerät vor Bedrohungen und warnt Sie und Ihren Unternehmensadministrator, wenn Bedrohungen erkannt werden.
  * **Kategorie:** Computerverwaltung

4. Nach erfolgreichem Abschluss wird die Meldung **Daten wurden erfolgreich in Microsoft Intune hochgeladen** angezeigt.

  Wenn Sie in der Intune-Konsole auf **Apps** klicken, wird die **Lookout for Work**-App nun in der Liste angezeigt. ![Screenshot der Seite mit den Intune-Administratorkonsolen-Apps, auf der die Liste mit Lookout for Work-Apps angezeigt wird](../media/mtp/lookout-app-listed-intune-console.png)

5. Stellen Sie die App für Benutzer bereit, indem Sie die Lookout for Work-App und anschließend die Option **Bereitstellung verwalten** auswählen.

  Sie müssen die gleichen Benutzer auswählen, die unter der Option „Registrierungsverwaltung“ in der Lookout-MTP-Konsole hinzugefügt wurden.  Informationen zum Hinzufügen von Benutzergruppen zu Lookout MTP finden Sie unter Schritt 3 im Abschnitt [Konfigurieren Ihres Abonnements mit Lookout MTP](configure-and-deploy-lookout-for-work-apps.md).

  >[!IMPORTANT]
  > Dem Intune-Assistenten für die App-Bereitstellung sind die Azure AD-Benutzergruppen nicht bekannt, er verwendet daher die Intune-Benutzergruppen. Sie müssen auf der Grundlage der Azure AD-Benutzergruppe, die bei der Lookout MTP-Konsole registriert ist, eine Intune-Benutzergruppe erstellen, wie in [diesem](plan-your-user-and-device-groups.md) Thema erläutert wird.

6. Aktivieren Sie die Option **Erforderliche Installation**, um vorzuschreiben, dass die Lookout-App auf dem Gerät des Benutzers installiert wird.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (Enterprise-signierte Version der Lookout-App)

1. Stellen Sie sicher, dass die **iOS-Verwaltung** auf Ihrem Gerät eingerichtet ist. Eine Anleitung zum Einrichten Ihres Geräts für die iOS-Verwaltung finden Sie unter [Einrichten der iOS- und Mac-Geräteverwaltung](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. Sie müssen nun die Lookout for Work-App für iOS **erneut signieren**. Lookout verteilt die Lookout for Work-App für iOS außerhalb von iOS App Store. **Vor der Verteilung der App** müssen Sie die App mit Ihrem iOS Enterprise Developer-Zertifikat neu signieren. Ausführliche Anweisungen zum erneuten Signieren der Lookout for Work-Apps für iOS finden Sie unter [iOS App Re-Signing Process (Erneute Signatur bei iOS-Apps)](https://personal.support.lookout.com/hc/en-us/articles/114094038714) auf der Lookout-Website.

3. Aktivieren Sie die Azure Active Directory-Authentifizierung für iOS-Benutzer, indem Sie folgendermaßen vorgehen:
  1.  Melden Sie sich beim [Azure Active Directory-Verwaltungsportal](https://manage.windowsazure.com) an, und navigieren Sie zur Anwendungsseite.
  2.  Fügen Sie die **Lookout for Work-App für iOS** als **native Clientanwendung** hinzu.
  ![Screenshot mit dem Dialogfeld zum Hinzufügen von Apps mit der Option für die native Clientanwendung](../media/mtp/aad-add-app.png)
  3. Ersetzen Sie **com.lookout.enterprise.yourcompanyname** durch die Kundenpaket-ID, die Sie beim Signieren der IPA ausgewählt haben.
  4.  Fügen Sie einen zusätzlichen Umleitungs-URI hinzu: **&lt;companyportal://code/>**, gefolgt von einer URL-codierten Version Ihres ursprünglichen Umleitungs-URI.
  5.  Fügen Sie **delegierte Berechtigungen** zu Ihrer App hinzu.

  Weitere Informationen finden Sie unter [Konfigurieren Sie eine native Clientanwendung](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Laden Sie die neu signierte IPA-Datei hoch, wie im Thema [Hinzufügen von Apps für mobile Geräte zu Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) beschrieben. Legen Sie iOS 8.0 oder höher als die mindestens erforderliche Betriebssystemversion fest.

  ![Screenshot der Apps-Seite in der Intune-Administratorkonsole, auf der die Lookout for Work-App in der Liste der Apps angezeigt wird](../media/mtp/ios-app-uploaded-intune.png)

5. Erstellen Sie die Konfigurationsrichtlinie für verwaltete Apps, wie im Thema [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) beschrieben.

  ![Screenshot des Assistenten zum Erstellen einer neuen Richtlinie, wobei die Konfigurationsrichtlinie für die App für iOS 8.0 oder höher hervorgehoben ist](../media/mtp/ios-app-config.png)

6. Wählen Sie zum **Bereitstellen der App für Benutzer** die Lookout for Work-App und anschließend die Option **Bereitstellung verwalten**.

  Sie müssen die gleichen Benutzer auswählen, die unter der Option „Registrierungsverwaltung“ in der Lookout-Konsole hinzugefügt wurden.  Informationen zum Hinzufügen von Benutzergruppen zum Lookout-Schutz vor Gerätebedrohungen finden Sie unter Schritt 3 im Abschnitt [Konfigurieren Ihres Abonnements mit Lookout MTP](configure-and-deploy-lookout-for-work-apps.md).

  >[!IMPORTANT]
  > Dem Intune-Assistenten für die App-Bereitstellung sind die Azure AD-Benutzergruppen nicht bekannt, weshalb er die Intune-Benutzergruppen verwendet. Sie müssen daher auf Grundlage der Azure AD-Benutzergruppe, die bei der Lookout-Konsole registriert ist, eine Intune-Benutzergruppe erstellen, was in [diesem](plan-your-user-and-device-groups.md) Thema erläutert wird.

  Aktivieren Sie die Option **Erforderliche Installation**, um vorzuschreiben, dass die Lookout-App auf dem Gerät des Benutzers installiert wird.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Was geschieht beim Öffnen der bereitgestellten App auf dem Gerät?

Wenn der Benutzer Lookout for Work auf dem mobilen Gerät öffnet, wird er aufgefordert, die App zu aktivieren und die Option „Bei Azure Active Directory anmelden“ auszuwählen. Eine ausführliche exemplarische Vorgehensweise mit dem Arbeitsablauf für den Endbenutzer finden sich in folgenden Themen:

* [Sie werden aufgefordert, Lookout for Work auf Ihrem Android-Gerät zu installieren](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Sie müssen eine Bedrohung beseitigen, die Lookout for Work auf Ihrem Android-Gerät erkannt hat](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Nächste Schritte
* [Aktivieren der Regel zum Schutz vor Bedrohungen auf dem Gerät in der Kompatibilitätsrichtlinie](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Jan17_HO2-->


