---
title: Early Edition | Microsoft-Dokumentation
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Die Early Edition für Microsoft Intune – Februar 2017

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
> Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisieren der Unternehmensportal-Website<!--753980-->
Die Unternehmensportal-Website wird Apps unterstützen, die für Benutzer bestimmt sind, die über keine verwalteten Geräte verfügen. Die Website ist mit anderen Microsoft-Produkten und -Diensten durch ein gegensätzliches Farbschema, dynamische Illustrationen und ein „Hamburger-Menü“ ![Kleines Bild des Hamburger-Menüs, das nun in der linken oberen Ecke des Unternehmensportals zu finden ist](./media/CP_hamburger_menu.png) verbunden, das Kontaktinformationen für den Helpdesk sowie Informationen für vorhandene verwaltete Geräte enthält. Die Angebotsseite wird neu angeordnet, um Apps hervorzuheben, die für Benutzer verfügbar sind, und mit einer Karussellsicht für empfohlene und kürzlich aktualisierte Apps. Sie finden Vorher- und Nachherbilder auf der Seite [Änderungen an der Intune App-Benutzeroberfläche](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Neue Anleitung für das Windows 10-Unternehmensportal <!--713927-->
Ab März bietet das Unternehmensportal für Windows 10 eine geführte Intune-Anleitung für Geräte, die nicht identifiziert oder registriert wurden. Die neue Anleitung umfasst Schritt-für-Schritt-Anweisungen für den Benutzerbuild von Windows 10, mit denen die AAD-Registrierung (erforderlich zur Identifikation für Features zum bedingten Zugriff) und die MDM-Registrierung (erforderlich für Features zur Geräteverwaltung) erläutert werden. Die geführte Anleitung ist optional und auf der Startseite des Unternehmensportals zu finden. Benutzer können die App weiterhin verwenden, auch ohne die Registrierung und Anmeldung abzuschließen, möglicherweise ist aber der Funktionsumfang eingeschränkt.

###

## <a name="notices"></a>Benachrichtigungen

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Die Gruppenmigration erfordert keine Updates für Gruppen oder Richtlinien für iOS-Geräte <!--898837-->
Es wird während der Migration auf Azure Active Directory-Gerätegruppen für jede Intune-Gerätegruppe, die durch ein Profil für die Unternehmensgeräteregistrierung vorab zugewiesen ist, eine entsprechende dynamische Gerätegruppe in AAD auf Grundlage des Profilnamens der Unternehmensgeräteregistrierung erstellt. Dadurch wird sichergestellt, dass während der Registrierung der Geräte diese automatisch gruppiert werden und die gleichen Richtlinien und Apps wie die ursprüngliche Intune-Gruppe erhalten.

Sobald ein Mandant den Migrationsprozess zur Gruppierung und Adressierung beitritt, erstellt Intune automatisch eine dynamische AAD-Gruppe, die einer Intune-Gruppe entspricht, die das Ziel eines Profils für die Unternehmensgeräteregistrierung ist. Wenn der Intune-Administrator die Intune-Gruppe löscht, auf die abgezielt wurde, wird die entsprechende dynamische AAD-Gruppe nicht gelöscht. Die Mitglieder der Gruppe sowie die dynamische Abfrage werden deaktiviert, jedoch wird die Gruppe selbst so lange beibehalten, bis der IT-Administrator diese über das AAD-Portal entfernt.

Genauso wird Intune eine dynamische Gruppe erstellen, wenn der IT-Administrator die Einstellung ändert, auf welche Gruppe durch das Profil für die Unternehmensgeräteregistrierung abgezielt wird, die die neue Profilzuweisung widerspiegelt, jedoch nicht die für die alte Zuweisung erstellte dynamische Gruppe entfernen.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Neue MDM-Serveradresse für Windows-Geräte <!--893007-->
Windows- und Windows Phone-Benutzer sind beim Versuch, ein Gerät zu registrieren, nicht erfolgreich, wenn Sie als MDM-Serveradresse __manage.microsoft.com__ eingeben (wenn Sie dazu aufgefordert werden). Die MDM-Serveradresse ändert sich von __manage.microsoft.com__ zu __enrollment.manage.microsoft.com__. Informieren Sie Ihre Benutzer, dass Sie nun als MDM-Serveradresse __enrollment.manage.microsoft.com__ verwenden sollen, wenn Sie zur Eingabe während der Registrierung eines Windows- oder Windows Phone-Geräts aufgefordert werden. Dieses Update erfordert, dass ein CNAME-Eintrag in DNS, der __EnterpriseEnrollment.contoso.com__ auf __manage.microsoft.com__ umleitet, durch einen CNAME-Eintrag im DNS ersetzt wird, der __EnterpriseEnrollment.contoso.com__ auf __EnterpriseEnrollment-s.manage.microsoft.com__ umleitet. Weitere Informationen zu dieser Änderung finden Sie unter [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Neue Benutzeroberfläche für die Unternehmensportal-App für Android <!--621622-->
Ab März befolgt die Unternehmensportal-App für Android die [material design guidelines (Richtlinien für Materialdesign)](https://material.io/guidelines/material-design/introduction.html), um ein moderneres Erscheinungsbild zu vermitteln. Diese verbesserte Benutzeroberfläche enthält Folgendes:

* __Farben__: Die Farben der Registerkartentitel können mithilfe Ihrer benutzerdefinierten Farbpalette angepasst werden.
* __Schnittstelle__: Die Schaltflächen „Empfohlene Apps“ und „Alle Apps“ wurden in der Registerkarte „Apps“ aktualisiert. Die Schaltfläche „Suche“ ist nun eine unverankerte interaktive Schaltfläche.
* __Navigation__: Alle Apps zeigen die Registerkartenansicht „Featured“ (Highlights), „Alle“ und „Kategorien“ für die einfachere Navigation.
* __Dienst__: Für die Registerkarten „Meine Geräte“ und „An IT-Abteilung wenden“ wurde die Lesbarkeit verbessert.

Sie finden Vorher- und Nachherbilder auf der Seite [Änderungen an der Intune App-Benutzeroberfläche](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Zuordnen mehrerer Verwaltungstools mit dem Windows Store für Unternehmen <!--926135-->
Wenn Sie mehr als ein Verwaltungstool zum Bereitstellen von Windows Store für Unternehmen-Apps verwenden, konnten Sie vorher nur eine App dem Windows Store für Unternehmen zuordnen. Nun können Sie mehrere Verwaltungstools dem Store zuordnen, z.B. Intune und Configuration Manager. Einzelheiten finden Sie unter [Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden, mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche in Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Februar 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Einschränken der Registrierung von Mobilgeräten <!--747600, 795782-->
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.

* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.  
* Für iOS und Android gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Anzeigen aller Aktionen auf verwalteten Geräten <!--677150-->
Ein neuer Bericht über __Geräteaktionen__ zeigt, wer Remoteaktionen wie das Zurücksetzen auf Werkseinstellungen auf Geräten ausgeführt hat sowie den Status dieser Aktion.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->
Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

#### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Anzeigen von Gerätekategoriern <!--814654-->
Sie können nun die Gerätekategorie als Spalte in der Geräteliste anzeigen. Sie können die Kategorie auch im Abschnitt „Eigenschaften“ des Blatts „Geräteeigenschaften“ bearbeiten.

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



<!--HONumber=Feb17_HO2-->


