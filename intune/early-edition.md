---
title: Early Edition
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12f4a09fe10ec792abe8183369a21f53c23f5d1a
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Die Early Edition für Microsoft Intune – Januar 2018

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden auf einer begrenzten Basis bereitgestellt, und Änderungen sind vorbehalten. Geben Sie diese Informationen nicht außerhalb Ihres Unternehmens weiter. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich mit Fragen oder Bedenken an den Ansprechpartner für Ihre Microsoft-Produktgruppe.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
>Die folgenden Änderungen sind in der Entwicklung für Intune. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## <a name="intune-in-the-azure-portal"></a>Intune im Azure-Portal

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Einfachere Lösung von Konformitätsfehlern für die Unternehmensportal-App für Windows 10 <!--676546 -->

Endbenutzer mit Windows-Geräten können in der Unternehmensportal-App auf den Grund der Nichtkonformität tippen. Wenn möglich werden sie direkt an den korrekten Ort in der Einstellungs-App geleitet, um das Problem zu beheben.

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Neue Option zur Benutzerauthentifizierung für die Apple-Massenregistrierung<!-- 747625 -->
Mit Intune können Sie Geräte über folgende Registrierungsmethoden mit der Unternehmensportal-App authentifizieren:

- Apple-Programm zur Geräteregistrierung
- Apple School Manager
- Apple Configurator-Registrierung

Wenn Sie die Unternehmensportaloption verwenden, kann die mehrstufige Authentifizierung von Azure Active Directory erzwungen werden, ohne dass hierdurch diese Registrierungsmethoden blockiert werden.

Bei Verwendung der Unternehmensportaloption überspringt Intune die Benutzerauthentifizierung im iOS-Einrichtungsassistenten für die Registrierung mit der Benutzeraffinität. Das bedeutet, dass das Gerät zunächst als Gerät ohne Benutzer registriert wird und somit keine Konfigurationen oder Richtlinien von Benutzergruppen erhält. Es erhält nur Konfigurationen und Richtlinien für Gerätegruppen. Allerdings installiert Intune automatisch die Unternehmensportal-App auf dem Gerät. Der erste Benutzer, der die Unternehmensportal-App startet und sich bei dieser anmeldet, wird mit dem Gerät in Intune verbunden. An dieser Stelle erhält der Benutzer Konfigurationen und Richtlinien seiner Benutzergruppen. Die Benutzerzuordnung kann nur durch erneute Registrierung geändert werden.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-Unterstützung für mehrere Apple DEP-/Apple School Manager-Konten <!-- 747685 -->
Intune unterstützt die Registrierung von Geräten mit bis zu 100 verschiedenen Apple DEP-Konten (Device Enrollment Program) oder Apple School Manager-Konten. Jedes Token kann separat für Registrierungsprofile und Geräte hochgeladen und verwaltet werden. Jedem hochgeladenen DEP-/School Manager-Token kann automatisch ein separates Registrierungsprofil zugewiesen werden. Wenn mehrere School Manager-Token hochgeladen werden, kann mit der Microsoft-Synchronisierung von Schul-/Unidaten jeweils nur ein Token freigegeben werden.

Nach der Migration funktionieren die Betaversionen der Graph-APIs und veröffentlichten Skripts zur Verwaltung von Apple DEP oder ASM über Graph nicht mehr. Neue Betaversionen der Graph-APIs sind in der Entwicklung und werden nach der Migration veröffentlicht.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Auswählen von Gerätekategorien durch den Zugriff auf die Einstellungen für Geschäfts-, Schul- oder Unikonten <!-- 1058963 eeready -->
Wenn Sie die [Gerätegruppenzuordnung](https://docs.microsoft.com/en-us/intune/device-group-mapping) aktiviert haben, werden Benutzer unter Windows 10 aufgefordert, eine Gerätekategorie auszuwählen, nachdem sie sich unter **Einstellungen** > **Konten** > **Auf Geschäfts-, Schul- oder Unikonto zugreifen** mit der Schaltfläche **Verbinden** oder über die Windows-Willkommensseite angemeldet haben.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Ausrichten von Konformitätsrichtlinien auf Geräte in Gerätegruppen <!--1307012 -->

Sie können Konformitätsrichtlinien gezielt auf Benutzer in Benutzergruppen ausrichten. Sie können Konformitätsrichtlinien gezielt auf Benutzer in Benutzergruppen ausrichten.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Ein- und Ausschließen von App-Zuweisungen basierend auf Gruppen<!-- 1406920 -->

Bei der App-Zuweisung und nach der Auswahl eines Zuweisungstyps können Sie die ein- und auszuschließenden Gruppen auswählen.

### <a name="remote-erase-command-support----1438084---"></a>Remoteunterstützung für den Befehl „Löschen“<!-- 1438084 -->

Administratoren können einen Löschbefehl remote ausgeben.

> [!IMPORTANT]
> Der Löschbefehl kann nicht zurückgesetzt werden und sollte mit Bedacht angewendet werden.

Der Löschbefehl entfernt alle Daten von einem Gerät, einschließlich des Betriebssystems. Zusätzlich wird dabei auch das Gerät aus der Intune-Verwaltung entfernt. Es erfolgt keine Warnung gegenüber dem Benutzer und die Löschung erfolgt unmittelbar nach Ausgabe des Befehls.

Sie können eine 6-stellige PIN für die Wiederherstellung konfigurieren. Mit dieser PIN kann das gelöschte Gerät entsperrt werden, woraufhin die erneute Installation des Betriebssystems beginnt. Nach dem Starten des Löschvorgangs wird die PIN in einer Statusleiste auf dem Übersichtsblatt des Geräts in Intune angezeigt. Die PIN bleibt für die Dauer der Löschung bestehen. Nach der Löschung verschwindet das Gerät vollständig aus der Intune-Verwaltung. Dokumentieren Sie die Wiederherstellungs-PIN, damit sie jedem, der das Gerät wiederherstellt, zur Verfügung steht.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Mit Windows Information Protection (WIP) verschlüsselte Daten in Windows-Suchergebnissen <!-- 1469193 -->

Mit einer neuen Einstellung in der WIP-Richtlinie (Windows Information Protection) können Sie steuern, ob mit WIP verschlüsselte Daten in den Windows-Suchergebnissen enthalten sind.

### <a name="website-learning-mode----1631908---"></a>Websitetrainingsmodus<!-- 1631908 -->

In Intune wird eine Erweiterung des WIP-Trainingsmodus (Windows Information Protection) eingeführt. Neben der Anzeige von Informationen über WIP-fähige Apps können Sie eine Zusammenfassung der Geräte anzeigen, die Arbeitsdaten für Websites freigegeben haben. Anhand dieser Informationen können Sie festlegen, welche Websites zu WIP-Gruppen- und Benutzerrichtlinien hinzugefügt werden sollen.

### <a name="updates-to-compliance-emails---1637547---"></a>Updates für Konformitäts-E-Mails<!--1637547 -->

Wenn eine E-Mail zur Meldung eines nicht konformen Geräts gesendet wird, werden Details über das nicht konforme Gerät einbezogen. Der folgende Artikel wird im Hinblick auf folgenden Aspekt aktualisiert: [Automatisieren von Aktionen in Bezug auf Nichtkonformität](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Ausschließliche Verfügbarkeit von Richtlinien für den bedingten Zugriff für Intune über das Azure-Portal  <!-- 1737088 1634311 -->
Wir vereinfachen den Prozess zum Konfigurieren und Verwalten des bedingten Zugriffs. Sie konfigurieren und verwalten Ihre Richtlinien im [Azure-Portal](https://portal.azure.com) unter **Azure Active Directory** > **Bedingter Zugriff**. Der Einfachheit halber können Sie dieses Blatt auch über **Intune** > **Bedingter Zugriff** im Azure-Portal aufrufen.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Warnungen für abgelaufene und in Kürze ablaufende Token <!-- 1639263 -->
Auf der Übersichtsseite werden Warnungen für abgelaufene und in Kürze ablaufende Token angezeigt. Wenn Sie auf eine Warnung für ein einzelnes Token klicken, navigieren Sie zur Detailseite des Tokens.  Wenn Sie auf eine Warnung mit mehreren Token klicken, werden Sie zu einer Liste aller Token mit dem jeweiligen Status weitergeleitet. Administratoren sollten ihre Token vor dem Ablaufdatum verlängern.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Remotedrucken über ein sicheres Netzwerk <!-- 1709994  -->
Mobile drahtlose PrinterOn-Drucklösungen ermöglichen es Benutzern, jederzeit von einem beliebigen Ort aus Druckvorgänge remote über ein sicheres Netzwerk durchzuführen. PrinterOn wird in das Intune APP SDK für iOS und Android integriert. Über das Intune-Blatt **App-Schutzrichtlinien** in der Administratorkonsole können Sie gezielt die App-Schutzrichtlinien für diese App steuern. Endbenutzer können die App „PrinterOn for Microsoft“ über den Play Store oder iTunes herunterladen, um sie innerhalb ihres Intune-Ökosystems zu nutzen.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Genehmigen der Unternehmensportal-App für Android for Work <!--1797090 -->
Wenn Ihre Organisation Android for Work verwendet, müssen Sie die Unternehmensportal-App für Android manuell genehmigen, damit sie weiterhin automatische Updates vom verwalteten Google Play Store erhält.

### <a name="faceid-on-ios-devices----1807377---"></a>„FaceID“ unter iOS-Geräten <!-- 1807377 -->
Die App-Schutzrichtlinien von Intune unterstützen jetzt eine Einstellung, um die „FaceID“ unter iOS-Geräten zu steuern. Diese Einstellung gilt für Geräte, die die FaceID-Funktion unterstützen (derzeit nur das iPhone X). Diese Einstellung unterscheidet sich von dem TouchID-Steuerelement, das derzeit unterstützt wird. Organisationen können auswählen, ob sie der FaceID-Option als gültige PIN-Eingabeaufforderung als Alternative zum TouchID-Steuerelement vertrauen.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Microsoft Graph-API für Intune – Allgemeine Verfügbarkeit <!-- 1833289 -->
Intune-APIs in Microsoft Graph bieten programmgesteuerten Zugriff auf Daten und Methoden zur Automatisierung administrativer Aktionen für den Intune-Dienst.  Dank der **allgemeinen Verfügbarkeit** dieser APIs können Kunden, Partner und Entwickler die APIs nutzen, um sie in interne oder kommerzielle Lösungen zu integrieren, die die Unterstützung von Intune oder anderen über Microsoft Graph verfügbaren Microsoft-Diensten erfordern.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>App-Schutzrichtlinien <!-- 679615 -->
Mit den Intune-App-Schutzrichtlinien können Sie globale Standardrichtlinien erstellen und damit den Schutz für alle Benutzer im gesamten Mandanten schnell aktivieren.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Widerrufen von Apps aus dem iOS Volume Purchase Program <!-- 820863 -->
Für ein bestimmtes Gerät, das mindestens eine iOS VPP-App (Volume Purchase Program) enthält, können Sie die zugehörige gerätebasierte App-Lizenz für das Gerät widerrufen. Durch das Widerrufen einer App-Lizenz wird die zugehörige VPP-App nicht vom Gerät deinstalliert. Zum Deinstallieren einer VPP-App müssen Sie die Zuweisungsaktion in **Deinstallieren** ändern. Weitere Informationen finden Sie unter [Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Widerrufen von Lizenzen für ein iOS Volume Purchase Program-Token <!-- 820870 -->
Sie können die Lizenz für alle iOS VPP-Apps (Volume Purchase Program) für ein bestimmtes VPP-Token widerrufen.

### <a name="new-ios-device-action------1244701---"></a>Neue iOS-Geräteaktion <!-- 1244701 -->
Sie können überwachte iOS 10.3-Geräte herunterfahren. Diese Aktion fährt das Gerät sofort und ohne Warnung für den Endbenutzer herunter. Die Aktion **Herunterfahren (nur überwacht)** finden Sie in den Geräteeigenschaften bei der Auswahl eines Geräts in der Workload **Gerät**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune stellt jetzt den Vorgang zur Kontoverschiebung bereit <!-- 1573558, 1579830 -->
Bei der **Kontoverschiebung** wird ein Mandant von einer Azure-Skalierungseinheit (ASU) zu einer anderen migriert. Die **Kontoverschiebung** kann für vom Kunden eingeleitete Szenarien verwendet werden, wenn Sie sie vom Intune-Supportteam anfordern. Sie kann auch ein von Microsoft gesteuertes Szenario sein, wenn Microsoft Anpassungen am Dienst im Back-End vornehmen muss. Während der **Kontoverschiebung** wechselt der Mandant zum schreibgeschützten Modus (ROM). Dienstvorgänge wie die Registrierung, das Umbenennen von Geräten oder das Aktualisieren des Kompatibilitätsstatus sind während des ROM-Zeitraums nicht möglich.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Zuweisen von mobilen Office 365-Apps an iOS- und Android-Geräte mithilfe des integrierten App-Typs <!-- 1332318 -->
Der **integrierte** App-Typ erleichtert es, Office 365-Apps für die iOS- und Android-Geräte, die Sie verwalten, zu erstellen und sie diesen zuzuweisen. Zu diesen Apps gehören Office 365-Apps wie Word, Excel, PowerPoint und OneDrive. Sie können bestimmte Apps dem App-Typen zuweisen und die Konfiguration der App-Informationen bearbeiten.


### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>Die Auflösung von Zuweisungskonflikten wurde für Apps im iOS Store geändert <!-- 1480316 -->
Möglicherweise stellen die Benutzer eine Veränderung im Hinblick auf die Verfügbarkeit von Apps aus dem iOS Store fest. Derzeit entscheidet sich eine App, die zwei Gruppen zugewiesen wurde und für die ein Konflikt zwischen **Required and Available** (Erforderlich und Verfügbar) und **Nicht verfügbar** besteht, für die Option **Required and Available**. Im Rahmen dieser Änderung wird die App allerdings zur Lösung des Konflikts die Option **Nicht verfügbar** auswählen.

Die Änderung wurde vorgenommen, um die Verwirrung anzugehen, die entsteht, wenn eine App mehreren Gruppen zugewiesen ist, die verschiedene App-Absichten haben.

Wenn Sie Ihre App vor dem Service Release im November im Informationsportal für Mitarbeiter und dem Unternehmensportal zur Verfügung stellen wollen, haben Sie zwei Möglichkeiten:

1. Entfernen Sie die Zuweisung **Nicht verfügbar** für Ihre Gruppe.
2. Erstellen Sie eine neue Gruppe, die keine Mitglieder enthält, denen die Absicht **Required and Available** zugewiesen wurde, und weisen Sie diese Gruppe als **Nicht verfügbar** zu.

Weitere Informationen finden Sie unter [How to assign apps to groups with Microsoft Intune (Zuweisen von Apps zu Gruppen mit Microsoft Intune)](apps-deploy.md).

> [!Note]
> Nach dem Release werden keine MDM-App-Zuweisungen mehr in der klassischen Intune-Konsole angezeigt, und Sie können sie nicht mehr bearbeiten. Allerdings können Sie die Azure-Konsole oder die Intune-Graph-API verwenden, um Ihre App-Zuweisungen festzulegen.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Verwalten von Android for Work-Geräten unabhängig von Android-Geräten <!-- 1490731 -->
Intune unterstützt das Verwalten von Registrierungen von Android for Work-Geräten unabhängig von der Android-Plattform. Diese Einstellungen werden unter **Geräteregistrierung** > **Registrierungsbeschränkungen** > **Gerätetypbeschränkungen** verwaltet. (Zuvor waren sie unter **Geräteregistrierung** > **Android for Work-Registrierung** > **Android for Work-Registrierungseinstellungen** zu finden.)

Standardmäßig ändern sich die Android for Work-Geräteeinstellungen gegenüber Ihren Android-Geräteeinstellungen nicht. Dies ändert sich allerdings, nachdem Sie ihre Android for Work-Einstellungen geändert haben.
 
Wenn Sie die private Android for Work-Registrierung blockieren, können sich nur unternehmenseigene Android-Geräte als Android for Work-Geräte registrieren.

Ziehen Sie folgendes in Betracht, wenn Sie mit den neuen Einstellungen arbeiten:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung zuvor noch nie integriert haben
Die neue Android for Work Plattform wird in den Standardgerätetypbeschränkungen blockiert. Nachdem Sie die Funktion integriert haben, können Sie zulassen, dass sich Geräte mit Android for Work registrieren. Ändern Sie dafür die Standardeinstellungen, oder erstellen Sie eine neue Gerätetypbeschränkung, um die Standardgerätetypbeschränkungen zu ersetzen.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung bereits integriert haben
Wenn Sie zuvor bereits eine Integration vorgenommen haben, hängt Ihre Situation von den von Ihnen ausgewählten Einstellungen ab:

| Einstellung | Android for Work-Status in den Standardgerätetypbeschränkungen | Hinweise |
| --- | --- | --- |
| **Alle Geräte als Android-Geräte verwalten** | Gesperrt | Alle Android-Geräte müssen sich ohne Android for Work registrieren. |
| **Unterstützte Geräte als Android for Work-Geräte verwalten** | Zugelassen | Alle Android-Geräte, die Android for Work unterstützen, müssen sich mit Android for Work registrieren. |
| **Nur unterstützte Geräte für Benutzer in diesen Gruppen als Android for Work-Geräte verwalten** | Gesperrt | Eine separate Richtlinie für Gerätetypbeschränkungen wurde erstellt, um die Standareinstellungen außer Kraft zu setzen. Diese Richtlinie definiert die Gruppen, für die Sie zuvor die Android for Work-Registrierung zugelassen haben. Benutzer der ausgewählten Gruppen dürfen ihre Android for Work-Geräte weiterhin registrieren. Alle anderen Benutzer können sich nicht mit Android for Work registrieren. |

In beiden Fällen wird die von Ihnen vorgesehene Regulierung beibehalten. Von Ihrer Seite ist kein weiterer Vorgang erforderlich, um die globalen oder gruppenbedingten Zulassungen von Android for Work in Ihrer Umgebung zu verwalten.

Die Änderungen werden mit dem Update im November eingeführt, allerdings kann es einige Zeit dauern, bis sie auch auf Ihrem Konto ausgeführt werden. Sie erhalten im Office 365-Portal eine Bestätigungsnachricht, wenn diese Änderungen auf Ihrem Konto vorgenommen worden sind.


### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurieren einer PIN für eine iOS-App <!-- 1586774 -->
Bald erhalten Sie eine PIN für angesteuerte iOS-Apps. Sie können die Anforderungen für die PIN und das Ablaufdatum in Tagen im Azure-Portal konfigurieren. Falls erforderlich wird von dem Benutzer verlangt, eine neue PIN festzulegen und zu verwenden, bevor er Zugriff auf eine iOS-App erhält. Nur iOS-Apps, die einen App-Schutz mit dem Intune App SDK aktiviert haben, unterstützen diese Funktion.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Update der Benutzeroberfläche für die Unternehmensportal-App für iOS <!--1412866-->

Ein größeres Update der Benutzeroberfläche soll in der Unternehmensportal-App für iOS veröffentlicht werden. In dem Update soll das Design vollständig umgestaltet werden. Das bedeutet, die Ansicht soll modernisiert und die Benutzerfreundlichkeit und Barrierefreiheit verbessert werden. Alle aktuellen Funktionen des iOS-Unternehmensportals sollen erhalten bleiben.

Sie können über das Apple TestFlight-Programm der aktualisierten Unternehmensportal-App für iOS eine Vorschauversion verwenden und Feedback übermitteln. Registrieren Sie sich unter „https://aka.ms/intune_ios_cp_testflight“, um Zugriff auf TestFlight zu erhalten. 

![Erste Bilder zur neuen Unternehmensportal-App unter iOS](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-Websites können die App „Intune Managed Browser“ erfordern und unterstützen die einmalige Anmeldung für diese (öffentliche Vorschau) <!-- 710595 -->   
Mithilfe von Azure Active Directory (Azure AD) können Sie den Zugriff auf Websites durch mobile Geräte auf die App „Intune Managed Browser“ beschränken. Im verwalteten Browser bleiben die Websitedaten sicher und getrennt von den persönlichen Daten des Benutzers. Zusätzlich unterstützt der Managed Browser die Funktionen für einmaliges Anmelden für Websites, die von Azure AD geschützt werden. Das Anmelden beim Managed Browser oder das Verwenden desselben auf einem Gerät mit einer anderen App, die von Intune verwaltet wird, ermöglicht es dem Managed Browser, auf Unternehmenswebsites zuzugreifen, die von Azure AD geschützt werden, ohne dass der Benutzer seine Anmeldeinformationen eingeben muss. Diese Funktion gilt für Websites wie Outlook Web Access (OWA) und SharePoint Online sowie für andere Unternehmenswebsites wie Intranetressourcen, auf die über den Azure-App-Proxy zugegriffen wird.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Unterstützung für die Windows 10-Editionsupgraderichtlinie <!-- 903672(archived), 1119689 -->  
Durch das Erstellen einer Windows 10-Editionsupgraderichtlinie können Sie für Windows 10-Geräte ein Upgrade auf folgende Betriebssysteme durchführen: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education und Windows 10 Professional Education N. Weitere Informationen zu Windows 10-Editionsupgrades finden Sie unter [Konfigurieren von Windows 10-Editionsupgrades](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune-App-Schutz und Citrix MDX-Entwicklungstools <!-- 709185 -->
Sie können Geräte und Apps mit einer Kombination aus Citrix XenMobile MDX und Microsoft Intune verwalten. Dadurch können Sie Apps mit der Intune-App-Schutzrichtlinie verwalten, während Sie die mVPN-Technologie von Citrix verwenden.

Sie können ein Coderepository suchen, das das App Wrapping Tool von Intune und des Intune App SDK für iOS und Android enthält, das von der Citrix MDX mVPN-Technologie integriert wird.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Umleiten von macOS-Benutzern zur neuen Unternehmensportal-App <!--1380728-->   
Wenn ein Benutzer sich bei der Website des Unternehmensportals anmeldet, um sein macOS-Gerät zu registrieren, wird dieser zum Download der neuen Unternehmensportal-App für macOS umgeleitet, um den Vorgang abzuschließen. Dies tritt bei macOS-Geräten auf, die OS X El Capitan 10.11 oder höher verwenden. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Unterstützung für Intune Managed Browser von iOS und Android <!-- 1374196 -->
Ab Oktober 2017 unterstützt die Intune Managed Browser-App für Android nur noch Geräte mit Android 4.4 oder höher. Die Intune Managed Browser-App unter iOS unterstützt nur noch Geräte mit iOS 9.0 oder höher. Frühere Versionen von Android und iOS können Managed Browser weiterhin verwenden, allerdings können keine neuen Versionen der App installiert werden, und einige App-Funktionen sind möglicherweise nicht verfügbar. Es wird empfohlen, dass Sie diese Geräte auf eine unterstützte Betriebssystemversion aktualisieren.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbesserte Fehlermeldungen für den Fall, wenn ein Benutzer die Höchstzahl von zur Registrierung erlaubten Geräten erreicht <!-- 1270370 -->
Statt einer generischen Fehlermeldung sehen Benutzer mit Android-Geräten eine an Benutzer gerichtete, handlungsrelevante Fehlermeldung: „You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin.“ (Sie haben die maximale Anzahl an Geräten registriert, die von Ihrem IT-Administrator erlaubt wurden. Bitte entfernen Sie ein registriertes Gerät, oder wenden Sie sich an Ihren IT-Administrator.“)




## <a name="notices"></a>Benachrichtigungen

Derzeit gibt es keine aktiven Benachrichtigungen.




### <a name="see-also"></a>Siehe auch
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new.md).
