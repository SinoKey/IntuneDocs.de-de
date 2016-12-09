---
title: "Registrieren Ihres Mac OS-Geräts bei Intune | Microsoft Intune"
description: "Beschreibt, wie Sie ein Mac OS-Gerät bei Intune registrieren."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 650e9b0700971e626e4062c312111ef60e74badc


---

# <a name="enroll-your-macos-device-in-intune"></a>Registrieren Ihres Mac OS-Geräts bei Intune

Sie benötigen Zugriff auf Apps, Daten und Ressourcen Ihrer Organisation, um Ihre Arbeit erledigen zu können. Wenn Sie bei der Arbeit ein Mac OS-Gerät verwenden, muss ein __Verwaltungsprofil__ installiert werden. Hierbei handelt es sich einfach um eine von Ihrem IT-Administrator eingerichtete Datei, mit der Einstellungen und Zugriffsinformationen auf Ihren Mac geladen werden. Möchten Sie mehr erfahren? Finden Sie heraus, [was geschieht, wenn Sie die Unternehmensportal-App installieren und Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Wenn Sie versuchen, ein iOS-Gerät – z.B. ein iPhone oder ein iPad – zu registrieren, [folgen Sie stattdessen diesen Anweisungen](enroll-your-device-in-intune-ios.md).

1. Suchen Sie im __Dock__ nach __Safari__, und öffnen Sie ein neues Fenster. Öffnen Sie dann die [Unternehmensportal-Website](http://portal.manage.microsoft.com).
2. Melden Sie sich bei mit Ihrem Geschäfts-, Schul- oder Unikonto bei der Unternehmensportal-Website an.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Nach der Anmeldung sehen Sie alle verfügbaren __Apps__, __Meine Geräte__ sowie __Kontaktinformationen__, um sich mit dem IT-Personal in Verbindung zu setzen. Oben auf der Seite wird folgender Hinweis angezeigt: **Entweder ist das Gerät nicht registriert, oder das Gerät kann nicht durch das Unternehmensportal identifiziert werden. <u>Tippen Sie hier</u>, um ein anderes Gerät auszuwählen.** Klicken Sie auf __Tippen Sie hier__.

 ![Mac OS-Startseite des Unternehmensportals](./media/macOS_enroll_001_landing_page.png)

4. Es wird ein Popupfenster mit einer kurzen Erläuterung dazu geöffnet, warum Sie __dieses Gerät identifizieren oder registrieren__ müssen. Lesen Sie die angezeigten Informationen, und klicken Sie auf __Registrieren__, um den Vorgang fortzusetzen.

 ![Dieses Mac OS-Gerät identifizieren oder registrieren](./media/macOS_enroll_002_IDenroll_popup.png)

5. Es wird ein zweites Popupfenster mit einer kurzen Erläuterung dazu geöffnet, was bei der __Registrierung dieses Geräts__ geschieht. Lesen Sie die angezeigten Informationen, und klicken Sie auf __Installieren__, um den Vorgang fortzusetzen.

 ![Dieses Mac OS-Gerät registrieren](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Intune benötigt Zugriff auf Ihren Computer, um sicherzustellen, dass die Gerätesicherheit für den Zugriff auf Organisationsinformationen ausreicht. Finden Sie heraus, [was geschieht, wenn Sie Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

6. Die __Systemeinstellungen__ werden geöffnet, und Sie erhalten die Meldung __„Verwaltungsprofil“ installieren?__ Klicken Sie auf __Installieren__, um den Vorgang fortzusetzen, oder zeigen Sie weitere Details an, indem Sie auf __Profil anzeigen__ klicken.

 ![Verwaltungsprofil installieren](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Ein Mac OS-Popupfenster wird angezeigt. Bestätigen Sie, dass Sie die Änderungen durchführen möchten, indem Sie den __Benutzernamen__ und das __Kennwort__ für Ihren Computer eingeben, und klicken Sie auf __OK__. Daraufhin wird das Verwaltungsprofil auf Ihrem Mac installiert.

 ![Popupfenster zur Mac OS-Profilinstallation](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Möglicherweise werden auf Ihrem Mac zusätzliche Meldungen mit weiteren Details zum Profil angezeigt, oder Sie müssen die __Installation__ bestätigen. Klicken Sie auf __Weiter__ und __Installieren__, um den Vorgang fortzusetzen. Sobald die Installation abgeschlossen ist, können Sie das neu installierte __Verwaltungsprofil__ in der Liste der __Geräteprofile__ anzeigen.

 ![Installiertes Mac OS-Profil](./media/macOS_enroll_006_sysprefs_installed_profile.png)

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Sie finden entsprechende Kontaktinformationen auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


