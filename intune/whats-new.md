---
title: Neuerungen in Microsoft Intune
titleSuffix: Intune on Azure
description: Erfahren Sie, welche Neuerungen es im Intune-Azure-Portal gibt
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dec4fb1d373f49c1f6c15b1f2a9acb2f8d20138d
ms.sourcegitcommit: be12974a7eaa4ce9cffe45aabe456c858d582e20
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Neuerungen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Erfahren Sie jede Woche, welche Neuerungen Microsoft Intune zu bieten hat. Sie erhalten auch Informationen zu [bevorstehenden Änderungen](#whats-coming), [wichtige Hinweise](#notices) zum Dienst und Informationen zu [vorherigen Versionen](whats-new-archive.md).

> [!Note]
> Viele diese Features werden letztlich auch für hybride Bereitstellungen mit Configuration Manager unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



## <a name="week-of-june-26th-2017"></a>Woche vom 26. Juni 2017

### <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Neuer rollenbasierter Administratorenzugriff für Intune-Administratoren <!-- 1099990 -->  
Eine neue Administratorrolle für den bedingten Zugriff wird hinzugefügt, um Azure AD-Richtlinien für den bedingten Zugriff zu erstellen, zu ändern und zu löschen. Vorher besaßen nur globale Administratoren und Sicherheitsadministratoren diese Berechtigung. Diese Rollenberechtigung kann Intune-Administratoren erteilt werden, damit sie Zugriff auf Richtlinien für den bedingten Zugriff haben.


### <a name="device-enrollment"></a>Geräteregistrierung
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Markieren von unternehmenseigenen Geräten mit Seriennummer <!-- 1215070 -->  
Intune unterstützt nun das Hochladen von iOS-, macOS- und Android-Seriennummern als IDs für unternehmenseigene Geräte. Sie können anhand von Seriennummern derzeit keine persönlichen Geräte für die Registrierung blockieren, da Seriennummern bei der Registrierung nicht überprüft werden. Die Funktion zum Blockieren persönlicher Geräte durch Seriennummer wird in Kürze veröffentlicht.


### <a name="device-management"></a>Geräteverwaltung
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Neue Remoteaktionen für iOS-Geräte <!-- 854689 -->
In dieser Version haben wir zwei neue remote Geräteaktionen für freigegebene iPad-Geräte hinzugefügt, die die Apple Classroom-App verwalten:

-   [Aktuellen Benutzer abmelden](device-logout-user.md): Meldet den aktuellen Benutzer eines von Ihnen ausgewählten iOS-Geräts aus.
-   [Benutzer entfernen](device-remove-user.md): Löscht einen von Ihnen ausgewählten Benutzer aus dem lokalen Cache eines iOS-Geräts.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Unterstützung für gemeinsam genutzte iPads mit der Classroom-App für iOS <!-- 1044681 -->
In diesem Release haben wir die Unterstützung für die Verwaltung der Classroom-App (iOS) erweitert, um Schüler und Studenten einzubeziehen, die sich mithilfe ihrer verwalteten Apple-ID auf gemeinsam genutzten iPads anmelden.


### <a name="app-management"></a>App-Verwaltung  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Änderungen an Integrierten Intune-Apps <!-- 1332306 -->

Zuvor enthielt Intune eine Reihe integrierter Apps, die Sie rasch zuweisen konnten. Auf Grundlage Ihrer Feedbacks haben wir diese Liste entfernt, und es werden keine integrierten Apps mehr angezeigt.
Wenn Sie jedoch schon integrierte Apps zugewiesen haben, werden sie noch immer auf der App-Liste angezeigt. Sie können diese Apps weiter nach Bedarf zuweisen.
In einer späteren Version möchten wir eine einfachere Methode zum Auswählen und Zuweisen integrierter Apps aus dem Intune-Portal integrieren.


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>Unterstützung für Offline-Apps aus dem Windows Store für Unternehmen <!--- 777044 --->
Offline-Apps, die Sie über den Windows Store für Unternehmen erworben haben, werden nun mit dem Intune-Portal synchronisiert. Sie können diese Apps dann für Geräte- oder Benutzergruppen bereitstellen. Offline-Apps werden durch Intune und nicht durch den Store installiert.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams ist jetzt Teil der App-basierten CA-Liste der genehmigten Apps <!-- 1257019 -->

Die Microsoft Teams-App für iOS und Android ist nun Bestandteil der genehmigten Apps für Richtlinien für den app-basierten bedingten Zugriff für Exchange und SharePoint Online. Im Azure-Portal kann die App über das Blatt „Intune-App-Schutz“ für alle Mandanten konfiguriert werden, die derzeit auf den app-basierten bedingten Zugriff zurückgreifen.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Verwaltete Browser- und App-Proxy-Integration <!-- 1287310 -->
 Der Intune Managed Browser kann nun mit dem Azure AD-Anwendungsproxydienst integriert werden, damit Benutzer auf interne Websites zugreifen können, auch wenn Sie remote arbeiten. Benutzer des Browsers geben einfach wie gewohnt die Website-URL ein, und der Managed Browser leitet die Anfrage über das Anwendungsproxy-Webgateway weiter. Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Neue App-Konfigurationseinstellungen für Intune Managed Browser <!-- 682951 -->
In dieser Version haben wir weitere Konfigurationen für die Intune Managed Browser-App für iOS und Android hinzugefügt. Die Standardhomepage und -lesezeichen für den Browser können mit einer App-Konfigurationsrichtlinie konfiguriert werden.
Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser](app-configuration-managed-browser.md).




### <a name="device-configuration"></a>Gerätekonfiguration  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Einstellungen für BitLocker für Windows 10 <!-- 951707 -->
Sie können jetzt die BitLocker-Einstellungen für Windows 10-Geräte, mithilfe eines neuen Intune Geräteprofils konfigurieren. Sie können z.B. anfordern, dass Geräte verschlüsselt werden und auch weitere Einstellungen konfigurieren, die angewendet werden, wenn BitLocker aktiviert wird.
Weitere Informationen finden Sie unter [Endpoint protection settings for Windows 10 and later (Endpoint Protection-Einstellungen für Windows 10 und höher)](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Neue Einstellungen für das Windows 10-Geräteeinschränkungsprofil <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

In dieser Version haben wir neue Einstellungen für das Windows 10-Geräteeinschränkungsprofil in folgenden Kategorien hinzugefügt:

 -  Windows Defender
-  Mobilfunk und Konnektivität
-  Gesperrter Bildschirm
-  Datenschutz
-  Suchen
-  Windows-Blickpunkt
-  Edgebrowser

Weitere Informationen zu Einstellungen für Windows 10 finden Sie unter [Einstellungen für Geräteeinschränkungen für Windows 10 und höher in Microsoft Intune](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>Woche vom 12. Juni 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Die Unternehmensportal-App für Android verfügt nun über eine neue Endbenutzererfahrung für App-Schutzrichtlinien <!--1305217-->
Auf Grundlage von Benutzerfeedback haben wir die Unternehmensportal-App für Android modifiziert, sodass sie nun die Schaltfläche **Auf Unternehmensinhalte zugreifen** besitzt. Der Hintergrund dazu ist, Endbenutzer daran zu hindern, unnötigerweise den Registrierungsprozess zu durchlaufen, wenn sie nur auf Apps zugreifen müssen, die App-Schutzrichtlinien unterstützen, eine Funktion der mobilen Anwendungsverwaltung von Intune. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Neue Menüaktion zum mühelosen Entfernen des Unternehmensportals <!--1164569-->
Basierend auf Benutzerfeedback wurde der Unternehmensportal-App für Android eine neue Menüaktion hinzugefügt, über die das Entfernen des Unternehmensportals von Ihrem Gerät eingeleitet werden kann. Über diese Aktion wird das Gerät aus der Intune-Verwaltung entfernt, damit die App vom Benutzer vom Gerät entfernt werden kann. Sie sehen diese Änderungen auf der Seite zu den [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md) und in der [Android-Endbenutzerdokumentation](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Verbesserungen bei der App-Synchronisierung mit dem Windows 10 Creators Update <!--676505-->

Die Unternehmensportal-App für Windows 10 löst nun automatisch eine Synchronisierung für App-Installationsanforderungen für Geräte mit dem Windows 10 Creators Update (Version 1703) aus. Dadurch wird das Problem beseitigt, dass App-Installationen während des Zustands „Synchronisierung ausstehend“ verzögert reagieren. Darüber hinaus können Benutzer die Synchronisierung innerhalb der App manuell initiieren. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Neue Anleitung für das Windows 10-Unternehmensportal <!---1058938--->

Die Unternehmensportal-App für Windows 10 bietet eine geführte Intune-Anleitung für Geräte, die nicht identifiziert oder registriert wurden. Die neue Anleitung umfasst Schritt-für-Schritt-Anweisungen, mit denen die Registrierung bei Azure Active Directory (erforderlich für Funktionen zum bedingten Zugriff) und die MDM-Registrierung (erforderlich für Funktionen zur Geräteverwaltung) durch den Benutzer erläutert werden. Auf die geführte Anleitung kann über die Hauptseite des Unternehmensportals zugegriffen werden. Benutzer können die App weiterhin verwenden, wenn die Registrierung und Anmeldung nicht abgeschlossen werden, haben jedoch lediglich Zugriff auf einen eingeschränkten Funktionsumfang.

Dieses Update ist nur auf Geräten unter Windows 10 Anniversary Update (Build 1607) oder höher sichtbar. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.

## <a name="week-of-june-5-2017"></a>Woche vom 5. Juni 2017

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Verwaltungskonsolen für Microsoft Intune und bedingten Zugriff allgemein verfügbar

Wir kündigen die allgemeine Verfügbarkeit der neuen Intune-Verwaltungskonsole in Azure und der Verwaltungskonsole für den bedingten Zugriff an. Über Intune in Azure können Sie jetzt alle Intune-Funktionen für die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) und mobiler Geräte (Mobile Device Management, MDM) zentral verwalten und die Azure AD-Zielgruppenbestimmung nutzen. Das Feature „Bedingter Zugriff“ in Azure führt umfassende Funktionen in Azure AD und Intune in einer einheitlichen Konsole zusammen. Aus administrativer Sicht ermöglicht Ihnen der Wechsel zur Azure-Plattform den Einsatz moderner Browser.

Intune wird in der Azure-Konsole auf portal.azure.com jetzt ohne die Bezeichnung **Vorschau** angezeigt.

Bestandskunden müssen derzeit keine Aktion ausführen, es sei denn, Sie haben im Nachrichtencenter eine Nachricht aus einer Reihe von Nachrichten erhalten, in der Sie aufgefordert werden, Maßnahmen zu ergreifen, damit wir Ihre Gruppen migrieren können. Sie haben möglicherweise im Nachrichtencenter auch den Hinweis erhalten, dass die Migration aufgrund von Fehlern unsererseits länger dauert. Wir arbeiten mit Volldampf daran, alle betroffenen Kunden zu migrieren.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Verbesserungen an den App-Kacheln in der Unternehmensportal-App für iOS
Wir haben das Design der App-Kacheln auf der Startseite entsprechend der Brandingfarbe geändert, die Sie für das Unternehmensportal festgelegt haben. Weitere Informationen finden Sie unter [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Kontoauswahl nun für die Unternehmensportal-App für iOS verfügbar
Benutzern von iOS-Geräten wird ggf. bei der Anmeldung beim Unternehmensportal unsere neue Kontoauswahl angezeigt, wenn sie für die Anmeldung bei anderen Microsoft-Anwendungen ihr Geschäfts-, Schul- oder Unikonto verwenden. Weitere Informationen finden Sie unter [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md).

## <a name="week-of-may-29-2017"></a>Woche vom 29. Mai 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Ändern der MDM-Autorität ohne Aufhebung der Registrierung für verwaltete Geräte <!--1103950-->

Sie können nun Ihre MDM-Autorität ändern, ohne sich an den Microsoft-Support wenden und die Aufhebung der Registrierung sowie die erneute Registrierung vorhandener verwalteten Geräte durchführen zu müssen. In der Configuration Manager-Konsole können Sie Ihre [MDM-Autorität ändern](/sccm/mdm/deploy-use/change-mdm-authority), und zwar von der Festlegung auf Configuration Manager (hybrid) in Microsoft Intune (eigenständig) oder umgekehrt.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Verbesserte Benachrichtigung für Samsung KNOX-Systemstart-PINs <!--1087143-->
Wenn Endbenutzer eine Systemstart-PIN für Samsung KNOX-Geräte festlegen müssen, um Kompatibilität hinsichtlich der Verschlüsselung zu erreichen, führt die für Endbenutzer angezeigte Benachrichtigung diese genau zu der Stelle in der App „Einstellungen“, wenn auf die Benachrichtigung getippt wird.  Zuvor hat die Benachrichtigung den Endbenutzer zum Bildschirm für die Kennwortänderung geführt.


### <a name="device-enrollment"></a>Geräteregistrierung

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Unterstützung für Apple School Manager (ASM) auf gemeinsam genutztem iPad<!-- 748864, 770395-->

Intune unterstützt jetzt die Verwendung von Apple Schule Manager (ASM) anstelle des Apple-Programms zur Geräteregistrierung, um die integrierte Registrierung von iOS-Geräten zu ermöglichen. ASM-Onboarding ist erforderlich, um die Classroom-App für gemeinsam genutzte iPads zu verwenden. Zudem ist es erforderlich, um das Synchronisieren von Daten von ASM zu Azure Active Directory über SDS (Microsoft School Data Sync) zu aktivieren. Weitere Informationen finden Sie unter [Aktivieren der iOS-Geräteregistrierung mit Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Das Konfigurieren gemeinsam genutzter iPads für die Nutzung der App „Classroom“ erfordert iOS Education-Konfigurationen in Azure, die noch nicht verfügbar sind.  Diese Funktionalität wird bald hinzugefügt.

### <a name="device-management"></a>Geräteverwaltung

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Bereitstellen von Remoteunterstützung auf Android-Geräten mithilfe von TeamViewer <!-- 675418 -->

Intune kann nun die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software nutzen, damit Sie Ihren Benutzern mit Android-Geräten Remoteunterstützung bieten können. Weitere Informationen finden Sie unter [Bereitstellen von Remoteunterstützung für von Intune verwaltete Android-Geräte](device-profile-android-teamviewer.md).

### <a name="app-management"></a>App-Verwaltung

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Neue Bedingungen für App-Schutzrichtlinien für MAM <!-- 679864 -->

Sie können nun eine Anforderung für MAM ohne Registrierung von Benutzern festlegen, die die folgenden Richtlinien erzwingt:

- Minimale Anwendungsversion
- Minimale Betriebssystemversion
- Mindestversion für Intune App SDK für die Zielanwendung (nur iOS)

Diese Funktion ist für Android und iOS verfügbar. Intune unterstützt die Durchsetzung einer Mindestversion für Betriebssystemplattformen, Anwendungen und das Intune App SDK. Unter iOS können Anwendungen mit integriertem SDK auch eine Durchsetzung einer Mindestversion auf SDK-Ebene festlegen. Der Benutzer kann nicht auf die Zielanwendung zugreifen, wenn die Mindestanforderungen der App-Schutzrichtlinie auf den drei oben aufgeführten verschiedenen Ebenen nicht erfüllt werden. An diesem Punkt kann der Benutzer entweder sein Konto entfernen (für Anwendungen mit mehreren Identitäten), die Anwendung schließen oder seine Betriebssystem- bzw. Anwendungsversion aktualisieren.

Sie können zusätzliche Einstellungen konfigurieren, um eine nicht blockierende Benachrichtigung bereitzustellen, die ein Upgrade des Betriebssystems oder der Anwendung empfiehlt. Diese Benachrichtigung kann geschlossen und die Anwendung wie gewohnt verwendet werden.

Weitere Informationen finden Sie unter [Einstellungen für App-Schutzrichtlinien für iOS](app-protection-policy-settings-ios.md) und [Einstellungen für App-Schutzrichtlinien für Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurieren von App-Konfigurationen für Android for Work <!-- 621621 -->
Einige Android-Apps aus dem Store unterstützen verwaltete Konfigurationsoptionen, mit denen ein IT-Administrator steuern kann, wie eine App im Arbeitsprofil ausgeführt wird. Mit Intune können Sie jetzt die von einer App unterstützten Konfigurationen anzeigen und sie im Intune-Portal mithilfe eines Konfigurations-Designers oder JSON-Editors konfigurieren. Weitere Informationen finden Sie unter [Verwenden von App-Konfigurationen für Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Neuen App-Konfigurationsfunktion für MAM ohne Registrierung <!-- 677969 -->

Sie können jetzt App-Konfigurationsrichtlinien über die Verwaltung mobiler Anwendungen (MAM) ohne Registrierungskanal erstellen. Dieses Feature entspricht den App-Konfigurationsrichtlinien, die in der App-Konfiguration für die mobile Geräteverwaltung (MDM) verfügbar sind. Ein Beispiel für die App-Konfiguration mit MAM ohne Registrierung finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurieren von Listen mit zugelassenen und blockierten URLs für den Managed Browser <!-- 682960 -->

Sie können jetzt eine Liste zulässiger und blockierter Domänen und URLs für den Intune Managed Browser mithilfe von App-Konfigurationseinstellungen im Azure-Portal konfigurieren. Diese Einstellungen können unabhängig davon verwaltet werden, ob der Browser auf einem verwalteten oder nicht verwalteten Gerät verwendet wird. Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Helpdeskansicht der App-Schutzrichtlinie <!-- 1069473 -->

IT-Helpdeskbenutzer können nun den Benutzerlizenzstatus und Status von App-Schutzrichtlinien, die Benutzern zugewiesen sind, auf dem Blatt „Problembehandlung“ überprüfen. Weitere Informationen finden Sie unter [Problembehandlung](./help-desk-operators.md).

### <a name="device-configuration"></a>Gerätekonfiguration

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Steuern von Websitebesuchen auf iOS-Geräten <!-- 723832 -->

Sie können nun mithilfe einer der beiden folgenden Methoden steuern, welche Websites Benutzer von iOS-Geräten besuchen können:

- Zulässige und blockierte URLs mit dem integrierten Webinhaltsfilter von Apple hinzufügen

- Erlauben, dass nur auf bestimmte Websites vom Safari-Browser aus zugegriffen werden darf. Lesezeichen werden in Safari für jede Website erstellt, die Sie angeben.

Weitere Informationen finden Sie im Artikel zu [Filtereinstellungen für Webinhalte auf iOS-Geräten](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Vorkonfigurieren von Geräteberechtigungen für Android for Work-Apps <!-- 621614 -->

Für Apps, die für Android for Work-Gerätearbeitsprofile bereitgestellt werden, können Sie nun den Berechtigungszustand für einzelne Apps konfigurieren.  Standardmäßig fordern Android-Apps, die Geräteberechtigungen erfordern (z. B. Zugriff auf den Standort oder die Gerätekamera), die Benutzer zum Annehmen oder Ablehnen der Berechtigungen auf.  Wenn eine App z. B. das Gerätemikrofon verwendet, wird der Endbenutzer aufgefordert, der App die Berechtigung zur Verwendung des Mikrofons zu erteilen. Dieses Feature gestattet Ihnen, die Berechtigungen im Namen des Endbenutzers zu definieren.  Sie können Berechtigungen konfigurieren, um diese a) automatisch ohne Benachrichtigung des Benutzers zu verweigern, b) automatisch ohne Benachrichtigung des Benutzers zu genehmigen oder c) den Benutzer zum Genehmigen oder Verweigern auffordern. Weitere Informationen finden Sie unter [Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definieren einer App-spezifischen PIN für Android for Work-Geräte <!-- 728976, 1102534 -->

Android-Geräte ab Version 7.0 mit einem als Android for Work-Gerät verwalteten Arbeitsprofil ermöglichen dem Administrator das Definieren einer Kennungsrichtlinie, die nur für Apps im Arbeitsprofil gilt.  Zu den Optionen gehören:

- Definieren einer geräteweiten Kennungsrichtline: Dies ist die vom Endbenutzer zu verwendende Kennung, um sein gesamtes Gerät zu entsperren.
 Definieren einer Kennungsrichtlinie für das Arbeitsprofil: Benutzer werden zur Eingabe einer Kennung aufgefordert, sobald eine App im Arbeitsprofil geöffnet wird.
- Definieren einer Geräterichtlinie und einer Arbeitsprofilrichtlinie: Die IT-Abteilung hat die Möglichkeit, eine gerätebezogene und eine arbeitsprofilbezogene Kennungsrichtlinie mit unterschiedlicher Stärken zu erstellen (z.B. eine vierstellige PIN zum Entsperren des Geräts, aber eine sechsstellige PIN zum Öffnen einer arbeitsbezogenen App).

Weitere Informationen finden Sie unter [Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Dies ist nur unter Android 7.0 und höher möglich.  Standardmäßig kann der Endbenutzer die beiden separat definierten PINs verwenden oder diese zu einer PIN kombinieren, die die Stärke der jeweils stärkeren PIN übernimmt.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Neue Einstellungen für Windows 10-Geräte <!-- 978585 -->

Wir haben neue [Einstellungen zur Windows-Geräteeinschränkung](device-restrictions-windows-10.md) hinzugefügt, die Features wie drahtlose Anzeigen, Geräteerkennung, Programmumschaltung und Fehlermeldungen von SIM-Karten steuern.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Änderungen an der Zertifikatkonfiguration <!-- 918991 and 823198 -->

Beim Erstellen eines SCEP-Zertifikatprofils für **Format des Antragstellernamens** steht die Option **Benutzerdefiniert** für iOS-, Android- und Windows-Geräte zur Verfügung. Vor dieser Aktualisierung war das Feld **Benutzerdefiniert** nur für iOS-Geräte verfügbar. Weitere Informationen finden Sie unter [How to create a SCEP certificate profile] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile) [Gewusst wie: Erstellen eines SCEP-Zertifikatprofils].

Beim Erstellen eines SCEP-Zertifikatprofils für **Alternativer Antragstellername** steht die Option **Benutzerdefiniertes Azure AD-Attribut** zur Verfügung. Die Option **Abteilung** ist verfügbar, wenn Sie **Benutzerdefiniertes Azure AD-Attribut** auswählen. Weitere Informationen finden Sie unter [How to create a PKCS certificate profile] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile) [Gewusst wie: Erstellen eines PKCS-Zertifikatprofils].

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurieren mehrerer Apps, die ausgeführt werden können, wenn sich ein Android-Gerät im Kioskmodus befindet <!-- 662059 -->

Wenn sich ein Android-Gerät im Kioskmodus befindet, konnte zuvor nur eine App konfiguriert werden, die ausgeführt werden durfte. Sie können jetzt mehrere Apps unter Verwendung der App-ID, der Speicher-URL oder durch Auswahl einer Android-App konfigurieren, die Sie bereits verwalten. Weitere Informationen finden Sie unter [Kioskmoduseinstellungen](device-restrictions-android.md#kiosk).


## <a name="notices"></a>Benachrichtigungen

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP-Adressen für Intune aktualisiert <!-- 1175274 -->

Eine [aktualisierte Liste der DNS-Namen und IP-Adressen](/intune/network-bandwidth-use) steht für die Firewall-Proxyeinstellungen zur Verfügung.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Verwenden von Azure Active Directory für bedingten Zugriff <!-- 967947 -->

„Bedingter Zugriff“ ist im Abschnitt „Azure Active Directory“ der Azure-Konsole verfügbar. Diese Option bietet ein leistungsstärkeres und flexibleres Framework für das Festlegen von Richtlinien für Cloud-Apps wie Office 365 Exchange Online und SharePoint Online.  Richtlinien können Sie auf dem Blatt **Bedingter Zugriff in Azure Active Directory** anstatt in der klassischen Intune-Konsole konfigurieren. In der klassischen Intune-Konsole vorhandene Richtlinien müssen in der Azure-Konsole neu erstellt werden. Weitere Informationen finden Sie unter [ Erstellen von Azure AD-Richtlinien für den bedingten Zugriff](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->

Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Portal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf das Azure-Portal zugreifen können.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Administratorrollen werden im Azure-Portal ersetzt

Die in der Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) vorhandenen Administratorrollen (Mitwirkender, Besitzer und Schreibgeschützt), die im klassischen Intune-Portal (Silverlight) verwendet werden, werden im Intune-Azure-Portal durch einen vollständigen Satz neuer rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) ersetzt. Nach der Migration zum Azure-Portal müssen Sie Ihre Administratoren diesen neuen Administratorrollen neu zuweisen. Weitere Informationen zu RBAC und den neuen Rollen finden Sie unter [Rollenbasierte Zugriffssteuerung für Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Was steht an?

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Ablauf des Supports für Android 4.3 und niedriger <!---1171127, 1326920 --->
Verwaltete Apps und die Unternehmensportal-App für Android benötigen Android 4.4 oder höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis Anfang Oktober aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. Ab Dezember werden alle registrierten Geräte deaktiviert und können dann nicht mehr auf Unternehmensressourcen zugreifen. Bei Verwendung von App-Schutzrichtlinien ohne mobile Geräteverwaltung erhalten Apps keine Updates mehr, und die Qualität ihrer Benutzung wird mit der Zeit abnehmen.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Erinnerung der Plattformunterstützung: die grundlegende Unterstützung für Windows Phone 8.1 wird am 11 Juli 2017 beendet.
<!-- 1327781 -->

Am 11. Juli 2017 wird die grundlegende Unterstützung für Windows Phone 8.1 endgültig beendet. Der Support für den Windows 8.1-PC ist davon nicht betroffen.

Dies hat keinen unmittelbaren Einfluss auf Windows Phone 8.1-Geräte, die vom Intune-Dienst verwaltet werden. Registrierte Geräte funktionieren weiterhin, und alle Richtlinien, Konfigurationen und Apps werden weiterhin wie erwartet funktionieren. Beachten Sie, dass es keine Verbesserungen für die Windows Phone 8.1-Plattform im Intune-Dienst sowie für die Unternehmensportal-App von Windows Phone 8.1.

Wir empfehlen Ihnen daher, zum schnellstmöglichen Zeitpunkt ein Upgrade für berechtigte Windows Phone 8.1-Geräte auf Windows 10 Mobile durchzuführen. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Änderungen bei der Unterstützung der Intune-iOS-Unternehmensportal-App <!-- 1164474  -->


In den kommenden Monaten erscheint eine neue Version für die Microsoft Intune-Unternehmensportal-App für iOS, die nur Geräte mit mindestens iOS 9.0 unterstützt. Die Version des Unternehmensportals, die iOS 8 unterstützt, wird für einen sehr kurzen Zeitraum weiterhin verfügbar sein. Beachten Sie jedoch, dass wenn Sie auch die MAM-fähigen iOS-Apps verwenden, für die wir iOS 9.0 und höher unterstützen, sicherstellen müssen, dass Ihre Endbenutzer ein Update auf das neueste Betriebssystem durchführen. 

#### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?
Wir geben Ihnen früh genug Bescheid, damit Sie genügend Zeit für die Planung haben, auch wenn wir noch kein bestimmtes Datum angeben können. Vergewissern Sie sich, dass Ihre Benutzer auf iOS 9 und höher aktualisiert haben, und Sie bei der Veröffentlichung der Unternehmensportal-App von Ihren Endbenutzern fordern, dass diese ihre Unternehmensportal-App aktualisieren.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wie sollte ich mich für die Änderung vorbereiten?

Ermutigen Sie Ihre Benutzer, ein Update auf iOS 9.0 oder höher durchzuführen, damit sie in den vollen Genuss der neuen Intune-Features kommen.  Fordern Sie Benutzer auf, die neue Version des Unternehmensportals zu installieren und die neuen darin angebotenen Funktionen zu benutzen.

Wechseln Sie zu Intune im Azure-Portal, und sehen Sie sich Geräte > Alle Geräte an. Filtern Sie nach der iOS-Version, um alle aktuellen Geräte mit einem Betriebssystem vor iOS 9 anzuzeigen.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbesserter Anmeldevorgang für alle Unternehmensportal-Apps auf allen Plattformen <!--User Story 1132123-->

Wir kündigen eine in den nächsten Monaten kommende Änderung an, durch die der Anmeldevorgang für die Intune-Unternehmensportal-Apps für Android, iOS und Windows verbessert wird. Die neue Benutzeroberfläche wird für die Unternehmensportal-App automatisch auf allen Plattformen eingeführt, sobald Azure AD die Änderung umsetzt. Darüber hinaus können Benutzer sich jetzt mithilfe eines generierten Codes zur einmaligen Verwendung von einem anderen Gerät aus beim Unternehmensportal anmelden. Dies ist besonders nützlich, wenn Benutzer sich ohne Anmeldeinformationen anmelden müssen.

Screenshots der vorherigen Anmeldeoberfläche, der neuen Anmeldeoberfläche mit Anmeldeinformationen und der neuen Anmeldeoberfläche zur Anmeldung von einem anderen Gerät aus finden Sie auf der Seite mit den [Neuerungen auf der App-Benutzeroberfläche](/intune/whats-new-app-ui).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Stellen Sie sich auf eine Änderung ein: Intune ändert die Oberfläche des Intune-Partnerportals <!-- 1050016 -->

Ab dem Dienstupdate Mitte Mai 2017 entfernen wir die Intune-Partnerseite von manage.microsoft.com.  

Wenn Sie ein Partneradministrator sind, können Sie über die Intune-Partnerseite nicht mehr im Namen Ihrer Kunden Elemente anzeigen und Aktionen durchführen. Stattdessen müssen Sie sich bei einer der beiden anderen Partnerportale von Microsoft anmelden.

Sowohl das [Microsoft Partner Center](https://partnercenter.microsoft.com/) als auch das [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) ermöglicht Ihnen das Anmelden bei den von Ihnen verwalteten Kundenkonten. Verwenden Sie als Partner künftig eine dieser Websites für die Verwaltung Ihrer Kunden.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->

Apple hat angekündigt, dass bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwungen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden.

Wir haben im Apple TestFlight-Programm eine Version der Unternehmensportal-App für iOS zur Verfügung gestellt, die die neuen ATS-Anforderungen erzwingt. Wenn Sie sie ausprobieren möchten, um Ihre ATS-Konformität zu testen, senden Sie eine E-Mail mit Angaben zu Vorname, Nachname, E-Mail-Adresse und Firmenname an <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](whats-new-app-ui.md)
* [Neuerungen in den vorherigen Monaten](whats-new-archive.md)
