---
title: Early Edition | Microsoft-Dokumentation
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>Die Early Edition für Microsoft Intune – Januar

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
> Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="actions-for-non-compliance---730266--"></a>Aktionen bei Inkompatibilität <!--730266-->
_Aktionen bei Inkompatibilität_ ist ein neues Feature für Kompatibilitätsrichtlinien, mit der Sie Aktionen für Geräte einrichten können, die nicht kompatibel sind. Sie können eine oder mehrere Aktionen angeben und den Zeitraum festlegen, in dem diese Aktionen ausgeführt werden müssen. Sie können z.B. Benutzer von Geräten per E-Mail benachrichtigen, sobald ihr Gerät inkompatibel wurde. Sie können auch den Zugriff nicht kompatibler Geräte auf Unternehmensressourcen sperren, nachdem die Geräte während einer dreitägigen Karenzzeit per bedingtem Zugriff zugreifen konnten.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Konsoleninterne Berichte für MAM ohne Registrierung <!--677961-->
Es wurden neue App-Schutzberichte sowohl für registrierte als auch nicht registrierte Geräte hinzugefügt. Erfahren Sie mehr über das [Überwachen von Verwaltungsrichtlinien für mobile Apps mit Intune](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Bedingter Zugriff für MAM mit SharePoint Online <!--679339-->
Sie können den Zugriff auf SharePoint Online für Apps, die von den Intune-Verwaltungsrichtlinien für mobile Apps (Mobile App Management, MAM) nicht unterstützt werden, blockieren.  Sie können in die Verwendung von Intune Mobile App Management (MAM) im Azure-Portal einsteigen. Suchen Sie nach dem Abschnitt __Bedingter Zugriff__ im Blatt __Einstellungen__. Hier finden Sie auch die Option für SharePoint Online. Dieses Feature wird getrennt vom Rest des Service Release ausgeliefert. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-Unterstützung <!--694397-->
Intune unterstützt und verwaltet jetzt Android 7.1.1 vollständig.

## <a name="notices"></a>Benachrichtigungen

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standardmäßige Verwaltung von Windows-Desktopgeräten über Windows-Einstellungen <!--663050-->
Das Standardverhalten für die Registrierung von Windows 10-Geräten ändert sich. Neue Registrierungen erfolgen gemäß dem typischen Registrierungsprozess über den MDM-Agent, nicht mehr über den PC-Agent.

Windows 10-Desktopbenutzer erhalten auf der Unternehmensportal-Website Registrierungsanweisungen, die sie durch den Prozess zum Hinzufügen von Windows 10-Desktopcomputern als mobile Geräte leiten. Dies wirkt sich nicht auf aktuell bereits registrierte PCs aus, und Ihre Organisation kann [auf Wunsch](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) Windows 10-Desktops weiterhin über den PC-Agent verwalten.

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Links im Unternehmensportal für iOS öffnen sich innerhalb der App <!--665954-->
Links in der Unternehmensportal-App für iOS, einschließlich Links zu Dokumentationen und Apps, werden über eine In-App-Ansicht von Safari direkt in der Unternehmensportal-App geöffnet. Dieses Update wird getrennt vom Dienstupdate im Januar ausgeliefert.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbesserte Unterstützung der Verwaltung mobiler Apps für das selektive Zurücksetzen <!--581242-->
Endbenutzer erhalten zusätzliche Anleitungen, um erneut Zugriff auf Geschäfts-, Schul- oder Unidaten zu erhalten, wenn diese Daten aufgrund der Richtlinie „Offline-Intervall, bevor App-Daten zurückgesetzt werden“ automatisch entfernt wurden.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Neue Dokumentation für App-Schutzrichtlinien <!--583398-->
Wir haben unsere Dokumentation für Administratoren und App-Entwickler aktualisiert, die App-Schutzrichtlinien (so genannte MAM-Richtlinien) mit dem Intune App Wrapping Tool oder dem Intune App SDK in ihren iOS- und Android-Apps aktivieren möchten.

Die folgenden Artikel wurden aktualisiert:

* [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Vorbereiten von iOS-Apps für die Verwaltung mobiler Anwendungen mit dem Intune App Wrapping Tool](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Erste Schritte mit dem Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Intune App SDK für iOS – Entwicklerhandbuch](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Folgende Artikel wurden der Dokumentbibliothek neu hinzugefügt:

* [Intune App SDK-Cordova-Plug-In](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK-Xamarin-Komponente](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Statusanzeige beim Starten des Unternehmensportals in iOS <!--665978-->
Für das Unternehmensportal für iOS wurde eine Statusanzeige auf dem Startbildschirm eingeführt, um den Benutzer über die Prozesse zu informieren, die gerade geladen werden. Die Einführung der Statusanzeige, die das Drehfeld ersetzt, wird in mehreren Phasen erfolgen. Dies bedeutet, dass einige Ihrer Benutzer bereits die neue Statusanzeige sehen, andere dagegen noch das Drehfeld.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche in Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="january-2017"></a>Januar 2017

#### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Zuweisen von Branchen-Apps unabhängig vom Registrierungsstatus von Geräten <!--748803-->
Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn ein Benutzergerät nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren.

### <a name="december-2016"></a>Dezember 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integration der Telekommunikationsausgaben in der öffentlichen Vorschau des Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Dec16_HO4-->


