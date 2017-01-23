---
title: Neuheiten | Microsoft-Dokumentation
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1d9ebc7fd727b80091625ed5256ae634323a9257
ms.openlocfilehash: f7e71d20923e113b533668a7b5aef688de196182


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Neuerungen in Microsoft Intune – Dezember 2016
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche auf Azure<!--736542-->
Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform. Im Vorfeld der allgemeinen Verfügbarkeit dieses Portals für alle Intune-Mandanten freuen wir uns, bekannt geben zu können, dass noch in diesem Monat mit dem Rollout einer Vorschau dieser neuen Verwaltungsoberfläche für ausgewählte Mandanten begonnen wird.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. In der Zwischenzeit erfahren Sie im Azure-Portal in der [neuen Dokumentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) mehr über die Neuigkeiten zu Microsoft Intune.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integration der Telekommunikationsausgaben in der öffentlichen Vorschau des Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) über alle Plattformen hinweg <!--747590-->
Sie können die mehrstufige Authentifizierung jetzt für eine ausgewählte Gruppe von Benutzern erzwingen, wenn diese ein iOS- oder Android-Gerät bzw. ein Gerät mit Windows 8.1 und höher oder Windows Phone 8.1 und höher über das Azure-Verwaltungsportal registrieren möchten. Dazu konfigurieren Sie MFA in der Microsoft Intune-Registrierungsanwendung in Azure Active Directory.

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Einschränken der Registrierung von Mobilgeräten<!--747596-->
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.
* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.
* Für iOS gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.


## <a name="notices"></a>Benachrichtigungen

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) bei der Registrierung geht auf das Azure-Portal über <!--VSO 750545-->
Bisher mussten sich Administratoren entweder bei der Intune-Konsole oder der Configuration Manager-Konsole (vor der Version von Oktober 2016) anmelden, um MFA für Intune-Registrierungen festzulegen. Mit diesem aktualisierten Feature melden Sie sich jetzt mit Ihren Intune-Anmeldeinformationen beim [Microsoft Azure-Portal](https://manage.windowsazure.com) an und konfigurieren die MFA-Einstellungen über Azure AD. Weitere Informationen dazu finden Sie [hier](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china--vso-658093--"></a>Unternehmensportal-App für Android ist jetzt in China verfügbar <!--VSO 658093-->
Die Unternehmensportal-App für Android wird jetzt zum Download in China veröffentlicht. Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte Apps von chinesischen App-Marktplätzen beziehen. Die Unternehmensportal-App für Android wird in den folgenden Stores zum Download zur Verfügung stehen:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Die Unternehmensportal-App für Android verwendet Google Play Services für die Kommunikation mit dem Microsoft Intune-Dienst. Da Google Play Services in China noch nicht verfügbar sind, kann die Ausführung der folgenden Aufgaben bis zu 8 Stunden dauern. 

|Intune-Administratorkonsole| Intune-Unternehmensportal-App für Android |Intune Unternehmensportalwebsite|   
|---|---|---|
|Vollständiges Zurücksetzen| Entfernen eines Remotegeräts| Entfernen eines Geräts (lokal und remote)|
|Selektives Zurücksetzen| Zurücksetzen eines Geräts| Zurücksetzen eines Geräts|
|Bereitstellung neuer oder aktualisierter Apps| Installieren von verfügbaren Branchen-Apps| Zurücksetzen der Gerätekennung|
|Remotesperre|||
|Zurücksetzen der Kennung|||

## <a name="deprecations"></a>Veraltete Funktionen

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Silverlight wird von Firefox nicht mehr unterstützt<!--VSO TBA-->
Mozilla entfernt die Unterstützung für Silverlight in Version 52 des [Firefox-Browsers](https://www.mozilla.org/firefox) ab März 2017. Bei der vorhandenen Intune-Konsole Daher werden Sie sich mit Firefox-Versionen nach Version 51 nicht mehr anmelden können. Wir empfehlen, für den Zugriff auf die Verwaltungskonsole Internet Explorer 10 oder 11 oder eine [Firefox-Version vor Version 52](https://ftp.mozilla.org/pub/firefox/releases/) zu verwenden. Durch den Übergang von Intune zum Azure-Portal wird die Unterstützung einer Reihe von [modernen Browsern](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) ohne Abhängigkeit von Silverlight möglich.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Entfernen von Richtlinien für das mobile Exchange Online-Postfach <!--770687-->
Seit Dezember können Administratoren Richtlinien für das mobile Exchange Online-Postfach (EAS) nicht mehr in der Intune-Konsole anzeigen oder konfigurieren. Das Rollout dieser Änderung erfolgt für alle Intune-Mandanten im Laufe des Dezembers und Januars. Die Konfiguration aller vorhandenen Richtlinien bleibt unverändert. Verwenden Sie zum Konfigurieren neuer Richtlinien die Exchange-Verwaltungsshell. Weitere Informationen finden Sie [hier](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Intune AV Player-, Image Viewer- und PDF Viewer-Apps werden auf Android nicht mehr unterstützt <!--747553-->
Ab Mitte Dezember 2016 können Benutzer die Intune AV-Player-, Image Viewer- und PDF Viewer-Apps nicht mehr verwenden. Diese Apps wurden durch die Azure Information Protection-App ersetzt. [Hier](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) erfahren Sie mehr über die Azure Information Protection-App.

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuheiten – Archiv](whats-new-archive.md)



<!--HONumber=Dec16_HO4-->


