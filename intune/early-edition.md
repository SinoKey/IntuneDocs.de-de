---
title: Early Edition
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4fd810529732d2b24b948eb0ae741d37e0fb59e
ms.sourcegitcommit: d64b03bff0566f08d88ecb488dd48f19af74cab3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>Die Early Edition für Microsoft Intune – Dezember 2017

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

### <a name="app-protection-policies-----679615---"></a>App-Schutzrichtlinien <!-- 679615 -->
Mit den Intune-App-Schutzrichtlinien können Sie globale Standardrichtlinien erstellen und damit den Schutz für alle Benutzer im gesamten Mandanten schnell aktivieren.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Widerrufen von Apps aus dem iOS Volume Purchase Program <!-- 820863 -->
Für ein bestimmtes Gerät, das mindestens eine iOS VPP-App (Volume Purchase Program) enthält, können Sie die zugehörige gerätebasierte App-Lizenz für das Gerät widerrufen. Durch das Widerrufen einer App-Lizenz wird die zugehörige VPP-App nicht vom Gerät deinstalliert. Zum Deinstallieren einer VPP-App müssen Sie die Zuweisungsaktion in **Deinstallieren** ändern. Weitere Informationen finden Sie unter [Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Widerrufen von Lizenzen für ein iOS Volume Purchase Program-Token <!-- 820870 -->
Sie können die Lizenz für alle iOS VPP-Apps (Volume Purchase Program) für ein bestimmtes VPP-Token widerrufen.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Löschen eines iOS Volume Purchase Program-Tokens <!-- 820879 -->
Sie können das iOS VPP-Token (Volume Purchase Program) über die Konsole löschen. Dies kann erforderlich sein, wenn doppelte Instanzen eines VPP-Tokens vorliegen.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Berichterstellung zum Check-In von NAC-Geräten (Network Access Control) <!-- 1232250 -->
Vor dieser Änderung konnten IT-Administratoren von der Intune-Seite aus nicht feststellen, ob ein mit NAC verwaltetes Gerät mit der zugehörigen NAC-Lösung kommunizierte oder nicht. Wenn ein mit NAC verwaltetes Gerät nicht mit der zugehörigen NAC-Lösung kommuniziert, wird das Gerät von der NAC-Lösung als nicht konform betrachtet. In diesem Fall wird es von der NAC-Lösung selbst und demzufolge auch von bedingten Zugriffsrichtlinien blockiert, die auf dem Gerätekonformitätsstatus beruhen.

Durch diese Änderung können IT-Administratoren anzeigen, welche mit NAC verwalteten Geräte erfolgreich mit der zugehörigen NAC-Lösung kommuniziert haben. Diese neue Funktion besteht aus zwei neuen Überwachungsfunktionen, die sich in der Gerätekonformitätsworkload innerhalb von Intune befinden. Die Statistiken werden folgendermaßen angezeigt:
- **Durchschnittliche NAC-Aufrufe in der letzten Stunde**
- **Letzte eingehende NAC-Anforderung (Datum/Uhrzeit)**

### <a name="new-ios-device-action------1244701---"></a>Neue iOS-Geräteaktion <!-- 1244701 -->
Sie können überwachte iOS 10.3-Geräte herunterfahren. Diese Aktion fährt das Gerät sofort und ohne Warnung für den Endbenutzer herunter. Die Aktion **Herunterfahren (nur überwacht)** finden Sie in den Geräteeigenschaften bei der Auswahl eines Geräts in der Workload **Gerät**.

### <a name="palo-alto-vpn-now-supported----1333680-eeready---"></a>Palo Alto-VPN jetzt unterstützt <!-- 1333680 eeready -->
In der Liste **Verbindungstyp** wird das Palo Alto-VPN aufgeführt, wenn Sie Ihr Basis-VPN konfigurieren.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>Unterstützung für mehrere Connectors für die Behandlung von SCEP- und PFX-Zertifikaten <!-- 1361755 eeready -->
Kunden, die den lokalen NDES-Connector zum Übermitteln von Zertifikaten an Geräte verwenden, können mehrere Connectors in einem einzelnen Mandanten konfigurieren.

Diese neue Funktion unterstützt das folgende Szenario:

- **Hochverfügbarkeit**

    Jeder NDES-Connector bezieht Zertifikatanforderungen mithilfe von Pull von Intune.  Wenn ein NDES-Connector offline geschaltet wird, kann der andere Connector weiterhin Anforderungen verarbeiten.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Neue Einstellung für die automatische erneute Bereitstellung <!-- 1469168 -->
Mit dieser Einstellung können Benutzer mit Administratorrechten alle Benutzerdaten und -einstellungen über **STRG+Windows+R** vom Sperrbildschirm des Geräts aus löschen. Das Gerät wird automatisch neu konfiguriert und bei der Verwaltung neu registriert.

Diese Einstellung finden Sie unter „Windows 10“ > „Geräteeinschränkungen“ > „Allgemein“ > “Automatische erneute Bereitstellung“.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>Installieren von Office-Apps auf macOS-Geräten <!-- 1494311 -->
Sie können Office-Apps auf macOS-Geräten installieren. Dieser neue App-Typ ermöglicht Ihnen die Installation von Word, Excel, PowerPoint, Outlook und OneNote. Diese Apps sind auch im Umfang von Microsoft AutoUpdater (MAU) enthalten, um Ihre Apps sicher und auf dem neuesten Stand zu halten.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Unterstützung für Surface Hub-Ressourcenkonto <!-- 1566442 eeready -->
Eine neue Geräteaktion wird hinzugefügt, damit Administratoren das einem Surface Hub zugeordnete Ressourcenkonto definieren und aktualisieren können.

Das Ressourcenkonto wird von einem Surface Hub für die Authentifizierung bei Skype/Exchange verwendet, um seine Teilnahme an einer Besprechung zu ermöglichen. Sie können ein eindeutiges Ressourcenkonto erstellen, damit der Surface Hub in der Besprechung als Konferenzraum angezeigt wird. Beispielsweise kann das Ressourcenkonto als *Konferenzraum B41/6233* angezeigt werden. Das Ressourcenkonto (auch als Gerätekonto bezeichnet) für den Surface Hub muss in der Regel für den Standort des Konferenzraums konfiguriert werden, wenn andere Parameter des Ressourcenkontos geändert werden müssen.

Wenn Administratoren das Ressourcenkonto auf einem Gerät aktualisieren möchten, müssen sie die aktuellen Active Directory-/Azure Active Directory-Anmeldeinformationen angeben, die dem Gerät zugeordnet sind. Wenn die Kennwortrotation für das Gerät aktiviert ist, müssen Administratoren zu Azure Active Directory wechseln, um das Kennwort zu finden.

> [!NOTE]
> Alle Felder werden im Paket nach unten gesendet und überschreiben alle Felder, die zuvor konfiguriert wurden. Leere Felder überschreiben auch vorhandene Felder.

Administratoren können folgende Einstellungen konfigurieren:

- **Ressourcenkonto**  

   - **Active Directory-Benutzer**   
   Domänenname\Benutzername oder Benutzerprinzipalname (UPN): user@domainname.com
   - **Passwort**


- **Optionaler Ressourcenkontoparameter** (muss über das angegebene Ressourcenkonto festgelegt werden)
   - **Zeitraum für Kennwortrotation**   
     Stellt sicher, dass das Kontokennwort aus Sicherheitsgründen jede Woche automatisch durch den Surface Hub aktualisiert wird. Um nach dem Aktivieren dieser Option Parameter zu konfigurieren, muss das Kennwort für das Konto in Azure Active Directory zuerst zurückgesetzt werden.

   - **SIP-Adresse (Session Initiation-Protokoll)**    
     Wird nur verwendet, wenn die AutoErmittlung nicht möglich ist.

   - **E-Mail**    
     E-Mail-Adresse des Geräte-/Ressourcenkontos.

   - **Exchange-Server**    
     Nur erforderlich, wenn die AutoErmittlung nicht möglich ist.

   - **Kalendersynchronisierung**    
     Gibt an, ob die Kalendersynchronisierung und andere Exchange-Serverdienste aktiviert sind. Beispiel: die Besprechungssynchronisierung.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune stellt jetzt den Vorgang zur Kontoverschiebung bereit <!-- 1573558, 1579830 -->
Bei der **Kontoverschiebung** wird ein Mandant von einer Azure-Skalierungseinheit (ASU) zu einer anderen migriert. Die **Kontoverschiebung** kann für vom Kunden eingeleitete Szenarien verwendet werden, wenn Sie sie vom Intune-Supportteam anfordern. Sie kann auch ein von Microsoft gesteuertes Szenario sein, wenn Microsoft Anpassungen am Dienst im Back-End vornehmen muss. Während der **Kontoverschiebung** wechselt der Mandant zum schreibgeschützten Modus (ROM). Dienstvorgänge wie die Registrierung, das Umbenennen von Geräten oder das Aktualisieren des Kompatibilitätsstatus sind während des ROM-Zeitraums nicht möglich.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Neue Einstellungen des WDSC-Gerätekonfigurationsprofils (Windows Defender Security Center) <!-- 1335507 -->
Unter dem Endpunktschutz namens **Windows Defender Security Center** fügt Intune einen neuen Abschnitt mit Einstellungen des Gerätekonfigurationsprofils hinzu. IT-Administratoren können konfigurieren, welche ///Komponenten der Windows Defender Security Center-App für Endbenutzer zugänglich sind. Wenn ein IT-Administrator eine Komponente in der Windows Defender Security Center-App ausblendet, werden Benachrichtigungen in Zusammenhang mit der ausgeblendeten Komponente nicht auf dem Gerät des Benutzers angezeigt.

Folgende Komponenten können von Administratoren aus den Einstellungen des Gerätekonfigurationsprofils von Windows Defender Security Center ausgeblendet werden:
- Viren- und Bedrohungsschutz
- Geräteleistung und -integrität
- Firewall- und Netzwerkschutz
- App- und Browsersteuerung
- Familienoptionen

IT-Administratoren können auch anpassen, welche Benutzer Benachrichtigungen empfangen können. Beispielsweise können Sie konfigurieren, ob Benutzer alle von sichtbaren Komponenten in WDSC generierten Benachrichtigungen oder nur kritische Benachrichtigungen erhalten. Zu nicht kritischen Benachrichtigungen gehören regelmäßige Zusammenfassungen von Windows Defender Antivirus-Aktivitäten und Benachrichtigungen bei Abschluss von Überprüfungen. Alle übrigen Benachrichtigungen gelten als kritisch. Darüber hinaus können Sie auch den Inhalt der Benachrichtigung anpassen. Beispielsweise können Sie die IT-Kontaktinformationen angeben, um sie in die Benachrichtigungen einzubetten, die auf den Geräten der Benutzer angezeigt werden.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Zuweisen von mobilen Office 365-Apps an iOS- und Android-Geräte mithilfe des integrierten App-Typs <!-- 1332318 -->
Der **integrierte** App-Typ erleichtert es, Office 365-Apps für die iOS- und Android-Geräte, die Sie verwalten, zu erstellen und sie diesen zuzuweisen. Zu diesen Apps gehören Office 365-Apps wie Word, Excel, PowerPoint und OneDrive. Sie können bestimmte Apps dem App-Typen zuweisen und die Konfiguration der App-Informationen bearbeiten.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Unterstützen des einmaligen Anmeldens (Single Sign-On, SSO) für iOS <!-- 1333645 -->  
Sie können SSO für iOS-Benutzer verwenden. Die iOS-Apps, die so programmiert wurden, dass sie nach Benutzeranmeldeinformationen in der Payload für einmaliges Anmelden suchen, sind mit diesem Payload-Konfigurationsupdate weiterhin funktionsfähig. Sie können auch den UPN und die Intune-Geräte-ID verwenden, um den Prinzipalnamen und den Bereich zu identifizieren.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>App-Bestand-API zur Bedrohungserkennung auf Mobilgeräten unter iOS 11 <!-- 1391759 -->
Intune erfasst sowohl von privaten als auch von unternehmenseigenen Geräten Informationen zum App-Bestand und stellt diese für Anbieter von Bedrohungserkennung auf Mobilgeräten (Mobile Thread Detection, MTD) wie Lookout for Work zur Verfügung. Sie können damit Informationen zum App-Bestand auf iOS 11-Geräten (oder höher) erfassen.

**App-Bestand**  
Die Bestände von sowohl unternehmenseigenen als auch privaten iOS 11-Geräten (oder höher) werden an Ihren MTD-Dienstanbieter übermittelt. Die Daten in den App-Beständen umfassen:

 - App-ID
 - App-Version
 - Kurzversion der App
 - App-Name
 - Größe des App-Pakets
 - Dynamische Größe der App
 - App wird geprüft oder nicht
 - App wird verwaltet oder nicht

### <a name="audit-updates----1412961---"></a>Überwachungsupdates <!-- 1412961 -->  
Die Intune-Überwachung stellt einen Datensatz mit Änderungsvorgängen im Zusammenhang mit Intune zur Verfügung.  Alle Vorgänge zum Erstellen, Aktualisieren, Löschen und von Remoteaufgaben werden erfasst und für ein Jahr gespeichert.  Im Azure-Portal werden die Überwachungsdaten der letzten 30 Tage filterbar in sämtlichen Workloads dargestellt.  Eine dazugehörige Graph-API ermöglicht den Abruf von Überwachungsdaten, die über ein Jahr hinweg gespeichert wurden. 

Die Überwachungsfunktion finden Sie unter der Gruppe **MONITOR**. Für jede Workload gibt es das Menüelement **Überwachungsprotokolle**.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Zulässige Textprotokolle verwalteter Apps <!-- 1414050  -->
Apps, die über das Intune App SDK verwaltet werden, können SMS-Nachrichten versenden.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Remote-Neustart von iOS-Geräten (nur überwacht) <!-- 1424595 -->
Sie können bei einem überwachten iOS 10.3-Gerät (und höher) über eine Geräteaktion einen Neustart auslösen. Weitere Informationen zum Geräteneustart finden Sie unter [Remotely restart devices with Intune (Remote-Neustart von Geräten mit Intune)](device-restart.md).

> [!Note]  
> Für diesen Befehl wird ein überwachtes Gerät und das Zugriffsrecht **Gerätesperre** benötigt. Das Gerät wird sofort neu gestartet. Kennungsgeschützte iOS-Geräte verbinden Sie nach dem Neustart nicht wieder mit dem WLAN-Netzwerk und können unter Umständen nicht mehr mit dem Server kommunizieren.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Remote-Sperren von verwalteten macOS-Geräten durch Intune <!-- 1437691 -->
Sie können ein verlorenes macOS-Gerät sperren und eine sechsstellige Wiederherstellungs-PIN festlegen. Wenn das Gerät gesperrt ist, wird im Blatt **Device overview** (Geräteübersicht) die PIN solange angezeigt, bis eine andere Geräteaktion gesendet wurde.

Weitere Informationen finden Sie unter [Remotely lock managed devices with Intune (Remote-Sperren von verwalteten Geräten durch Intune)](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Häufigkeitseinstellungen von Windows Defender Advanced Threat Protection-Berichten <!--- 1455974  --->
Der Dienst Windows Defender Advanced Threat Protection (WDETP) ermöglicht es Administratoren, zu verwalten, wie häufig für verwaltete Geräte Berichte erstellt werden sollen. Mit der neuen Option **Häufigkeit von Telemetrieberichten erhöhen** erfasst WDETP häufiger Daten und prüft Risiken. Die Standardeinstellung für die Berichterstellung optimiert Geschwindigkeit und Leistung. Für Geräte, die ein hohes Risiko darstellen,kann es sehr nützlich sein, häufiger Berichte zu erstellen. Diese Einstellung finden Sie in den **Gerätekonfigurationen** in dem Profil **Windows Defender ATP**.

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

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Unterstützung von mehreren Konnektoren für den Registrierungsdienst für Netzwerkgeräte <!-- 1528104 -->
Über den Registrierungsdienst für Netzwerkgeräte (Network Device Enrollment Service NDES) können Mobilgeräte, die ohne Domänen-Anmeldeinformationen ausgeführt werden, Zertifikate auf Basis des Simple Certificate Enrollment-Protokolls (SCEP) abrufen. Mit diesem Update werden mehrere NDES-Konnektoren unterstützt.

### <a name="new-scep-profile-details-supported----1559808---"></a>Unterstützen von neuen SCEP-Profildetails <!-- 1559808 -->
Administratoren können zusätzliche Einstellungen festlegen, wenn sie ein SCEP-Profil auf Windows-, iOS-, macOS- und Android-Plattformen erstellen.  Administratoren können die IMEI, die Seriennummer oder allgemeine Namen, einschließlich der E-Mail-Adresse im Format des Antragstellernamens, festlegen.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurieren einer PIN für eine iOS-App <!-- 1586774 -->
Bald erhalten Sie eine PIN für angesteuerte iOS-Apps. Sie können die Anforderungen für die PIN und das Ablaufdatum in Tagen im Azure-Portal konfigurieren. Falls erforderlich wird von dem Benutzer verlangt, eine neue PIN festzulegen und zu verwenden, bevor er Zugriff auf eine iOS-App erhält. Nur iOS-Apps, die einen App-Schutz mit dem Intune App SDK aktiviert haben, unterstützen diese Funktion.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Beibehalten von Daten während einer Zurücksetzung auf Werkseinstellungen <!-- 1588489 -->
Ein Support für eine neue Funktion zur Zurücksetzung auf Windows-Werkseinstellungen wird hinzugefügt. Administratoren können jetzt angeben, ob die Geräteregistrierung und andere bereitgestellte Daten während einer Zurücksetzung auf Werkseinstellungen auf einem Gerät erhalten bleiben sollen. 
 
Die folgenden Daten bleiben während der Zurücksetzung auf Werkseinstellungen erhalten:
- Dem Gerät zugeordnete Benutzerkonten
- Zustand des Computers (der Domäne beigetreten, AADJ)
- MDM-Registrierung
- Über OEM installierte Apps (Store- und Win32-Apps)
- Benutzerprofil
- Benutzerdaten außerhalb des Benutzerprofils
- Automatische Anmeldung des Benutzers
 
Die folgenden Daten bleiben nicht erhalten:
- Benutzerdateien
- Vom Benutzer installierte Apps (Store- und Win32-Apps)
- Geräteeinstellungen, die nicht dem Standard entsprechen 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Bericht über den Installationsstatus der App jetzt als Balkendiagramm <!-- 1249446 -->  
Der Bericht über den **Installationsstatus der App**, der in jeder App über die **App**-Liste im Workload **Mobile Apps** verfügbar ist, wird zukünftig als Balkendiagramm dargestellt.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Hinzufügen der Funktion „Find my iPhone“ („Mein iPhone finden“) für private Geräte <!--1427287-->
Ihnen wird angezeigt, ob für iOS-Geräte eine Aktivierungssperre aktiviert ist. Diese Funktion konnten Sie zuvor im klassischen Intune-Portal finden.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruppen zugeordnete Registrierungseinschränkungen <!-- 747598 -->
Als Intune-Administrator können Sie benutzerdefinierte Beschränkungen für Gerätetypen und -grenzwerte für Benutzergruppen erstellen.
 
Im Intune Azure-Portal können Sie bis zu 25 Instanzen für jeden Beschränkungstypen erstellen, die Sie Benutzergruppen zuordnen können. Gruppen zugeordnete Beschränkungen setzen die Standardbeschränkungen außer Kraft.
 
Sämtliche Instanzen eines Beschränkungstypen werden in einer Liste mit einer strengen Reihenfolge verwaltet. Diese Reihenfolge definiert einen Prioritätswert für die Lösung von Konflikten. Ein Benutzer, der von mehr als einer Beschränkungsinstanz betroffen ist, wird nur von der Instanz mit dem höchsten Prioritätswert eingeschränkt. Sie können die Priorität einer vorhandenen Instanz ändern, indem Sie sie an eine andere Stelle in der Liste ziehen. 
 
Diese Funktion wird mit der Migration von Android for Work-Einstellungen aus dem Android for Work-Registrierungsmenü in das Registrierungsmenü freigegeben. Da diese Migration einige Tage in Anspruch nehmen kann, wird Ihr Konto möglicherweise auf andere Teile des Releases im November aktualisiert, bevor die Gruppenzuweisung für Registrierungsbeschränkungen aktiviert ist.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Anzeigen von Zuweisungen des Windows 10-Updaterings <!-- 1621837 -->
Wenn Sie für den angezeigten Benutzer **Probleme behandeln**, werden Ihnen sämtliche Zuweisungen des Windows 10-Updaterings angezeigt.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-Websites können die App „Intune Managed Browser“ erfordern und unterstützen die einmalige Anmeldung für diese (öffentliche Vorschau) <!-- 710595 -->   
Mithilfe von Azure Active Directory (Azure AD) können Sie den Zugriff auf Websites durch mobile Geräte auf die App „Intune Managed Browser“ beschränken. Im verwalteten Browser bleiben die Websitedaten sicher und getrennt von den persönlichen Daten des Benutzers. Zusätzlich unterstützt der Managed Browser die Funktionen für einmaliges Anmelden für Websites, die von Azure AD geschützt werden. Das Anmelden beim Managed Browser oder das Verwenden desselben auf einem Gerät mit einer anderen App, die von Intune verwaltet wird, ermöglicht es dem Managed Browser, auf Unternehmenswebsites zuzugreifen, die von Azure AD geschützt werden, ohne dass der Benutzer seine Anmeldeinformationen eingeben muss. Diese Funktion gilt für Websites wie Outlook Web Access (OWA) und SharePoint Online sowie für andere Unternehmenswebsites wie Intranetressourcen, auf die über den Azure-App-Proxy zugegriffen wird.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Behandlung von Problemen bei der Registrierung <!--- 746324 --->  
Im Arbeitsbereich „Problembehandlung“ werden Probleme bei der Registrierung der Benutzer angezeigt. Die Details zum Problem und die vorgeschlagenen Wiederherstellungsschritte können die Administratoren und Helpdeskbetreiber bei der Behandlung der Probleme unterstützen. Bestimmte Probleme bei der Registrierung werden nicht erfasst, und für einige Fehler liegen möglicherweise keine Wiederherstellungsvorschläge vor.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Unterstützung für die Windows 10-Editionsupgraderichtlinie <!-- 903672(archived), 1119689 -->  
Durch das Erstellen einer Windows 10-Editionsupgraderichtlinie können Sie für Windows 10-Geräte ein Upgrade auf folgende Betriebssysteme durchführen: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education und Windows 10 Professional Education N. Weitere Informationen zu Windows 10-Editionsupgrades finden Sie unter [Konfigurieren von Windows 10-Editionsupgrades](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Unterstützung für Lookout in Android for Work <!-- 1087312 -->   
Der Intune-Connector mit Lookout unterstützt die Verwendung der Lookout for Work-App auf Android for Work-Geräten. Sie können die Lookout-App innerhalb oder außerhalb des Containers bereitstellen.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune-App-Schutz und Citrix MDX-Entwicklungstools <!-- 709185 -->
Sie können Geräte und Apps mit einer Kombination aus Citrix XenMobile MDX und Microsoft Intune verwalten. Dadurch können Sie Apps mit der Intune-App-Schutzrichtlinie verwalten, während Sie die mVPN-Technologie von Citrix verwenden.

Sie können ein Coderepository suchen, das das App Wrapping Tool von Intune und des Intune App SDK für iOS und Android enthält, das von der Citrix MDX mVPN-Technologie integriert wird.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hochverfügbarkeit der Unterstützung von lokalem Exchange-Connector <!-- 676614 -->   
Sie können über mehrere Clientzugriffs-Serverrollen (CAS) für den lokalen Exchange-Connector verfügen. Bei einem Fehler des Haupt-Clientzugriffsservers empfängt der Exchange-Connector z.B. eine Abfrage, um auf andere Clientzugriffsserver zurückzugreifen. Durch diese Funktion wird sichergestellt, dass der Dienst nicht unterbrochen wird.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager Management Pack für Exchange-Connector <!-- 885457 -->   
Mit dem System Center Operations Manager Management Pack für den Exchange-Connector können Sie die Exchange-Connector-Protokolle analysieren. Dieses Management Pack bietet Ihnen bei der Behebung von Problemen verschiedene Möglichkeiten zur Überwachung von Intune.





## <a name="intune-apps"></a>Intune-Apps

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Unterstützen Ihrer Benutzer bei der eigenständigen Problemlösung über die Unternehmensportal-App für Android <!---1573324, 1573150, 1558616, 1564878--->
Die Unternehmensportal-App für Android fügt Anweisungen für Benutzer hinzu, damit sie Anwendungsfälle verstehen und, wenn möglich, selbst lösen können. 

- Eine neue Nachricht wird angezeigt, in der darüber informiert wird, dass eine Kompatibilitätsrichtlinie zur Verschlüsselung bereitgestellt wurde, aber der [Gerätehersteller das Gerät nicht](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) gemäß den von [Google empfohlenen Richtlinien] (https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean) verschlüsselt.
- Die Benutzer werden auf das (Azure Active Directory-Portal) [https://account.activedirectory.windowsazure.com/r/#/profile] geleitet, um ein Gerät zu entfernen, wenn sie die maximale Anzahl von Geräten, die hinzugefügt werden dürfen, überschritten haben. 
- Den Benutzern wird eine Anleitung zur Verfügung gestellt, die ihnen dabei helfen soll, [Fehler bei der Aktivierung auf Samsung KNOX-Geräten zu beheben](https://go.microsoft.com/fwlink/?linkid=859718) oder [den Energiesparmodus zu deaktivieren](/intune-user-help/power-saving-mode-android). Wenn keine dieser Lösungen bei der Behebung des Problems hilft, werden wir eine Erklärung zur Verfügung stellen, in der beschrieben wird, [wie Protokolle an Microsoft übermittelt werden können](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Neue „Lösungs“-Aktion für Android-Geräte verfügbar <!---1583480--->
In der Unternehmensportal-App für Android wird eine „Lösungs“-Aktion auf der Seite _Geräteeinstellungen aktualisieren_ eingeführt. Wenn der Benutzer diese Option auswählt, wird er direkt zu der Einstellung weitergeleitet, die dafür verantwortlich ist, dass das Gerät nicht kompatibel ist. Derzeit unterstützt die Unternehmensportal-App für Android diese Aktion für die Einstellungen [Gerätekennung](/intune-user-help/set-your-pin-or-password-android), [Geräteverschlüsselung](/intune-user-help/encrypt-your-device-android), [USB-Debuggen](/intune-user-help/you-need-to-turn-off-usb-debugging-android) und [Unbekannte Quellen](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Umleiten von macOS-Benutzern zur neuen Unternehmensportal-App <!--1380728-->   
Wenn ein Benutzer sich bei der Website des Unternehmensportals anmeldet, um sein macOS-Gerät zu registrieren, wird dieser zum Download der neuen Unternehmensportal-App für macOS umgeleitet, um den Vorgang abzuschließen. Dies tritt bei macOS-Geräten auf, die OS X El Capitan 10.11 oder höher verwenden. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps, die mit oder ohne Registrierung verfügbar sind, können nun installiert werden, ohne dass Sie zur Registrierung aufgefordert werden. <!-- 1334712 -->
Unternehmens-Apps, die mit oder ohne Registrierung in der Android-Unternehmensportal-App zur Verfügung gestellt wurden, können installiert werden, ohne dass Sie zur Registrierung aufgefordert werden.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Unterstützung für Intune Managed Browser von iOS und Android <!-- 1374196 -->
Ab Oktober 2017 unterstützt die Intune Managed Browser-App für Android nur noch Geräte mit Android 4.4 oder höher. Die Intune Managed Browser-App unter iOS unterstützt nur noch Geräte mit iOS 9.0 oder höher. Frühere Versionen von Android und iOS können Managed Browser weiterhin verwenden, allerdings können keine neuen Versionen der App installiert werden, und einige App-Funktionen sind möglicherweise nicht verfügbar. Es wird empfohlen, dass Sie diese Geräte auf eine unterstützte Betriebssystemversion aktualisieren.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbesserte Fehlermeldungen für den Fall, wenn ein Benutzer die Höchstzahl von zur Registrierung erlaubten Geräten erreicht <!-- 1270370 -->
Statt einer generischen Fehlermeldung sehen Benutzer eine freundliche, handlungsrelevante Fehlermeldung: „You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin.“ (Sie haben die maximale Anzahl an Geräten registriert, die von Ihrem IT-Administrator erlaubt wurden. Bitte entfernen Sie ein registriertes Gerät, oder wenden Sie sich an Ihren IT-Administrator.“)




## <a name="notices"></a>Benachrichtigungen

Derzeit gibt es keine aktiven Benachrichtigungen.




### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new.md).
