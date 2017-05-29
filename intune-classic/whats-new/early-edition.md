---
title: Early Edition | Microsoft-Dokumentation
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Die Early Edition für Microsoft Intune – Mai 2017

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
> Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Unterstützung für einmaliges Anmelden über das Unternehmensportal für iOS zu Outlook für iOS <!--834012-->

Benutzer müssen sich nicht mehr in der Outlook-App anmelden, wenn sie in der Unternehmensportal-App für iOS auf dem gleichen Gerät mit dem gleichen Konto angemeldet sind. Wenn Benutzer die Outlook-App starten, können sie ihr Konto auswählen und sich automatisch anmelden. Wir arbeiten auch daran, diese Funktion für andere Microsoft-Apps hinzuzufügen.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Verbesserte Benachrichtigung für Samsung KNOX-Systemstart-PINs <!--1087143-->

Wenn Endbenutzer eine Systemstart-PIN für Samsung KNOX-Geräte festlegen müssen, um Kompatibilität hinsichtlich der Verschlüsselung zu erreichen, führt die für Endbenutzer angezeigte Benachrichtigung diese genau zu der Stelle in der App „Einstellungen“, wenn die Benachrichtigung angetippt wird.  Zuvor hat die Benachrichtigung den Endbenutzer zum Bildschirm für die Kennwortänderung geführt.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Höherstufen der aktuellsten Version des Unternehmensportals für Android <!--1098661-->

Endbenutzer erhalten eine In-App-Benachrichtigung, wenn eine neue empfohlene Version der Unternehmensportal-App für Android auf dem Benachrichtigungsbildschirm der App freigegeben wurde. Diese Benachrichtigung informiert Benutzer darüber, dass ein Update des Unternehmensportals verfügbar ist. Durch Antippen der Benachrichtigung wird eine Webseite mit der Liste der verfügbaren App-Stores geöffnet, in denen die aktualisierte Version heruntergeladen werden kann. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Verbesserungen bei der App-Synchronisierung mit dem Windows 10 Creators Update <!-- 676505 -->

Das Unternehmensportal für Windows 10 initiiert automatisch eine Synchronisierung für App-Installationsanforderungen für Geräte mit dem Windows 10 Creators Update (1704). Dadurch wird das Problem beseitigt, dass App-Installationen während des Zustands „Synchronisierung ausstehend“ verzögert reagieren. Darüber hinaus können Benutzer die Synchronisierung innerhalb der App manuell initiieren. 

Das Unternehmensportal für Windows 10 stellt auch eine Aktualisierungsschaltfläche bereit, damit der Benutzer den Inhalt in der App jederzeit aktualisieren kann. 

## <a name="notices"></a>Benachrichtigungen

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->

Apple hat angekündigt, dass sie ab Frühjahr 2017 bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwingen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->

Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Vorschauportal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Was für APPX in Intune unter Azure bereitsteht <!-- 1000270 -->

Als Teil der Migration zu Intune unter Azure werden wir drei APPX-Änderungen vornehmen:

1. Einen neuen APPX-App-Typ in der klassischen Intune-Verwaltungskonsole hinzufügen, der nur für MDM-registrierte Geräte bereitgestellt werden kann
2. Den vorhandenen APPX-App-Typ nur für PCs wiederverwenden, die über den Intune PC-Agent verwaltet werden
3. Alle vorhandenen APPX-Formate in MDM-Formate mit der Migration konvertieren

Diese Änderungen werden keine Ihrer vorhandenen Bereitstellungen auf Geräte beeinflussen, die über den Intune PC-Agent verwaltet werden. Nach der Migration können Sie diese migrierten APPX-Formate auf allen neuen Geräten bereitstellen, die über den Intune PC-Agent verwaltet wird und die zuvor noch nicht zugewiesen wurden.

Nach der Migration müssen Sie die APPX erneut als PC-APPX hochladen, wenn Sie neue PC-Bereitstellungen machen möchten. Weitere Informationen finden Sie unter [Appx changes in Intune on Azure (APPX-Änderungen in Intune unter Azure)](https://aka.ms/appxchange) im Intune-Support-Teamblog.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche in Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/intune/what-is-intune) an.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Unterstützung für verwaltete Konfigurationsoptionen für Android-Apps <!-- 621621 -->

Sie können Android-Apps im Play Store konfigurieren, die verwaltete Konfigurationsoptionen unterstützen.  Mit diesem Feature können Sie die Liste der Konfigurationswerte anzeigen, die von einer App unterstützt werden. Zudem wird eine übersichtliche, hochwertige Benutzeroberfläche bereitgestellt, damit diese Werte konfiguriert werden können.

### <a name="remote-assistance-for-android-devices----675418---"></a>Remoteunterstützung für Android-Geräte <!-- 675418 -->

In Intune wird die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwendet, damit Sie Ihren Benutzern, die Android-Geräte ausführen, Remoteunterstützung bieten können.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Vorkonfigurieren von Geräteberechtigungen für Android for Work-Apps <!-- 621614 -->

Für Apps, die für Android for Work-Gerätearbeitsprofile bereitgestellt werden, können Sie den Berechtigungszustand für einzelne Apps konfigurieren. Standardmäßig fordern Android-Apps, die Geräteberechtigungen erfordern (z. B. Zugriff auf den Standort oder die Gerätekamera), die Benutzer zum Annehmen oder Ablehnen der Berechtigungen auf.  Wenn eine App z. B. das Gerätemikrofon verwendet, wird der Endbenutzer aufgefordert, der App die Berechtigung zur Verwendung des Mikrofons zu erteilen. Dieses Feature gestattet es Ihnen, die Berechtigungen im Namen des Endbenutzers zu definieren.  Der Administrator kann Berechtigungen für Folgendes konfigurieren:

- Automatische Ablehnung ohne Benachrichtigung des Benutzers
- Automatische Genehmigung ohne Benachrichtigung des Benutzers
- Aufforderung des Benutzers zur Annahme oder Ablehnung

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Definieren einer App-spezifischen PIN für Android for Work-Geräte <!--728976-->

Sie können eine Kennungsrichtlinie definieren, die nur für Apps im Arbeitsprofil für Geräte mit Android 7.0 und höher gilt, die als Android for Work-Geräte verwaltet werden.  Zu den Optionen gehören:

- Definieren einer geräteweiten Kennungsrichtline – Dies ist die vom Endbenutzer zu verwendende Kennung, um sein gesamtes Gerät zu entsperren.
- Definieren einer Kennungrichtlinie für das Arbeitsprofil – Benutzer werden zur Eingabe einer Kennung aufgefordert, sobald eine App im Arbeitsprofil geöffnet wird.
- Definieren einer Geräterichtlinie und einer Arbeitsprofilrichtlinie – Die IT-Abteilung hat die Möglichkeit, eine gerätebezogene und eine arbeitsprofilbezogene Kennungsrichtlinie mit unterschiedlicher Stärke zu erstellen (z. B. eine vierstellige PIN zum Entsperren des Geräts, aber eine sechsstellige PIN zum Öffnen einer arbeitsbezogenen App).

>[!NOTE]
> Diese Option ist nur unter Android 7.0 und höher verfügbar.  Standardmäßig hat der Endbenutzer die Möglichkeit, die beiden separat definierten PINs zu verwenden oder diese zu einer PIN zu kombinieren, die die Stärke der jeweils stärkeren PIN übernimmt.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Verwalten von Kennwort und anderen Einstellungen für Android for Work <!--1102534-->

Wir fügen eine neue Einschränkungsrichtlinie für Android for Work-Geräte hinzu, mit der Sie Kennwort- und Arbeitsprofileinstellungen auf Android for Work-Geräten verwalten können.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Neue Filterrichtlinie für Webinhalte für iOS-Geräte <!-- 723832 -->

Sie können steuern, welche Websites Benutzer von iOS-Geräten mithilfe einer der folgenden zwei Methoden besuchen können:

  - Zulässige und blockierte URLs mit dem integrierten Webinhaltsfilter von Apple hinzufügen
  - Erlauben, dass nur auf bestimmte Websites vom Safari-Browser aus zugegriffen werden darf. Lesezeichen werden in Safari für jede Website erstellt, die Sie angeben.

### <a name="apple-school-manager-asm-support---748864--"></a>Unterstützung für Apple School Manager (ASM)<!--748864-->

Intune unterstützt die Verwendung von Apple Schule Manager (ASM) anstelle des Apple-Programms zur Geräteregistrierung, um die integrierte Registrierung von iOS-Geräten zu ermöglichen. ASM-Onboarding ist erforderlich, um die Classroom-App für gemeinsam genutzte iPads zu verwenden. Zudem ist es erforderlich, um das Synchronisieren von Daten von ASM zu Azure Active Directory über SDS (Microsoft School Data Sync) zu aktivieren.  

### <a name="shared-ipad-support---770395-1044681---"></a>Unterstützung gemeinsam genutzter iPads <!--770395, 1044681 -->

Intune unterstützt die Konfiguration des Modus für gemeinsam genutzte iPads im Registrierungsprofil für das Apple-Geräteregistrierungsprogramm oder Apple School Manager. Mit dieser Einstellung können sich mehrere verwaltete Apple-IDs auf demselben Gerät anmelden.

Wir werden auch die Unterstützung für die Verwaltung der Classroom-App (iOS) erweitern, um Schüler und Studenten einzubeziehen, die sich mithilfe ihrer verwalteten Apple-ID auf gemeinsam genutzten iPads anmelden.

### <a name="new-windows-device-restriction-settings---978585--"></a>Neue Einstellungen zur Einschränkung für Windows-Geräte <!--978585-->

Es werden Einstellungen zum Windows-Geräteeinschränkungsprofil hinzugefügt, das Features wie drahtlose Anzeigen, Geräteerkennung, Programmumschaltung und Fehlermeldungen von SIM-Karten steuert.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Office 365 ProPlus-App für Windows 10-Geräte verfügbar <!--1121362-->

Wir fügen den neuen Office 365 ProPlus-Anwendungstyp hinzu, der das Zuweisen von Office 365 ProPlus-Apps zu Windows 10-Geräten vereinfacht. Darüber hinaus erhalten Sie die Möglichkeit, Microsoft Project und Microsoft Visio zu installieren, wenn Sie über die entsprechenden Lizenzen verfügen. Die gewünschten Apps werden gebündelt und in der Intune-Konsole als einzelne App in der App-Liste angezeigt.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Neue Liste für „Zulassen/Blockieren“ für den Managed Browser <!--682960-->

Sie erhalten die Möglichkeit, die Liste für „Zulassen/Blockieren“ von Domänen und URLs für den Managed Browser mit den Einstellungen für die Intune-Anwendungskonfiguration im Azure-Portal zu konfigurieren. Dies kann für den Managed Browser unabhängig davon verwaltet werden, ob er auf einem verwalteten oder nicht verwalteten Gerät verwendet wird.

### <a name="new-app-configuration-capabilities----677969---"></a>Neue Funktionen für die App-Konfiguration <!-- 677969 -->

Dieses Feature ist vergleichbar mit der App-Konfiguration zur Verwaltung mobiler Geräte (Mobile Device Management, MDM). Mit diesem Feature können Administratoren weitere App-Konfigurationswerte als nur die App-Konfigurationswerte anwenden, die über MAM-Schutzrichtlinien ohne Registrierungskanal zur Verfügung stehen.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Neue Bedingungen für App-Schutzrichtlinien für MAM <!--679864-->

Sie erhalten die Möglichkeit, eine Anforderung für MAM ohne Registrierung von Benutzern über die Admin Console festzulegen, die Folgendes erzwingt:

- Minimale Anwendungsversion
- Minimale Betriebssystemversion
- Mindestversion für Intune App SDK für die Zielanwendung (nur iOS)

Dieses Feature wird für Android und iOS zur Verfügung gestellt. Intune unterstützt die Durchsetzung einer Mindestversion für Betriebssystemplattformen, Anwendungen und das Intune App SDK. Unter iOS können Anwendungen mit integriertem SDK auch eine Durchsetzung einer Mindestversion auf SDK-Ebene festlegen.

Der Benutzer kann nicht auf die Zielanwendung zugreifen, wenn die Mindestanforderungen der App-Schutzrichtlinie auf den drei oben aufgeführten verschiedenen Ebenen nicht erfüllt werden. An diesem Punkt kann der Benutzer entweder sein Konto entfernen (für Anwendungen mit mehreren Identitäten), die Anwendung schließen und/oder seine Betriebssystem- bzw. Anwendungsversion aktualisieren, um die Anforderungen zu erfüllen.

Darüber hinaus erhalten Sie die Möglichkeit, zusätzliche Einstellungen über die Verwaltungskonsole zu konfigurieren, um eine nicht blockierende Benachrichtigung bereitzustellen, die ein Upgrade des Betriebssystems oder der Anwendung empfiehlt. Diese Benachrichtigung kann geschlossen und die Anwendung wie gewohnt verwendet werden.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Ändern der MDM-Autorität ohne Aufhebung der Registrierung für verwaltete Geräte <!--1103950-->

Sie erhalten die Möglichkeit zur Änderung Ihrer MDM-Autorität, ohne sich an den Microsoft Support wenden und die Aufhebung der Registrierung sowie die erneute Registrierung vorhandener verwalteten Geräte durchführen zu müssen. In der Configuration Manager-Konsole können Sie Ihre MDM-Autorität von der Festlegung auf Configuration Manager (hybrid) in Microsoft Intune (eigenständig) oder umgekehrt ändern.


### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).

