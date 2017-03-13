---
title: Neuheiten | Microsoft-Dokumentation
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: cb1679deda0ba325ee3bd7288713f12317489006
ms.openlocfilehash: 37d44dc2752815ef7abf47e5d4a658a126892a86
ms.lasthandoff: 02/18/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Neuheiten in Microsoft Intune – Februar 2017
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisieren der Unternehmensportal-Website<!--753980-->
Die Unternehmensportal-Website wird Apps unterstützen, die für Benutzer bestimmt sind, die über keine verwalteten Geräte verfügen. Die Website ist mit anderen Microsoft-Produkten und -Diensten durch ein gegensätzliches Farbschema, dynamische Illustrationen und ein „Hamburger-Menü“ ![Kleines Bild des Hamburger-Menüs, das nun in der linken oberen Ecke des Unternehmensportals zu finden ist](./media/CP_hamburger_menu.png) verbunden, das Kontaktinformationen für den Helpdesk sowie Informationen für vorhandene verwaltete Geräte enthält. Die Angebotsseite wird neu angeordnet, um Apps hervorzuheben, die für Benutzer verfügbar sind, und mit einer Karussellsicht für empfohlene und kürzlich aktualisierte Apps. Sie finden Vorher- und Nachherbilder auf der Seite [Änderungen an der Intune App-Benutzeroberfläche](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Neue Anleitung für das Windows 10-Unternehmensportal <!--713927-->
Ab März bietet das Unternehmensportal für Windows 10 eine geführte Intune-Anleitung für Geräte, die nicht identifiziert oder registriert wurden. Die neue Anleitung umfasst Schritt-für-Schritt-Anweisungen für den Benutzerbuild von Windows 10, mit denen die AAD-Registrierung (erforderlich zur Identifikation für Features zum bedingten Zugriff) und die MDM-Registrierung (erforderlich für Features zur Geräteverwaltung) erläutert werden. Die geführte Anleitung ist optional und auf der Startseite des Unternehmensportals zu finden. Benutzer können die App weiterhin verwenden, auch ohne die Registrierung und Anmeldung abzuschließen, möglicherweise ist aber der Funktionsumfang eingeschränkt.

## <a name="notices"></a>Benachrichtigungen

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Die Gruppenmigration erfordert keine Updates für Gruppen oder Richtlinien für iOS-Geräte <!--898837-->
Es wird während der Migration auf Azure Active Directory-Gerätegruppen für jede Intune-Gerätegruppe, die durch ein Profil für die Unternehmensgeräteregistrierung vorab zugewiesen ist, eine entsprechende dynamische Gerätegruppe in AAD auf Grundlage des Profilnamens der Unternehmensgeräteregistrierung erstellt. Dadurch wird sichergestellt, dass während der Registrierung der Geräte diese automatisch gruppiert werden und die gleichen Richtlinien und Apps wie die ursprüngliche Intune-Gruppe erhalten.

Sobald ein Mandant den Migrationsprozess zur Gruppierung und Adressierung beitritt, erstellt Intune automatisch eine dynamische AAD-Gruppe, die einer Intune-Gruppe entspricht, die das Ziel eines Profils für die Unternehmensgeräteregistrierung ist. Wenn der Intune-Administrator die Intune-Gruppe löscht, auf die abgezielt wurde, wird die entsprechende dynamische AAD-Gruppe nicht gelöscht. Die Mitglieder der Gruppe sowie die dynamische Abfrage werden deaktiviert, jedoch wird die Gruppe selbst so lange beibehalten, bis der IT-Administrator diese über das AAD-Portal entfernt.

Genauso wird Intune eine dynamische Gruppe erstellen, wenn der IT-Administrator die Einstellung ändert, auf welche Gruppe durch das Profil für die Unternehmensgeräteregistrierung abgezielt wird, die die neue Profilzuweisung widerspiegelt, jedoch nicht die für die alte Zuweisung erstellte dynamische Gruppe entfernen.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standardmäßige Verwaltung von Windows-Desktopgeräten über Windows-Einstellungen <!--663050-->
Das Standardverhalten für die Registrierung von Windows 10-Geräten ändert sich. Neue Registrierungen erfolgen gemäß dem typischen Registrierungsprozess über den MDM-Agent, nicht mehr über den PC-Agent. Windows 10-Desktopbenutzer erhalten auf der Unternehmensportal-Website Registrierungsanweisungen, die sie durch den Prozess zum Hinzufügen von Windows 10-Desktopcomputern als mobile Geräte leiten. Dies wirkt sich nicht auf aktuell bereits registrierte PCs aus, und Ihre Organisation kann [auf Wunsch](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) Windows 10-Desktops weiterhin über den PC-Agent verwalten.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbesserte Unterstützung der Verwaltung mobiler Apps für das selektive Zurücksetzen <!--581242-->
Endbenutzer erhalten zusätzliche Anleitungen, um erneut Zugriff auf Geschäfts-, Schul- oder Unidaten zu erhalten, wenn diese Daten aufgrund der Richtlinie „Offline-Intervall, bevor App-Daten zurückgesetzt werden“ automatisch entfernt wurden.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Links im Unternehmensportal für iOS öffnen sich innerhalb der App <!--665954-->
Links in der Unternehmensportal-App für iOS, einschließlich Links zu Dokumentationen und Apps, werden über eine In-App-Ansicht von Safari direkt in der Unternehmensportal-App geöffnet. Dieses Update wird getrennt vom Dienstupdate im Januar ausgeliefert.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Neue MDM-Serveradresse für Windows-Geräte <!--893007-->
Windows- und Windows Phone-Benutzer sind beim Versuch, ein Gerät zu registrieren, nicht erfolgreich, wenn Sie als MDM-Serveradresse __manage.microsoft.com__ eingeben (wenn Sie dazu aufgefordert werden). Die MDM-Serveradresse ändert sich von __manage.microsoft.com__ zu __enrollment.manage.microsoft.com__. Informieren Sie Ihre Benutzer, dass Sie nun als MDM-Serveradresse __enrollment.manage.microsoft.com__ verwenden sollen, wenn Sie zur Eingabe während der Registrierung eines Windows- oder Windows Phone-Geräts aufgefordert werden. Für das CNAME-Setup sind keine Änderungen erforderlich. Weitere Informationen zu dieser Änderung finden Sie unter [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Neue Benutzeroberfläche für die Unternehmensportal-App für Android <!--621622-->
Ab März befolgt die Unternehmensportal-App für Android die [material design guidelines (Richtlinien für Materialdesign)](https://material.io/guidelines/material-design/introduction.html), um ein moderneres Erscheinungsbild zu vermitteln. Diese verbesserte Benutzeroberfläche enthält Folgendes:

* __Farben__: Die Farben der Registerkartentitel können mithilfe Ihrer benutzerdefinierten Farbpalette angepasst werden.
* __Schnittstelle__: Die Schaltflächen „Empfohlene Apps“ und „Alle Apps“ wurden in der Registerkarte „Apps“ aktualisiert. Die Schaltfläche „Suche“ ist nun eine unverankerte interaktive Schaltfläche.
* __Navigation__: Alle Apps zeigen die Registerkartenansicht „Featured“ (Highlights), „Alle“ und „Kategorien“ für die einfachere Navigation.
* __Dienst__: Für die Registerkarten „Meine Geräte“ und „An IT-Abteilung wenden“ wurde die Lesbarkeit verbessert.

Sie finden Vorher- und Nachherbilder auf der Seite [Änderungen an der Intune App-Benutzeroberfläche](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Zuordnen mehrerer Verwaltungstools mit dem Windows Store für Unternehmen <!--926135-->
Wenn Sie mehr als ein Verwaltungstool zum Bereitstellen von Windows Store für Unternehmen-Apps verwenden, konnten Sie vorher nur eine App dem Windows Store für Unternehmen zuordnen. Nun können Sie mehrere Verwaltungstools dem Store zuordnen, z.B. Intune und Configuration Manager. Einzelheiten finden Sie unter [Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden, mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Neuigkeiten in der öffentlichen Vorschau der neuen Intune-Administratoroberfläche auf Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/intune-azure/introduction/whats-new) an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Neuigkeiten in der Intune-Vorschau in Azure finden Sie [hier](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuigkeiten in der Azure-Vorschau](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Neuheiten – Archiv](whats-new-archive.md)

