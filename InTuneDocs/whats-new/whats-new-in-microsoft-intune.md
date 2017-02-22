---
title: Neuheiten | Microsoft-Dokumentation
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 053cf0a1b5d06496397b36cbd1a7ebdce420fed3
ms.openlocfilehash: 5158d58c32066ea720335a878fef87451542c195


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Neuerungen in Microsoft Intune – Januar 2017
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Konsoleninterne Berichte für MAM ohne Registrierung <!--677961-->
Es wurden neue App-Schutzberichte sowohl für registrierte als auch nicht registrierte Geräte hinzugefügt. Erfahren Sie mehr über das [Überwachen von Verwaltungsrichtlinien für mobile Apps mit Intune](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-Unterstützung <!--694397-->
Intune unterstützt und verwaltet jetzt Android 7.1.1 vollständig.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Lösen von Problemen, wenn iOS-Geräte inaktiv sind oder die Verwaltungskonsole nicht mit ihnen kommunizieren kann <!--unknown-->
Wenn Geräte von Benutzern keinen Kontakt mehr mit Intune haben, können Sie neue Schritte zur Problembehandlung bereitstellen, damit sie erneuten Zugriff auf Unternehmensressourcen gewinnen können. Weitere Informationen finden Sie unter [Geräte sind inaktiv oder die Verwaltungskonsole kann nicht mit ihnen kommunizieren](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Benachrichtigungen

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standardmäßige Verwaltung von Windows-Desktopgeräten über Windows-Einstellungen <!--663050-->
Das Standardverhalten für die Registrierung von Windows 10-Geräten ändert sich. Neue Registrierungen erfolgen gemäß dem typischen Registrierungsprozess über den MDM-Agent, nicht mehr über den PC-Agent.

Windows 10-Desktopbenutzer erhalten auf der Unternehmensportal-Website Registrierungsanweisungen, die sie durch den Prozess zum Hinzufügen von Windows 10-Desktopcomputern als mobile Geräte leiten. Dies wirkt sich nicht auf aktuell bereits registrierte PCs aus, und Ihre Organisation kann [auf Wunsch](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) Windows 10-Desktops weiterhin über den PC-Agent verwalten.

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbesserte Unterstützung der Verwaltung mobiler Apps für das selektive Zurücksetzen <!--581242-->
Endbenutzer erhalten zusätzliche Anleitungen, um erneut Zugriff auf Geschäfts-, Schul- oder Unidaten zu erhalten, wenn diese Daten aufgrund der Richtlinie „Offline-Intervall, bevor App-Daten zurückgesetzt werden“ automatisch entfernt wurden.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Links im Unternehmensportal für iOS öffnen sich innerhalb der App <!--665954-->
Links in der Unternehmensportal-App für iOS, einschließlich Links zu Dokumentationen und Apps, werden über eine In-App-Ansicht von Safari direkt in der Unternehmensportal-App geöffnet. Dieses Update wird getrennt vom Dienstupdate im Januar ausgeliefert.

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisieren der Unternehmensportal-Website<!--753980-->
Ab Februar unterstützt die Unternehmensportal-Website Apps, die für Benutzer bestimmt sind, die über keine verwalteten Geräte verfügen. Die Website ist mit anderen Microsoft-Produkten und -Diensten durch ein gegensätzliches Farbschema, dynamische Illustrationen und ein „Hamburger-Menü“ ![Unternehmensportal-Website Hamburger-Menü](./media/CP_hamburger_menu.png) verbunden, das Kontaktinformationen für den Helpdesk sowie Informationen für vorhandene verwaltete Geräte enthält. Die Angebotsseite wird neu angeordnet, um Apps hervorzuheben, die für Benutzer verfügbar sind, und mit einer Karussellsicht für empfohlene und kürzlich aktualisierte Apps. Auf der Seite [Änderungen an der Intune App-Benutzeroberfläche](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017) finden Sie Vorher-nachher-Bilder.

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

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Statusanzeige beim Starten des Unternehmensportals in iOS <!--665978-->
Für das Unternehmensportal für iOS wurde eine Statusanzeige auf dem Startbildschirm eingeführt, um den Benutzer über die Prozesse zu informieren, die gerade geladen werden. Die Einführung der Statusanzeige, die das Drehfeld ersetzt, wird in mehreren Phasen erfolgen. Dies bedeutet, dass einige Ihrer Benutzer bereits die neue Statusanzeige sehen, andere dagegen noch das Drehfeld.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Neuigkeiten in der öffentlichen Vorschau der neuen Intune-Administratoroberfläche auf Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Neuigkeiten in der Intune-Vorschau in Azure finden Sie [hier](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuigkeiten in der Azure-Vorschau](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Neuheiten – Archiv](whats-new-archive.md)



<!--HONumber=Feb17_HO1-->


