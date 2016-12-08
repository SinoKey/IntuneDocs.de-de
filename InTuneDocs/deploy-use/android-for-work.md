---
title: Informationen zu Android for Work | Microsoft Intune
description: "Intune verwaltet Android for Work, um zusätzliche Verwaltungsfunktionen und zusätzlichen Datenschutz zu bieten, wenn Benutzer ihre Android-Geräte für die Arbeit verwenden."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 83914246bde673b188ca3f7d9cf50b4d0de2edd4
ms.openlocfilehash: 127db326fc96625c719b8136964bae014a904b3d


---

# <a name="manage-android-for-work-devices-with-intune"></a>Verwalten von Android for Work-Geräten mit Intune

Android for Work ist ein Satz von Features und Diensten für Android-Geräte. Diese Features und Dienste bieten zusätzliche Verwaltungsfunktionen und zusätzlichen Datenschutz, wenn Benutzer ihre Android-Geräte für die Arbeit verwenden. Intune kann Ihnen helfen, Apps und Unternehmensressourcen für Android for Work-Geräte bereitzustellen, um sicherzustellen, dass Arbeits- und persönliche Informationen getrennt werden. Bei erfolgreicher Bereitstellung bleiben Apps und die Daten, auf die sie zugreifen, ausschließlich innerhalb der Android for Work-Umgebung auf dem Gerät.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Unterstützte Geräte

Android for Work erfordert neuere Android-Hardware, da viele Verwaltungsfunktionen von Features abhängen, die Teil des neueren Android-Betriebssystems sind. Android for Work wird derzeit von Geräten unterstützt, auf denen Android 5.0 Lollipop und höher ausgeführt wird, und die Arbeitsprofilunterstützung bieten. Für Geräte, die keine native Unterstützung für Android for Work bieten, bleibt die konventionelle Android-Verwaltung verfügbar. Erfahren Sie mehr über [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) (Voraussetzungen für Android for Work).

## <a name="onboarding"></a>Onboarding

Vor dem Registrieren von Android for Work müssen Sie einige Onboardingschritte abschließen. Diese Schritte stellen eine Verbindung zwischen Ihrem Intune-Mandanten und dem Play for Work-Dienst von Google her, der integraler Bestandteil des Verteilungs- und Verwaltungsprozesses der Android for Work-App ist. Erfahren Sie mehr über [Aktivieren der Registrierung von Android for Work-Geräten](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Arbeitsprofilverwaltung

Wenn Sie ein Android for Work-Gerät mit Intune verwalten, verwalten Sie nicht das gesamte Gerät. Das Verwalten von Funktionen wirkt sich nur auf ein Arbeitsprofil aus, das während der Registrierung erstellt wird. Alle Apps, die dem Gerät mit Intune bereitgestellt werden, sind Teil des Arbeitsprofils. Die Symbole für Apps im Arbeitsprofil zeigen eine orangefarbene Aktentasche an. Diese Markierung unterscheidet Unternehmens-Apps von persönlichen Apps auf dem Gerät. Alle Android-Apps und Daten außerhalb des Android for Work-Teils des Geräts bleiben persönlich und unter der Kontrolle des Endbenutzers. Benutzer können jede App ihrer Wahl auf dem persönlichen Teil des Geräts installieren, während Administratoren Aktionen im Bereich des Arbeitsprofils verwalten und überwachen können.

## <a name="app-publishing-and-distribution"></a>Veröffentlichung und Verteilung von Apps

Der Google Play for Work-Dienst ist integraler Bestandteil der App-Verteilung und -Verwaltung. Alle für Android for Work-Geräte im Arbeitsprofil bereitgestellten Apps stammen von Play for Work. Zum Verwalten und Bereitstellen von Apps im Play Store melden Sie sich als Intune-Administrator bei der Play for Work-Website an, und genehmigen Sie Apps für Ihren Intune-Mandanten. Diese Apps werden mit der Intune-Konsole synchronisiert, wo sie mithilfe von Intune verwaltet und bereitgestellt werden können. Von Ihrer Organisation entwickelte branchenspezifische Apps (Line of Business, LOB) müssen mithilfe der Veröffentlichungskonsole für Android-Apps von Google für Play for Work veröffentlicht werden. Branchenspezifische Apps müssen in der Veröffentlichungskonsole für Android-Apps für den Zugriff auf Ihre Organisation konfiguriert werden.

Die Installation von Apps erfolgt ohne Eingreifen des Benutzers und ohne dass der Benutzer **Installation aus unbekannten Quellen** zulassen muss. Zum Suchen nach und Installieren optionaler oder verfügbarer Apps haben die Benutzer die Play Store-App mit Badgeverwendung auf ihren Geräten. Erfahren Sie mehr über [Bereitstellen von Apps für Android for Work-Geräte mit Intune](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>App-Konfiguration

Android for Work bietet die Infrastruktur für die Bereitstellung von App-Konfigurationswerten für Apps, die diese unterstützen. Durch Angabe von Konfigurationswerten für Arbeits-Apps stellen Sie sicher, dass sie ordnungsgemäß eingerichtet sind, wenn der Benutzer die App zum ersten Mal starten. Unterstützung für App-Konfiguration erfordert, dass App-Entwickler ihre Android-Apps speziell für verwaltete Konfigurationswerte erstellen. Wenn dies der Fall, können Sie diese Konfigurationseinstellungen mit Intune angeben und anwenden. Erfahren Sie mehr über [Android for Work app configuration settings](afw-app-configuration-policy.md) (Android for Work-App-Konfigurationseinstellungen).

## <a name="email-configuration"></a>E-Mail-Konfiguration

Android for Work stellt keine Standard-E-Mail-App bzw. kein natives E-Mail-Profil-Objekt bereit, wie es bei iOS der Fall ist. E-Mail-Konfigurationen können stattdessen durch Anwenden von App-Konfigurationseinstellungen auf E-Mail-Apps eingestellt werden, die diese unterstützen. Gmail und Nine Work sind zwei Exchange ActiveSync-Client-Apps (EAS) im Play Store, die die Konfiguration mit der Android for Work-App-Konfiguration unterstützen.

Intune bietet Konfigurationsvorlagen für Gmail- und Nine Work-Apps. Andere E-Mail-Apps, die App-Konfigurationsprofile unterstützen, können mit Konfigurationsrichtlinien für mobile Apps konfiguriert werden.

Wenn Sie bedingten EAS-Zugriff für Android for Work-Geräte verwenden, müssen Sie entweder die Gmail- oder Nine Work-E-Mail-App verwenden. Die Microsoft Outlook for Android-App oder jede andere E-Mail-App, die moderne Authentifizierung über ADAL verwendet, wird ebenfalls unterstützt. Erfahren Sie mehr über [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) (Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen mit Microsoft Intune).

## <a name="mobile-app-management-policies"></a>Verwaltungsrichtlinien für mobile Apps

Einschränkungsrichtlinien, die auf Apps angewandt werden, die für die mobile Anwendungsverwaltung (MAM) aktiviert sind, werden im Arbeitsprofil und persönlichen Profil vollständig unterstützt. Sie können branchenspezifische Apps in der Android-App-Veröffentlichungskonsole unter https://play.google.com/apps/publish veröffentlichen. Diese Konsole enthält eine Option, mit der Sie Apps für Ihr Unternehmen als privat kennzeichnen können. Erfahren Sie mehr über [Einstellungen für Kompatibilitätsrichtlinien für Android for Work-Geräte in Microsoft Intune](afw-compliance-policy-settings-in-microsoft-intune.md). Weitere Informationen finden Sie unter [Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>VPN-Profile

VPN-Unterstützung entspricht Android VPN-Profilen. Die gleichen VPN-Anbieter und grundlegenden Konfigurationsoptionen sind verfügbar. Es gibt zwei wesentliche Unterschiede:

1.  **Arbeitsprofilbezogenes VPN**: VPN-Verbindungen sind auf die Apps beschränkt, die für das Arbeitsprofil bereitgestellt werden. Nur von Android for Work verwaltete Apps können die VPN-Verbindung verwenden. Persönliche Apps auf dem Gerät können eine verwaltete VPN-Verbindung nicht verwenden.

2.  **App-spezifisches VPN**: Wenn ein VPN-Anbieter die Konfiguration für App-spezifisches VPN unterstützt und das Konfigurieren von VPN pro App über das App-Konfigurationsprofil von Android for Work-ermöglicht, kann App-spezifisches VPN in Intune konfiguriert werden. Klären Sie mit dem VPN-Anbieter, ob diese Funktion unterstützt wird. Erfahren Sie mehr über [VPN-Verbindungen in Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Zertifikatprofile

Die gleichen Zertifikatprofil-Konfigurationsoptionen, die für die herkömmliche Android-Verwaltung zur Verfügung stehen, sind auf Android for Work-Geräten verfügbar. Android for Work bietet verbesserte Zertifikatverwaltungs-APIs. Verbesserte Zertifikatsverwaltung bietet die folgenden Funktionen:

1.  Gewährleistung, dass die Zertifikatbereitstellung im Hintergrund und nahtlos für den Benutzer erfolgt.

2.  Gewährleistung, dass die bereitgestellten Zertifikate vollständig entfernt werden, wenn ein Gerät von Intune zurückgezogen und das Arbeitsprofil entfernt wird.

3.  Bietet verbesserte Nachrichten, die Benutzer darüber informieren, dass das Zertifikat bereitgestellt und von ihrer IT-Abteilung über ihren Verwaltungsdienst konfiguriert wurde.

Erfahren Sie mehr darüber unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>WLAN-Profile

Von Android for Work verwaltete WLAN-Profile werden garantiert entfernt, wenn das Gerät von Intune zurückgezogen und das Arbeitsprofil gelöscht wird. Erfahren Sie mehr über [Konfigurieren von Geräten zur Herstellung einer Verbindung mit Ihren WLAN-Unternehmensnetzwerken](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Nächste Schritte
[Aktivieren der Registrierung von Android for Work-Geräten](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Bereitstellen von Apps für Android for Work-Geräte mit Intune](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO5-->


