---
title: "Registrieren Ihres macOS-Geräts bei Intune | Microsoft-Dokumentation"
description: "Beschreibt, wie Sie ein Mac OS-Gerät bei Intune registrieren."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: e2a507ff6f803cf022536824ca2f12f6d6a64d75
ms.openlocfilehash: 4b532299070bdb8ddf0e9de1e6b598e8dcd8ffb3
ms.lasthandoff: 02/24/2017


---

# <a name="enroll-your-macos-device-in-intune"></a>Registrieren Ihres Mac OS-Geräts bei Intune

Sie benötigen Zugriff auf Apps, Daten und Ressourcen Ihrer Organisation, um Ihre Arbeit erledigen zu können. Wenn Sie bei der Arbeit ein Mac OS-Gerät verwenden, muss ein __Verwaltungsprofil__ installiert werden. Hierbei handelt es sich einfach um eine von Ihrem IT-Administrator eingerichtete Datei, mit der Einstellungen und Zugriffsinformationen auf Ihren Mac geladen werden. Möchten Sie mehr erfahren? Finden Sie heraus, [was geschieht, wenn Sie die Unternehmensportal-App installieren und Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Wenn Sie versuchen, ein iOS-Gerät – z.B. ein iPhone oder ein iPad – zu registrieren, [folgen Sie stattdessen diesen Anweisungen](enroll-your-device-in-intune-ios.md).

1. Suchen Sie im __Dock__ nach __Safari__, und öffnen Sie ein neues Fenster. Öffnen Sie dann die [Unternehmensportal-Website](http://portal.manage.microsoft.com).
2. Melden Sie sich bei mit Ihrem Geschäfts-, Schul- oder Unikonto bei der Unternehmensportal-Website an.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Wenn Sie sich anmelden, werden Ihnen die verfügbaren Registerkarten der __Startseite__, der __Apps__ und der __Kategorien__ angezeigt. Auf dieser Seite wird Ihnen angezeigt, welche Apps installiert werden können. Wenn Sie noch keine registrierten Geräte haben, wird Ihnen die Meldung **We can‘t show you any apps** (Keine Apps verfügbar) angezeigt. Um fortzufahren wählen Sie __Meine Geräte__ aus.

 ![Ein Screenshot der Startseite des Webportals; im Webportal wird angezeigt, dass noch keine Apps installiert werden können; darunter die Schaltfläche „Meine Geräte“.](./media/macOS_enroll_001_landing_page.png)

4. Auf der Seite __Meine Geräte__ wird entweder eine Liste der registrierten Geräte angezeigt oder einfach nur ein Banner. Dies hängt davon ab, ob Sie bereits ein macOS- oder ein anderes Gerät registriert haben. Wählen Sie das Banner __Wenn Ihr Gerät aufgelistet ist, klicken Sie hier, um es zu identifizieren.  Sie können auch hier klicken, um ein nicht aufgelistetes Gerät zu registrieren__ aus, um ein nicht aufgelistetes Gerät zu registrieren.

  ![Ein Screenshot der Seite „Meine Geräte“ mit mehreren nicht identifizierten Geräten oberhalb der Banneraufforderung, nicht aufgelistete Geräte zu registrieren oder nicht identifizierte Geräte zu identifizieren.](./media/macOS_enroll_002_tap_here_banner.png)

5. Es wird ein Popupfenster mit einer kurzen Erläuterung dazu geöffnet, warum Sie __dieses Gerät identifizieren oder registrieren__ müssen. Lesen Sie die angezeigten Informationen, und klicken Sie auf __Registrieren__, um den Vorgang fortzusetzen.

 ![Dieses Mac OS-Gerät identifizieren oder registrieren](./media/macOS_enroll_003_IDenroll_popup.png)

6. Es wird ein zweites Popupfenster mit einer kurzen Erläuterung dazu geöffnet, was bei der __Registrierung dieses Geräts__ geschieht. Lesen Sie die angezeigten Informationen, und klicken Sie auf __Installieren__, um den Vorgang fortzusetzen.

 ![Dieses Mac OS-Gerät registrieren](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Intune benötigt Zugriff auf Ihren Computer, um sicherzustellen, dass die Gerätesicherheit für den Zugriff auf Organisationsinformationen ausreicht. Finden Sie heraus, [was geschieht, wenn Sie Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. Die __Systemeinstellungen__ werden geöffnet, und Sie erhalten die Meldung __„Verwaltungsprofil“ installieren?__ Klicken Sie auf __Installieren__, um den Vorgang fortzusetzen, oder zeigen Sie weitere Details an, indem Sie auf __Profil anzeigen__ klicken.

 ![Verwaltungsprofil installieren](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Ein Mac OS-Popupfenster wird angezeigt. Bestätigen Sie, dass Sie die Änderungen durchführen möchten, indem Sie den __Benutzernamen__ und das __Kennwort__ für Ihren Computer eingeben, und klicken Sie auf __OK__. Daraufhin wird das Verwaltungsprofil auf Ihrem Mac installiert.

 ![Popupfenster zur Mac OS-Profilinstallation](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Möglicherweise werden auf Ihrem Mac zusätzliche Meldungen mit weiteren Details zum Profil angezeigt, oder Sie müssen die __Installation__ bestätigen. Klicken Sie auf __Weiter__ und __Installieren__, um den Vorgang fortzusetzen. Sobald die Installation abgeschlossen ist, können Sie das neu installierte __Verwaltungsprofil__ in der Liste der __Geräteprofile__ anzeigen.

 ![Installiertes Mac OS-Profil](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Sie finden entsprechende Kontaktinformationen auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

