---
title: Early Edition | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Die Early Edition für Microsoft Intune – Dezember

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche auf Azure

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die neue Dokumentation an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integration der Telekommunikationsausgaben in der öffentlichen Vorschau des Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) über alle Plattformen hinweg <!--747590-->
Sie können die mehrstufige Authentifizierung jetzt für eine ausgewählte Gruppe von Benutzern erzwingen, wenn diese ein iOS- oder Android-Gerät bzw. ein Gerät mit Windows 8.1 und höher oder Windows Phone 8.1 und höher über das Azure-Verwaltungsportal registrieren möchten. Dazu konfigurieren Sie MFA in der Microsoft Intune-Registrierungsanwendung in Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Bedingter Zugriff für MAM mit SharePoint Online <!--VSO 679339-->
Sie können den Zugriff auf SharePoint Online für Apps, die von den Intune-Verwaltungsrichtlinien für mobile Apps (Mobile App Management, MAM) nicht unterstützt werden, blockieren.  Sie können in die Verwendung von Intune Mobile App Management (MAM) im Azure-Portal einsteigen. Suchen Sie nach dem Abschnitt __Bedingter Zugriff__ im Blatt __Einstellungen__. Hier finden Sie auch die Option für SharePoint Online. Dieses Feature wird getrennt vom Rest des Service Release ausgeliefert.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Einschränken der Registrierung von Mobilgeräten bei Intune
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile. 
* Die Registrierung als Mobilgeräteplattform kann für macOS und Windows 8.1 oder höher eingeschränkt werden. 
* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Agents nicht eingeschränkt. 
* Für iOS gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann. Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.


## <a name="notices"></a>Benachrichtigungen

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) bei der Registrierung geht auf das Azure-Portal über <!--VSO 750545-->
Bisher mussten sich Administratoren entweder bei der Intune-Konsole oder der Configuration Manager-Konsole (vor Version 1610) anmelden, um MFA für Intune-Registrierungen festzulegen. Mit diesem aktualisierten Feature melden Sie sich jetzt mit Ihren Intune-Anmeldeinformationen beim [Microsoft Azure-Portal](https://manage.windowsazure.com) an und konfigurieren die MFA-Einstellungen über Azure AD. Weitere Informationen dazu finden Sie [hier](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Unternehmensportal-App für Android ist jetzt in China verfügbar <!--VSO 658093-->
Die Unternehmensportal-App für Android wird jetzt zum Download in China veröffentlicht. Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte Apps von chinesischen App-Marktplätzen beziehen. Die Unternehmensportal-App für Android steht bei 360, Tencent, Xiaomi, Wandoujia und Huawei zum Download zur Verfügung. 

Die Unternehmensportal-App für Android verwendet Google Play Services für die Kommunikation mit dem Microsoft Intune-Dienst. Da Google Play Services in China noch nicht verfügbar sind, kann die Ausführung der folgenden Aufgaben bis zu 8 Stunden dauern. 

|Intune-Administratorkonsole| Intune-Unternehmensportal-App für Android |Intune Unternehmensportalwebsite|   
|---|---|---|
|Vollständiges Zurücksetzen| Entfernen eines Remotegeräts| Entfernen eines Geräts (lokal und remote)|
|Selektives Zurücksetzen| Zurücksetzen eines Geräts| Zurücksetzen eines Geräts|
|Bereitstellung neuer oder aktualisierter Apps| Installieren von verfügbaren Branchen-Apps| Zurücksetzen der Gerätekennung|
|Remotesperre|||
|Zurücksetzen der Kennung|||

## <a name="deprecations"></a>Veraltete Funktionen

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Entfernen von Richtlinien für das mobile Exchange Online-Postfach <!--770687-->
Seit Dezember können Administratoren Richtlinien für das mobile Exchange Online-Postfach (EAS) nicht mehr in der Intune-Konsole anzeigen oder konfigurieren. Das Rollout dieser Änderung erfolgt für alle Intune-Mandanten im Laufe des Dezembers und Januars. Die Konfiguration aller vorhandenen Richtlinien bleibt unverändert. Verwenden Sie zum Konfigurieren neuer Richtlinien die Exchange-Verwaltungsshell. Weitere Informationen finden Sie [hier](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Intune AV Player-, Image Viewer- und PDF Viewer-Apps werden auf Android nicht mehr unterstützt <!--747553-->
Ab Mitte Dezember 2016 können Benutzer die Intune AV-Player-, Image Viewer- und PDF Viewer-Apps nicht mehr verwenden. Diese Apps wurden durch die Azure Information Protection-App ersetzt. [Hier](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) erfahren Sie mehr über die Azure Information Protection-App.

### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO5-->


