---
title: Archiv der Neuheiten | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## September 2016
## Neue Funktionen, Ankündigungen und Informationen
* [Bedingter Zugriff für Windows](#windows-conditional-access)
* [iOS 10-Unterstützung](#ios-10-support)
* [Das App Wrapping-Tool unterstützt MAM ohne Geräteregistrierung für Android und iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Die Umstellung von Intune-Gruppen auf Azure Active Directory beginnt im September](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-Integration zum Schutz von Android-Geräten](#lookout-integration-to-protect-android-devices)
* [Unternehmensportal-Updates für Android, iOS und Windows](#company-portal-updates)
* [Intune-Glossar](#intune-glossary)
* [Was steht an?](#whats-coming)

## Bedingter Zugriff für Windows
Sie können jetzt über die Intune-Verwaltungskonsole Richtlinien für bedingten Zugriff erstellen, um den Zugriff von Windows-PCs auf Exchange Online und SharePoint Online zu blockieren. Sie können auch Richtlinien für bedingten Zugriff erstellen, um den Zugriff auf Office-Desktop- und universelle Anwendungen zu blockieren.

## iOS 10-Unterstützung
Vorhandene Intune-MDM- und-MAM-Szenarien sind mit iOS 10 kompatibel. Tipps finden Sie im [Intune-Supportteamblog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## Das App Wrapping-Tool unterstützt MAM ohne Geräteregistrierung für Android und iOS
Das Intune App Wrapping-Tool ist ein Befehlszeilentool, das verwendet wird, um Intune-MAM in Branchen-Apps (LOB, Line-of-Business) für iOS und Android zu aktivieren . Es stellt die einfachste Möglichkeit dar, das Intune MAM-SDK in Ihre App zu integrieren, sodass Ihre App die durch Intune bereitgestellten MAM-Richtlinien durchsetzen kann. MAM-Richtlinien bieten Ihnen diese Möglichkeiten:

1. Verschlüsseln der Daten der App.
2. Vorschreiben der Eingabe einer PIN beim Starten der App durch den Information Worker.
3. Einschränken der Übermittlung von Daten durch die App auf andere verwaltete Apps.
4. Verhindern der Sicherung von Daten nach Android, iTunes und iCloud durch die App.
5. Ausschneiden, Kopieren und Einfügen nur im Zusammenwirken mit anderen verwalteten Apps.

Die öffentliche Vorschau des aktualisierten Intune App Wrapping-Tools unterstützt jetzt MAM ohne Geräteregistrierung für interne Branchen-Apps unter iOS und Android. Das bedeutet, dass Ihre Benutzer ihre Geräte nicht bei Intune registrieren müssen, um MAM-aktivierte Branchen-Apps zu verwenden.

Jeder kann die öffentliche Vorschausoftware testen und die nützliche Dokumentation lesen, die sich auf dem msintuneappsdk-GitHub befindet:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Damit Sie das Microsoft Intune App Wrapper für Android und iOS Pre-Release installieren und verwenden können, müssen diese Voraussetzungen erfüllt sein:

* Sie müssen die Microsoft-Lizenzbedingungen für das Microsoft Intune App Wrapping-Tool für Android und iOS Pre-Release lesen
* Drucken Sie die Lizenzbedingungen aus, und heben Sie eine Kopie für Ihre Unterlagen auf. Indem Sie das Microsoft Intune App Wrapping-Tool für Android Pre-Release herunterladen und verwenden, stimmen Sie diesen Lizenzbedingungen zu. Wenn Sie sie nicht akzeptieren, dürfen Sie die Software nicht verwenden.
<!---TFS 1235607--->

## Die Umstellung von Intune-Gruppen auf Azure Active Directory beginnt im September
Einige neue Intune-Konten verwenden Azure Active Directory-Sicherheitsgruppen anstelle von Intune-Benutzergruppen. Sie werden bemerken, dass Sie mit Sicherheitsgruppen arbeiten, da die Gruppenseite auf dem Intune-Portal dann über einen Link zum Azure-Verwaltungsportal verfügt.

## Lookout-Integration zum Schutz von Android-Geräten
Microsoft integriert die Lookout-Lösung zum Schutz vor Bedrohungen auf mobilen Geräten, um mobile Android-Geräte durch das Erkennen von Schadsoftware, gefährlichen Apps und mehr auf Geräten zu schützen. Mithilfe der Lösung von Lookout können Sie die Bedrohungsstufe bestimmen und konfigurieren. Sie können in Intune eine Regel der Kompatibilitätsrichtlinie erstellen, um die Gerätekonformität auf der Grundlage der Risikobewertung durch Lookout zu bestimmen. Mithilfe von Richtlinien für den bedingten Zugriff können Sie den Zugriff auf Unternehmensressourcen auf der Basis des Kompatibilitätsstatus des Geräts zulassen oder blockieren.

Endbenutzer nicht kompatibler Geräte werden zur Registrierung aufgefordert, und die Installation der Lookout for Work-Anwendung auf Android-Geräten, die Aktivierung der App und die Behebung der in der Lookout for Work-Anwendung erkannten Bedrohungen wird vorgeschrieben, bevor der Zugriff erteilt wird. Weitere Informationen finden Sie unter [Einschränken des Zugriffs auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko](restrict-access-based-on-device-network-app-risk.md).


## Aktualisierungen am Unternehmensportal

### Android

**Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android**<br/>
Dem Unternehmensportal für Android wurde auf der Startseite ein neues Symbol „Benachrichtigungen“ hinzugefügt. Beim Tippen auf dieses Symbol wird auf die Seite „Benachrichtigungen“ zugegriffen, die Ihren Endbenutzern alle Elemente in der Unternehmensportal-App anzeigt, die ihr Eingreifen erfordern, etwa inkompatible Geräte, Aktualisierung der Registrierung und Aktivierung der Registrierung. Das iOS-Unternehmensportal verfügt bereits über diese Benachrichtigungsfunktionalität. Durch die neue Seite „Benachrichtigungen“ wird Benutzern nicht bei jedem Starten oder erneuten Anzeigen des Unternehmensportals die Seite „Einrichten des Unternehmenszugriffs“ angezeigt, sofern das Gerät bereits registriert ist. Wenn Sie eine eigene Hilfestellung für Endbenutzer erstellen, empfiehlt es sich, Ihre Dokumentation entsprechend zu aktualisieren, um dieser Änderung Rechnung zu tragen. Aktualisierte Screenshots finden Sie [hier](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Abgeben von Feedback im Unternehmensportal für Android**</br>
Dem Menü des Unternehmensportals für Android wurde ein neues Element hinzugefügt. Nach Tippen auf **Hilfe und Feedback** werden drei Aktionen angezeigt:
* Über **Hilfe anfordern** können Sie Ihrer IT-Abteilung Probleme mit dem Unternehmensportal melden. Die IT erstellt eine E-Mail mit Ihrem E-Mail-Client, an die die Unternehmensportalprotokolle angefügt werden. **Hilfe anfordern** ersetzt die Option **Daten senden** auf der Seite **Einstellungen**.
* Verwenden Sie **Feedback abgeben**, um dem für das Unternehmensportal zuständigen Team Feedback zu geben.
* Verwenden Sie **App bewerten**, um für die Unternehmensportal-App eine Bewertung oder Kritik auf Google Play zu hinterlassen.

### iOS
**Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
Alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS müssen jetzt die aktuelle Version verwenden. Neue Benutzer können ausschließlich die neueste Version herunterladen, und aktuelle Benutzer müssen ein Update auf sie ausführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen das Unternehmensportal erst dann nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.
<!---TFS 1283165--->

**Verbesserungen für das Abrufen von Apps durch iOS-Endbenutzer**<br/>
Die folgenden Änderungen wurden an den App-Kacheln in der Unternehmensportal-App für iOS vorgenommen, damit Benutzer für alle ihre Apps an einer einzigen Stelle an verschiedene Ansichten verwiesen werden: auf der Unternehmensportal-Website. Einschränkungen seitens Apple verhindern das Auflisten branchenspezifischer und verwalteter App Store-Apps in der Unternehmensportal-App, sodass Benutzer verschiedene Ansichten besuchen müssen, um all ihre Apps zu finden.

- Die Kachel **Unternehmens-Apps** verwies zuvor auf eine Liste aller Apps auf der Registerkarte ALLE der Unternehmensportal-Website, und diese Funktion bleibt weiterhin bestehen. Der Name der Kachel wurde in **Alle Apps** geändert.
- Die Kachel **Andere Apps** verwies zuvor auf eine Ansicht innerhalb der Unternehmensportal-App, in der alle Apps aufgeführt werden, deren Anzeige Apple der Unternehmensportal-App gestattet. Der Name der Kachel wurde in **Ausgewählte Apps** geändert, und durch Tippen auf die Kachel gelangen Benutzer auf die Registerkarte AUSGEWÄHLTE der Unternehmensportal-Website.
-  Die Kachel **Kategorien** verwies zuvor auf eine Ansicht innerhalb der Unternehmensportal-App, in der Kategorien von Apps aufgeführt werden. Der Name der Kachel hat sich nicht geändert, aber sie verweist jetzt auf die Registerkarte KATEGORIEN der Unternehmensportal-Website.
Aktualisierte Screenshots finden Sie [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Aufforderung zur Installation der iOS-App „Managed Browser“, wenn IT-Experten diese Anforderung für eine App festlegen**<br/>
Wenn Sie einen Webclip so konfiguriert haben, dass er nur im verwalteten Browser geöffnet wird, und der verwaltete Browser auf einem Gerät nicht installiert ist, wird der Benutzer von der Unternehmensportal-App auf dem Gerät aufgefordert, den verwalteten Browser zu installieren, damit der Webclip installiert werden kann.
<!---TFS 1228570--->

### Windows
**Der Windows Phone 8.1-Unternehmensportal-App wurde eine Feedback-Schaltfläche hinzugefügt**<br/>
Die Windows Phone 8.1-Unternehmensportal-App ermöglicht Endbenutzern, Feedback zur App mithilfe einer neuen Schaltfläche „Feedback senden“ zu senden. Benutzer finden die Schaltfläche durch Tippen auf das Drei-Punkte-Menü unten rechts auf dem Bildschirm der Unternehmensportal-App und anschließendes Tippen auf **Feedback senden**. Das gesammelte anonymisierte Feedback hilft Microsoft, die Benutzerfreundlichkeit der Unternehmensportal-App zu verbessern.
<!---TFS 1317806--->

## Intune-Glossar</br>
Wir haben der Bibliothek einen neuen [Glossarabschnitt](https://docs.microsoft.com/intune/understand-explore/intune-glossary) hinzugefügt, in dem einige der im Intune-Produkt verwendeten Begriffe erläutert werden.



<!--HONumber=Oct16_HO2-->


