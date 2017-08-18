---
title: Neuerungen in den vorherigen Monaten in Microsoft Intune
titleSuffix: Intune on Azure
description: "Überprüfen Sie ältere Ankündigungen auf der Intune-Seite mit den Neuerungen"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 8/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31617fb9992937f43f5bfc3b882f09d4be7de7b6
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2017
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Neuerungen in Microsoft Intune (vorherige Monate)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="june-2017"></a>Juni 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Neuer rollenbasierter Administratorenzugriff für Intune-Administratoren <!-- 1099990 -->  
Eine neue Administratorrolle für den bedingten Zugriff wird hinzugefügt, um Azure AD-Richtlinien für den bedingten Zugriff zu erstellen, zu ändern und zu löschen. Vorher besaßen nur globale Administratoren und Sicherheitsadministratoren diese Berechtigung. Diese Rollenberechtigung kann Intune-Administratoren erteilt werden, damit sie Zugriff auf Richtlinien für den bedingten Zugriff haben.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Markieren von unternehmenseigenen Geräten mit Seriennummer <!-- 1215070 -->  
Intune unterstützt nun das Hochladen von iOS-, macOS- und Android-Seriennummern als IDs für unternehmenseigene Geräte. Sie können anhand von Seriennummern derzeit keine persönlichen Geräte für die Registrierung blockieren, da Seriennummern bei der Registrierung nicht überprüft werden. Die Funktion zum Blockieren persönlicher Geräte durch Seriennummer wird in Kürze veröffentlicht.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Neue Remoteaktionen für iOS-Geräte <!-- 854689 -->
In dieser Version haben wir zwei neue remote Geräteaktionen für freigegebene iPad-Geräte hinzugefügt, die die Apple Classroom-App verwalten:

-   [Aktuellen Benutzer abmelden](device-logout-user.md): Meldet den aktuellen Benutzer eines von Ihnen ausgewählten iOS-Geräts aus.
-   [Benutzer entfernen](device-remove-user.md): Löscht einen von Ihnen ausgewählten Benutzer aus dem lokalen Cache eines iOS-Geräts.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Unterstützung für gemeinsam genutzte iPads mit der Classroom-App für iOS <!-- 1044681 -->
In diesem Release haben wir die Unterstützung für die Verwaltung der Classroom-App (iOS) erweitert, um Schüler und Studenten einzubeziehen, die sich mithilfe ihrer verwalteten Apple-ID auf gemeinsam genutzten iPads anmelden.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Änderungen an Integrierten Intune-Apps <!-- 1332306 -->
Zuvor enthielt Intune eine Reihe integrierter Apps, die Sie rasch zuweisen konnten. Auf Grundlage Ihrer Feedbacks haben wir diese Liste entfernt, und es werden keine integrierten Apps mehr angezeigt.
Wenn Sie jedoch schon integrierte Apps zugewiesen haben, werden sie noch immer auf der App-Liste angezeigt. Sie können diese Apps weiter nach Bedarf zuweisen.
In einer späteren Version möchten wir eine einfachere Methode zum Auswählen und Zuweisen integrierter Apps aus dem Intune-Portal integrieren.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Einfachere Installation von Office 365-Apps <!--- 1121362 --->
Der neue App-Typ von **Office 365 ProPlus** erleichtert Ihnen die Zuweisung von Office 365 ProPlus-2016-Apps zu von Ihnen verwalteten Geräten, die mit der neuesten Version von Windows 10 ausgeführt werden. Darüber hinaus erhalten Sie die Möglichkeit, Microsoft Project und Microsoft Visio zu installieren, wenn Sie über die entsprechenden Lizenzen verfügen. Die gewünschten Apps werden gebündelt und in der Intune-Konsole als einzelne App in der App-Liste angezeigt.
Weitere Informationen finden Sie unter [How to add Office 365 apps for Windows 10 (Hinzufügen von Office 365-Apps für Windows 10)](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Unterstützung für Offline-Apps aus dem Microsoft Store für Unternehmen <!--- 777044 --->
Offline-Apps, die Sie über den Microsoft Store für Unternehmen erworben haben, werden nun mit dem Intune-Portal synchronisiert. Sie können diese Apps dann für Geräte- oder Benutzergruppen bereitstellen. Offline-Apps werden durch Intune und nicht durch den Store installiert.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams ist jetzt Teil der App-basierten CA-Liste der genehmigten Apps <!-- 1257019 -->
Die Microsoft Teams-App für iOS und Android ist nun Bestandteil der genehmigten Apps für Richtlinien für den app-basierten bedingten Zugriff für Exchange und SharePoint Online. Im Azure-Portal kann die App über das Blatt „Intune-App-Schutz“ für alle Mandanten konfiguriert werden, die derzeit auf den app-basierten bedingten Zugriff zurückgreifen.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Verwaltete Browser- und App-Proxy-Integration <!-- 1287310 -->
Der Intune Managed Browser kann nun mit dem Azure AD-Anwendungsproxydienst integriert werden, damit Benutzer auf interne Websites zugreifen können, auch wenn Sie remote arbeiten. Benutzer des Browsers geben einfach wie gewohnt die Website-URL ein, und der Managed Browser leitet die Anfrage über das Anwendungsproxy-Webgateway weiter. Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Neue App-Konfigurationseinstellungen für Intune Managed Browser <!-- 682951 -->
In dieser Version haben wir weitere Konfigurationen für die Intune Managed Browser-App für iOS und Android hinzugefügt. Die Standardhomepage und -lesezeichen für den Browser können mit einer App-Konfigurationsrichtlinie konfiguriert werden.
Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser](app-configuration-managed-browser.md).

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Einstellungen für BitLocker für Windows 10 <!-- 951707 -->
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


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Die Unternehmensportal-App für Android verfügt nun über eine neue Endbenutzererfahrung für App-Schutzrichtlinien <!--1305217-->
Auf Grundlage von Benutzerfeedback haben wir die Unternehmensportal-App für Android modifiziert, sodass sie nun die Schaltfläche **Auf Unternehmensinhalte zugreifen** besitzt. Der Hintergrund dazu ist, Endbenutzer daran zu hindern, unnötigerweise den Registrierungsprozess zu durchlaufen, wenn sie nur auf Apps zugreifen müssen, die App-Schutzrichtlinien unterstützen, eine Funktion der mobilen Anwendungsverwaltung von Intune. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Neue Menüaktion zum mühelosen Entfernen des Unternehmensportals <!--1164569-->
Basierend auf Benutzerfeedback wurde der Unternehmensportal-App für Android eine neue Menüaktion hinzugefügt, über die das Entfernen des Unternehmensportals von Ihrem Gerät eingeleitet werden kann. Über diese Aktion wird das Gerät aus der Intune-Verwaltung entfernt, damit die App vom Benutzer vom Gerät entfernt werden kann. Sie sehen diese Änderungen auf der Seite zu den [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md) und in der [Android-Endbenutzerdokumentation](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Verbesserungen bei der App-Synchronisierung mit dem Windows 10 Creators Update <!--676505-->
Die Unternehmensportal-App für Windows 10 löst nun automatisch eine Synchronisierung für App-Installationsanforderungen für Geräte mit dem Windows 10 Creators Update (Version 1703) aus. Dadurch wird das Problem beseitigt, dass App-Installationen während des Zustands „Synchronisierung ausstehend“ verzögert reagieren. Darüber hinaus können Benutzer die Synchronisierung innerhalb der App manuell initiieren. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Neue Anleitung für das Windows 10-Unternehmensportal <!---1058938--->
Die Unternehmensportal-App für Windows 10 bietet eine geführte Intune-Anleitung für Geräte, die nicht identifiziert oder registriert wurden. Die neue Anleitung umfasst Schritt-für-Schritt-Anweisungen, mit denen die Registrierung bei Azure Active Directory (erforderlich für Funktionen zum bedingten Zugriff) und die MDM-Registrierung (erforderlich für Funktionen zur Geräteverwaltung) durch den Benutzer erläutert werden. Auf die geführte Anleitung kann über die Hauptseite des Unternehmensportals zugegriffen werden. Benutzer können die App weiterhin verwenden, wenn die Registrierung und Anmeldung nicht abgeschlossen werden, haben jedoch lediglich Zugriff auf einen eingeschränkten Funktionsumfang.

Dieses Update ist nur auf Geräten unter Windows 10 Anniversary Update (Build 1607) oder höher sichtbar. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Verwaltungskonsolen für Microsoft Intune und bedingten Zugriff allgemein verfügbar
Wir kündigen die allgemeine Verfügbarkeit der neuen Intune-Verwaltungskonsole in Azure und der Verwaltungskonsole für den bedingten Zugriff an. Über Intune in Azure können Sie jetzt alle Intune-Funktionen für die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) und mobiler Geräte (Mobile Device Management, MDM) zentral verwalten und die Azure AD-Zielgruppenbestimmung nutzen. Das Feature „Bedingter Zugriff“ in Azure führt umfassende Funktionen in Azure AD und Intune in einer einheitlichen Konsole zusammen. Aus administrativer Sicht ermöglicht Ihnen der Wechsel zur Azure-Plattform den Einsatz moderner Browser.

Intune wird in der Azure-Konsole auf portal.azure.com jetzt ohne die Bezeichnung **Vorschau** angezeigt.

Bestandskunden müssen derzeit keine Aktion ausführen, es sei denn, Sie haben im Nachrichtencenter eine Nachricht aus einer Reihe von Nachrichten erhalten, in der Sie aufgefordert werden, Maßnahmen zu ergreifen, damit wir Ihre Gruppen migrieren können. Sie haben möglicherweise im Nachrichtencenter auch den Hinweis erhalten, dass die Migration aufgrund von Fehlern unsererseits länger dauert. Wir arbeiten mit Volldampf daran, alle betroffenen Kunden zu migrieren.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Verbesserungen an den App-Kacheln in der Unternehmensportal-App für iOS
Wir haben das Design der App-Kacheln auf der Startseite entsprechend der Brandingfarbe geändert, die Sie für das Unternehmensportal festgelegt haben. Weitere Informationen finden Sie unter [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Kontoauswahl nun für die Unternehmensportal-App für iOS verfügbar
Benutzern von iOS-Geräten wird ggf. bei der Anmeldung beim Unternehmensportal unsere neue Kontoauswahl angezeigt, wenn sie für die Anmeldung bei anderen Microsoft-Anwendungen ihr Geschäfts-, Schul- oder Unikonto verwenden. Weitere Informationen finden Sie unter [Neuerungen auf der Benutzeroberfläche der App](whats-new-app-ui.md).

## <a name="may-2017"></a>Mai 2017

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
- Definieren einer Kennungsrichtlinie für das Arbeitsprofil: Benutzer werden zur Eingabe einer Kennung aufgefordert, sobald eine App im Arbeitsprofil geöffnet wird.
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



## <a name="april-2017"></a>April 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Unterstützung der Verwaltung der Apple-App Classroom
Sie können jetzt die iOS-App Classroom auf iPad-Geräten verwalten. Richten Sie die Classroom-App auf dem iPad der Lehrkraft mit den ordnungsgemäßen Schulungsraums- und Schüler-/Studentendaten ein. Konfigurieren Sie anschließend die iPads der Schüler/Studenten, die für einen Schulungsraum registriert sind, damit Sie deren Nutzung der App steuern können.
Einzelheiten finden Sie unter [Konfigurieren von iOS-Einstellungen für Bildungseinrichtungen](education-settings-configure-ios.md)

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Unterstützung für verwaltete Konfigurationsoptionen für Android-Apps <!-- 621621 -->
Android-Apps im Play Store, die verwaltete Konfigurationsoptionen unterstützen, können jetzt von Intune konfiguriert werden.  Mit dieser Funktion kann die IT die Liste der Konfigurationswerte sehen, die von einer App unterstützt werden, und es wird eine übersichtliche, hochwertige Benutzeroberfläche bereitgestellt, damit die IT diese Werte konfigurieren kann.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Neue Android-Richtlinie für komplexe PINs <!-- 722069 -->
Sie können jetzt einen erforderlichen numerisch-komplexen [Kennworttyp](device-restrictions-android.md#password) in einem Android-Geräteprofil für Geräte festlegen, auf denen Android 5.0 und höher ausgeführt wird.  Verwenden Sie diese Einstellung, um zu verhindern, dass Benutzer eine PIN erstellen, die sich wiederholende oder aufeinanderfolgende Zahlen enthält, z.B. 1111 oder 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Zusätzliche Unterstützung für Android for Work-Geräte
- **Verwalten von Kennwort- und Arbeitsprofileinstellungen** <!-- 612808 -->

  Mit dieser neuen Einschränkungsrichtlinie für Android for Work-Geräte können Sie jetzt Kennwort- und Arbeitsprofileinstellungen auf von Ihnen verwalteten Android for Work-Geräten verwalten.

- **Datenaustausch zwischen Arbeitsprofilen und persönlichen Profilen zulassen** <!-- 1045102 -->

Dieses Profil zur Einschränkung von Android for Work-Geräten weist jetzt neue Optionen auf, mit denen Sie die gemeinsame Datennutzung von Arbeits- und persönlichen Profilen konfigurieren können.

- **Beschränken von Kopieren und Einfügen zwischen Arbeitsprofilen und persönlichen Profilen** <!-- 1046094 -->

  Mit einem neuen benutzerdefinierten Geräteprofil für Android for Work-Geräte können Sie einschränken, ob Kopier- und Einfügeaktionen zwischen Arbeits- und persönlichen Apps zulässig sind oder nicht.

Weitere Informationen finden Sie unter [Geräteeinschränkungen für Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Zuweisen von branchenspezifischen Apps zu iOS- und Android-Geräten <!-- 1057568 -->
Sie können Benutzern oder Geräten branchenspezifische Apps für [iOS](lob-apps-ios.md) (IPA-Dateien) und [Android](lob-apps-android.md) (APK-Dateien) zuweisen.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Neue Geräterichtlinien für iOS <!-- 723774, 723815, 723826, 723830 -->
- **Apps auf dem Startbildschirm**: Steuert, welche Apps Benutzer auf dem [Startbildschirm ihres iOS-Geräts](home-screen-settings-ios.md) sehen. Diese Richtlinie wirkt sich auf das Layout des Startbildschirms aus, stellt aber keine Apps bereit.

- **Verbindungen mit AirPrint-Geräten**: Steuert, mit welchen [AirPrint-Geräten](air-print-settings-ios-macos.md) (Netzwerkdruckern) Endbenutzer eines iOS-Geräts eine Verbindung herstellen können.

- **Verbindungen zu AirPlay-Geräten**: Steuert, mit welchen [AirPlay-Geräten](airplay-settings-ios.md) (z.B. Apple TV) Endbenutzer eines iOS-Geräts eine Verbindung herstellen können.

- **Benutzerdefinierte Sperrbildschirmnachricht**: Konfiguriert eine benutzerdefinierte Nachricht, die Benutzern auf dem Sperrbildschirm ihres iOS-Geräts angezeigt wird und die Standardnachricht des Sperrbildschirms ersetzt. Weitere Informationen finden Sie unter [Aktivieren des Modus für verlorene Geräte auf iOS-Geräten](device-lost-mode.md).

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Einschränken von Pushbenachrichtigungen für iOS-Apps <!-- 723767 -->
In einem Intune-Geräteeinschränkungsprofil können Sie jetzt die folgenden [Benachrichtigungseinstellungen](app-notification-settings-ios.md) für iOS-Geräte konfigurieren:

- Aktivieren oder deaktivieren Sie die Benachrichtigungen für eine bestimmte App vollständig.
- Aktivieren oder deaktivieren Sie die Benachrichtigung für eine bestimmte App in der Mitteilungszentrale.
- Geben Sie den Warnungstyp an, entweder **Keinen**, **Banner** oder **modale Warnung**.
- Geben Sie an, ob die Badges für diese App zulässig sind.
- Geben Sie an, ob die Benachrichtigungssounds zulässig sind.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Konfigurieren von iOS-Apps, damit sie autonom im Einzelanwendungsmodus ausgeführt werden sollen <!-- 737837 -->
Sie können jetzt ein Intune-Geräteprofil verwenden, um iOS-Geräte so zu konfigurieren, dass bestimmte Apps im [autonomen Einzelanwendungsmodus](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only) ausgeführt werden. Wenn dieser Modus konfiguriert ist und die App ausgeführt wird, wird das Gerät gesperrt, sodass es nur die App ausführen kann. Ein Beispiel hierfür ist, wenn Sie eine App konfigurieren, mit der Benutzer einen Test auf dem Gerät ausführen können. Wenn die Aktionen der App abgeschlossen sind oder Sie diese Richtlinie entfernen, kehrt das Gerät in seinen normalen Zustand zurück.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Konfigurieren von vertrauenswürdigen Domänen für das Durchsuchen von E-Mails und das Webbrowsen auf iOS-Geräten <!-- 723765 -->
Sie können in einem iOS-Geräteeinschränkungsprofil jetzt die folgenden [Domäneneinstellungen](device-restrictions-ios.md#domains) konfigurieren:

- **Nicht gekennzeichnete E-Mail-Domänen**: Vom Benutzer gesendete oder empfangene E-Mails, die nicht den hier angegebenen Domänen entsprechen, werden als nicht vertrauenswürdig markiert.

- **Verwaltete Webdomänen**: Dokumente, die von den hier angegebenen URLs heruntergeladen werden, gelten als verwaltet (nur Safari).  

- **AutoAusfüllen-Domänen für Safari-Kennwörter**: Benutzer können Kennwörter in Safari nur aus URLs speichern, die mit den von Ihnen hier angegebenen Mustern übereinstimmen. Um diese Einstellung verwenden, muss sich das Gerät im überwachten Modus befinden und darf nicht für mehrere Benutzer konfiguriert sein. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Im iOS-Unternehmensportal verfügbare VPP-Apps als <!-- 748782 -->
Sie können per Volumenlizenz erworbene iOS-Apps (VPP-Apps) Endbenutzern jetzt als **verfügbare** Installationen zuweisen. Endbenutzer benötigen ein Apple Store-Konto, um die App zu installieren.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronisieren von eBooks vom Apple-VPP-Store <!-- 800878 -->
Sie können jetzt [Bücher synchronisieren](vpp-apps-ios.md), die Sie im Apple-VPP-Store mit Intune erworben haben, und diese Bücher Benutzern zuweisen.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Mehrbenutzerverwaltung für Samsung KNOW Standard-Geräte <!-- 971988 -->
Geräte, die mit Samsung KNOX Standard ausgeführt werden, werden jetzt für die [Mehrbenutzerverwaltung](android-enroll.md) von Intune unterstützt. Das bedeutet, dass sich Endbenutzer auf dem Gerät mit ihren Azure Active Directory-Anmeldeinformationen an- und wieder abmelden können, und dass das Gerät zentral verwaltet wird, egal ob es sich in Gebrauch befindet oder nicht.  Wenn sich Endbenutzer anmelden, verfügen Sie über Zugriff auf Apps und erhalten alle Richtlinien, die ihnen zugewiesen sind. Wenn sich Benutzer abmelden, werden alle App-Daten gelöscht.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Zusätzliche Einstellungen zur Einschränkung für Windows-Geräte <!-- 818566 -->
Wir haben Unterstützung für zusätzliche [Einschränkungseinstellungen für Windows-Geräte](device-restrictions-windows-10.md) hinzugefügt, z.B. zusätzliche Unterstützung für den Edge-Browser, Anpassung des Gerätesperrbildschirms, Anpassungen des Startmenüs, festgelegtes Hintergrundbild der Windows Spotlight-Suche und Proxyeinstellungen.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Unterstützung für Windows 10 Creators Update für mehrere Benutzer <!-- 822547 -->
Wir haben Unterstützung für die [Mehrbenutzerverwaltung](windows-enroll.md) für Geräte hinzugefügt, die das Windows 10 Creators Update ausführen und in die Azure Active Directory-Domäne eingebunden sind. Das bedeutet Folgendes: Wenn sich unterschiedliche Standardbenutzer mit ihren Azure AD-Anmeldeinformationen auf dem Gerät anmelden, erhalten sie alle Apps und Richtlinien, die ihrem jeweiligen Benutzernamen zugewiesen sind. Benutzer können das Unternehmensportal derzeit nicht für Self-Service-Szenarien beispielsweise zum Installieren von Apps verwenden.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start für Windows 10-PCs <!-- 1004830 -->
Eine neue [Fresh Start-Geräteaktion](device-fresh-start.md) für Windows 10-PCs ist jetzt verfügbar.  Wenn Sie diese Aktion ausführen, werden alle installierten Apps auf dem PC entfernt, und der PC wird automatisch auf die neueste Windows-Version aktualisiert. Damit können vorinstallierte OEM-Apps entfernt werden, die oft mit einem neuen PC geliefert werden. Sie können konfigurieren, ob Benutzerdaten beibehalten werden, wenn diese Geräteaktion ausgegeben wird.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Zusätzliche Windows 10-Upgradepfade <!-- 903672 -->
Sie können jetzt eine [Richtlinie für Editionsupgrades](edition-upgrade-configure-windows-10.md) erstellen, um Geräte auf die folgenden zusätzlichen Windows 10-Editionen zu aktualisieren:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Massenregistrierung von Windows 10-Geräten <!-- 747607 -->
Sie können jetzt eine große Anzahl von Geräten, auf denen das Windows 10 Creators Update ausgeführt wird, mit Windows Configuration Designer (WCD) in Azure Active Directory und Intune einbinden. Um die [MDM-Massenregistrierung](windows-bulk-enroll.md) für Ihren Azure AD-Mandanten zu aktivieren, erstellen Sie ein Bereitstellungspaket, das Geräte mithilfe von Windows Configuration Designer in Ihren Azure AD-Mandanten einbindet. Sie können das Paket auf alle unternehmenseigenen Geräte anwenden, die Sie per Massenvorgang registrieren und verwalten möchten. Nachdem das Paket auf Ihre Geräte angewendet wurde, werden die Geräte in Azure AD eingebunden und bei Intune registriert und sind dann bereit für die Anmeldung durch Ihre Azure AD-Benutzer.  Azure AD-Benutzer sind auf diesen Geräten Standardbenutzer und erhalten zugewiesene Richtlinien sowie erforderliche Apps. Die Verwendung von Self-Service-Funktionen und Unternehmensportalen wird derzeit nicht unterstützt.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Neue MAM-Einstellungen für die PIN und verwaltete Speicherorte <!-- 581122, 736644 -->
Es sind zwei neue App-Einstellungen verfügbar, die Sie in MAM-Szenarien (Mobile Application Management, Verwaltung mobiler Anwendungen) unterstützen:

- **App-PIN deaktivieren, wenn die Geräte-PIN verwaltet wird**: Erkennt, ob eine Geräte-PIN auf dem registrierten Gerät vorhanden ist. Falls ja, wird die App-PIN umgangen, was durch die App-Schutzrichtlinien ausgelöst wird. Diese Einstellung ermöglicht eine Verminderung der Häufigkeit, wann immer Benutzern eine Aufforderung zur PIN-Eingabe angezeigt wird, wenn sie eine MAM-fähige Anwendung auf einem registrierten Gerät öffnen. Diese Funktion ist für Android und iOS verfügbar.

- **Wählen, welche Speicherdienste Unternehmensdaten speichern können**: Damit können Sie angeben, an welchen Speicherorten Unternehmensdaten gespeichert werden sollen. Benutzer können in ausgewählten Speicherortdiensten speichern, das heißt, dass alle anderen Speicherortdienste, die nicht aufgelistet sind, blockiert werden.

  Liste der unterstützten Speicherortdienste:

  - OneDrive
  - Business SharePoint Online
  - Lokaler Speicher

### <a name="help-desk-troubleshooting-portal----907448---"></a>Helpdeskportal zur Problembehandlung <!-- 907448 -->
Im neuen [Portal zur Problembehandlung](help-desk-operators.md) können Helpdeskmitarbeiter und Intune-Administratoren Benutzer und Geräte anzeigen und Aufgaben ausführen, um technische Intune-Probleme zu lösen.

## <a name="march-2017"></a>März 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Unterstützung des iOS-Modus für verlorene Geräte <!--431695-->
Für Geräte unter iOS 9.3 (oder höher) wurde von Intune die Unterstützung des **Modus für verlorene Geräte** hinzugefügt. Nun können Sie ein Gerät sperren, um zu dessen Verwendung vollständig zu unterbinden, und auf dem Sperrbildschirm des Geräts eine Meldung und eine Kontakttelefonnummer anzeigen.

Der Endbenutzer kann das Gerät erst wieder entsperren, wenn ein Administrator den Modus für verlorene Geräte deaktiviert. Bei aktivierten Modus für verlorene Geräte können Sie mithilfe der Aktion **Gerät suchen** den geografischen Standort des Geräts auf einer Karte in der Intune-Konsole anzeigen.

Bei dem Gerät muss es sich um ein firmeneigenes, über DEP registriertes iOS-Gerät im überwachten Modus handeln.

Weitere Informationen finden Sie unter [Was ist die Microsoft Intune-Geräteverwaltung?](device-management.md).

### <a name="improvements-to-device-actions-report---677150--"></a>Verbesserungen des Geräteaktionenberichts<!--677150-->
Wir haben die Leistung des Geräteaktionenberichts verbessert. Darüber hinaus können Sie jetzt den Bericht nach Status filtern. Beispielsweise könnten Sie den Bericht so filtern, dass nur Geräteaktionen angezeigt werden, die abgeschlossen wurden.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Zuweisen von Branchen-Apps für Benutzer nicht registrierter Geräte <!--748823-->
Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn das Gerät eines Benutzers nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren.

### <a name="new-compliance-reports---846671--"></a>Neue Kompatibilitätsberichte <!--846671-->
Jetzt informieren Kompatibilitätsberichte Sie über die Kompatibilitätsstellung von Geräten in Ihrem Unternehmen, sodass sie schnell kompatibilitätsbezogene Probleme beheben können, von denen Ihre Benutzer betroffen sind. Sie können Informationen anzeigen zu:

- Gesamter Kompatibilitätsstatus von Geräten
- Kompatibilitätsstatus für eine einzelne Einstellung
- Kompatibilitätsstatus für eine einzelne Richtlinie

Sie können mit diesen Berichten auch Detailinformationen zu einzelnen Geräten erhalten, um bestimmte Einstellungen und Richtlinien anzuzeigen, die sich auf das Gerät auswirken.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->
Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Portal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.


## <a name="february-2017"></a>Februar 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Einschränken der Registrierung von Mobilgeräten <!--747600, 795782-->
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.

* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.  
* Für iOS und Android gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices) beschrieben.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Anzeigen aller Aktionen auf verwalteten Geräten <!--677150-->
Ein neuer Bericht über __Geräteaktionen__ zeigt, wer Remoteaktionen wie das Zurücksetzen auf Werkseinstellungen auf Geräten ausgeführt hat sowie den Status dieser Aktion. Weitere Informationen finden Sie unter [Was ist die Geräteverwaltung?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->
Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](apps-add.md).

### <a name="display-device-categories---814654--"></a>Anzeigen von Gerätekategoriern <!--814654-->
Sie können nun die Gerätekategorie als Spalte in der Geräteliste anzeigen. Sie können die Kategorie auch im Abschnitt „Eigenschaften“ des Blatts „Geräteeigenschaften“ bearbeiten. Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurieren von Einstellungen für Windows Update for Business <!--776716-->

Windows als Dienst ist die neue Methode zur Bereitstellung von Updates für Windows 10. Ab Windows 10 enthalten neue Funktions- und Qualitätsupdates die Inhalte aller früheren Updates. Das bedeutet, dass Ihre Windows 10-Geräte nach der Installation des neuesten Updates vollständig auf dem neuesten Stand sind. Im Gegensatz zu früheren Versionen von Windows müssen Sie nun anstelle eines Teilupdates das gesamte Update installieren.

Mithilfe von Windows Update for Business können Sie die Updateverwaltung vereinfachen, sodass Sie für Gruppen von Geräten keine einzelnen Updates genehmigen müssen. Sie können weiterhin eine Updaterolloutstrategie konfigurieren, um das Risiko in Ihren Umgebungen zu managen und sicherzustellen, dass Updates zur richtigen Zeit installiert werden. Mit Microsoft Intune können Sie Updateeinstellungen auf Geräten konfigurieren und die Updateinstallation zurückstellen. Intune speichert nur die Updaterichtlinienzuweisung, nicht die Updates. Geräte greifen direkt auf Windows Update zu, um die Updates zu beziehen. Intune dient zum Konfigurieren und Verwalten der **Windows 10-Updateringe**. Ein Updatering enthält eine Reihe von Einstellungen, die festlegen, wann und wie Updates für Windows 10 installiert werden. Ausführlichere Informationen finden Sie unter [Konfigurieren von Einstellungen für Windows Update for Business](windows-update-for-business-configure.md).

## <a name="january-2017"></a>Januar 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Zuweisen von Branchen-Apps unabhängig vom Registrierungsstatus von Geräten <!--748823-->
Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn ein Benutzergerät nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren. Siehe [Was ist die App-Verwaltung?](app-management.md).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Lösen von Problemen, wenn iOS-Geräte inaktiv sind oder die Verwaltungskonsole nicht mit ihnen kommunizieren kann
Wenn Geräte von Benutzern keinen Kontakt mehr mit Intune haben, können Sie neue Schritte zur Problembehandlung bereitstellen, damit sie erneuten Zugriff auf Unternehmensressourcen gewinnen können. Weitere Informationen finden Sie unter [Geräte sind inaktiv oder die Verwaltungskonsole kann nicht mit ihnen kommunizieren](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Dezember 2016 (erste Version)

### <a name="telecom-expense-management-integration-in-azure-portal--747605--"></a>Integration der Verwaltung der Telekommunikationsausgaben in das Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Bereitstellen und Verwalten von Apps aus einem Store auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von branchenspezifischen Apps auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von per Volumenlizenz erworbenen Apps auf iOS- und Windows-Geräten
- Bereitstellen und Verwalten von Web-Apps auf Android-, iOS- und Windows-Geräten
- In iOS verwaltete App-Konfigurationsprofile
- Konfigurieren von App-Schutzrichtlinien und Bereitstellen von branchenspezifischen Apps auf Geräten, die nicht in Intune registriert sind
- VPN-Profile, VPN pro App, WLAN, E-Mail und Zertifikatprofile
- Konformitätsrichtlinien
- Bedingter Zugriff für Azure AD
- Bedingter Zugriff auf lokales Exchange
- Geräteregistrierung
- Rollenbasierte Zugriffssteuerung

## <a name="deprecated-features-in-the-azure-portal"></a>Veraltete Features im Azure-Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Unterstützung für die zeilenweise Überprüfung von Hardware-IDs
Das Azure-Portal unterstützt keine zeilenweise Überprüfung von Hardware-IDs für IMEI-Nummern und Apple-Seriennummern. In der klassischen Intune-Konsole können Sie Informationen aus einer durch Trennzeichen getrennten Datei (CSV) importieren und die vorhandenen Daten für einzelne Hardware-IDs überschreiben. Das Azure-Portal bietet eine optimierte Option, durch die automatisch die Daten für alle Hardware-IDs überschrieben oder neue Daten für vorhandene IDs ignoriert werden.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal nicht zeilenweise entscheiden, welche IMEI-Geräte (International Mobile Equipment Identity) aktualisiert werden sollen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Diese Änderung tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Unterstützung für Standardprofile für Unternehmensgeräteregistrierungen in Apple DEP
Das Azure-Portal unterstützt nicht das Standardprofil für Unternehmensgeräteregistrierungen für Geräteseriennummern in Apple DEP (Device Enrollment Programm). Diese Funktion, die in der klassischen Intune-Konsole zur Verfügung steht, wird nicht fortgeführt, damit nicht versehentlich Profile zugewiesen werden. Im Azure-Portal wird Seriennummern, die aus einem Apple DEP-Konto synchronisiert werden, zunächst keine Profil für die Unternehmensgeräteregistrierung zugewiesen.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal keine Standardprofilrichtlinie für alle Apple-Geräte festlegen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Dies tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.

### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new.md).
