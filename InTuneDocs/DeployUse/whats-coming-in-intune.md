---
# required metadata

title: Anstehende Neuerungen | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Anstehende Neuerungen in Microsoft Intune
Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Informieren Sie sich regelmäßig über neue Updates der anstehenden Neuerungen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)..

## Nachrichtencenterintegration
Im Rahmen der Migration von Intune in das [Office 365-Verwaltungsportal](https://portal.office.com/) beginnen wir damit, das Nachrichtencenter zu nutzen, um über neue Features und andere Benachrichtigungen zu informieren.  Wenn Sie zudem die mobile Begleit-App Office 365 Admin installieren, können Sie Benachrichtigungen auf Ihrem Mobiltelefon empfangen und problemlos alle Nachrichten an Benutzer oder einen Verteilungsalias weiterleiten.<br>  
Wir beginnen mit unserer Maiversion damit, das Nachrichtencenter zu nutzen, um Sie zu benachrichtigen, wenn Updates abgeschlossen sind, und wir werden Informationen zu neuen und verbesserten Features von Intune aufnehmen.  Sehen Sie sich das Nachrichtencenter noch heute an, indem Sie sich beim [Office 365-Verwaltungsportal](https://portal.office.com/) anmelden und die Option **NACHRICHTENCENTER** im linken Navigationsbereich auswählen.
<!---TFS 1242782--->


## App-Verwaltung
- **Bedingter Zugriff für Browser.** Sie können eine Richtlinie für bedingten Zugriff für Exchange Online und SharePoint Online festlegen, sodass nur verwaltete und kompatible iOS- und Android-Geräte darauf zugreifen können. Endbenutzer, die versuchen, sich mit iOS- und Android-Geräten bei Outlook Web Access- (OWA) und SharePoint-Websites anzumelden, werden aufgefordert, ihr Gerät bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS 1175844--->

- **MAM SDK: Unterstützung für die Konfiguration der PIN-Länge.** Sie können die Länge der PIN für MAM-Apps angeben, ähnlich wie eine Geräte-PIN. Dazu müssen Endbenutzer die neuen Einschränkungen einhalten, die Sie festlegen. Sie sehen einen leicht abgewandelten PIN-Bildschirm, mit dem längere Eingaben möglich sind.
<!--- TFS 1104753--->

- **MAM-Steuerelemente, um die Synchronisierung von Outlook-Kontakten zu verhindern (iOS).** Eine neue Einstellung ist für die Verwaltung mobiler Anwendungen ohne Registrierung des Geräts verfügbar. Mit dieser Einstellung kann der Intune-Administrator verhindern, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf iOS-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, kann die App Kontakte nicht mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, kann die App Kontakte im nativen Adressbuch speichern. Wenn ein Intune-Administrator selektiv ein Gerät zurücksetzt, werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird jetzt von der Outlook-Anwendung auf iOS-Geräten unterstützt.
<!---TFS item 1276166--->

- **Skype for Business für Android.** Intune-Administratoren können jetzt Skype for Business mit MAM ohne Registrierungsrichtlinien einrichten.  Sobald die Benutzer angemeldet sind, werden die MAM-Richtlinien angewendet.
<!--- TFS item 1248444 --->

- **Skype for Business für iOS.** Intune-Administratoren können jetzt Skype for Business mit MAM ohne Registrierungsrichtlinien einrichten.  Sobald die Benutzer angemeldet sind, werden die MAM-Richtlinien angewendet.
<!--- TFS item 1248443 --->

### Xamarin-Unterstützung
Das Microsoft Intune-App-SDK unterstützt jetzt Xamarin-Apps in diesen Szenarien:

- Schreiben neuer Apps oder Ändern des Codes vorhandener branchenspezifischer Apps mit dem Intune-SDK. Sie erhalten das Plug-In auf der [GitHub-Seite für Microsoft Intune](https://github.com/msintuneappsdk).
- Hinzufügen von MAM-Unterstützung zu vorhandenen branchenspezifischen Apps mithilfe des Intune App Wrapping Tools.

Hilfe bei der Auswahl der zu verwendenden Methode erhalten Sie unter [Decide how to prepare apps for mobile application management with Microsoft Intune (Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune)](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)..
<!--- TFS 1061478 & TFS 1152340--->


## Geräteverwaltung
- **Remoteunterstützungssitzungen für Windows-PCs.** Über die TeamViewer-Integration für mit Agents verwaltete Windows-Desktop-PCs können Sie Remoteunterstützungssitzungen für mit Agents verwaltete Windows-Desktopcomputer einrichten, um Helpdesks für Endbenutzer zu unterstützen. Dies gilt für Windows 7, 8, 8.1 und Windows 10.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Zugriffssteuerung
* **Skype for Business Online unterstützt bedingten Zugriff.** Intune-Administratoren können eine Richtlinie für bedingten Zugriff für Skype for Business Online festlegen, sodass nur verwaltete und kompatible iOS- und Android-Geräte darauf zugreifen können. Endbenutzer, die versuchen, sich bei der mobilen Skype for Business-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS item 1254499--->

## Unternehmensportal
* **Banner für die Geräteidentifikation stellen zusätzliche Informationen für Endbenutzer bereit.** Benutzer können das Gerät leicht identifizieren, das sie ausgewählt haben, wenn sie die Unternehmensportalwebsite verwenden. Wenn das falsche Gerät ausgewählt wird, können sie das richtige Gerät auswählen, indem sie auf den Link „Hier tippen“ im Banner auf der Startseite tippen.
<!--- TFS 1231157--->

* **Windows-App-Pakete sind direkt über das Unternehmensportal verfügbar**: Benutzer von Windows 8-, Windows 8.1- und Windows RT-PCs können Windows-App-Pakete (mit der Erweiterung APPX) nun direkt von der Unternehmensportalwebsite installieren. Zuvor mussten sie von Intune-Administratoren bereitgestellt werden, oder die Benutzer mussten die Unternehmensportal-App auf ihren Geräten installieren, um Apps zu installieren.
<!--- TFS item 1082481 --->

* **Benutzer können ihr Gerät über das Unternehmensportal remote sperren** Eine neue Option für Remotesperren wurde der Unternehmensportalwebsite hinzugefügt, damit die Endbenutzer ihr Gerät bei Verlust oder Diebstahl über das Portal remote sperren können. Die folgende Tabelle enthält eine Übersicht über die Plattformunterstützung für Remotesperren für Intune und Intune mit Configuration Manager.
<!--- TFS item 1195661 --->

|Plattform  |Details zur Unterstützung|
|---------|---------|
|iOS | Unterstützt|
|Android | Unterstützt|
|Windows Phone 8.1 | Unterstützt|
|Windows 10 Mobile | Wird nur unterstützt, wenn für das Telefon eine Kennung festgelegt wurde|
|PC (Windows 8.0 und früher) | Nicht unterstützt|
|PC (Windows 8.1) | Nicht unterstützt|
|Windows Phone 8.0 | Nicht unterstützt|
|Windows 10 Desktop | Nicht unterstützt|

## Veraltete Dienste
* **Entfernung der Zielgruppenadressierung benutzerdefinierter Gruppen bei Benachrichtigungsregeln.** Ab Anfang Juni 2016 können Sie mit dem Assistenten zum Erstellen von Benachrichtigungsregeln keine Zielgruppenadressierung benutzerdefinierter Gruppen mit Benachrichtigungsregeln mehr einrichten.

    Um eine benutzerdefinierte Gruppe über die Microsoft Intune-Verwaltungskonsole als Ziel festzulegen, wählen Sie derzeit **Verwaltung** > **Benachrichtigungsregeln** > **Neue Regel erstellen** aus. In Schritt 2 des Assistenten zum Erstellen von Benachrichtigungsregeln müssen Sie die Gerätegruppen auswählen, für die die Regel gelten soll. Der Schritt **Gerätegruppen auswählen** wird in der Intune-Konsole nicht mehr unterstützt.

    **Gerätegruppen auswählen** wird nach der Juniversion 1606 von Intune nicht mehr unterstützt. Diese Option wird jedoch weiterhin bis August 2016 angezeigt. Nach August beginnen wir damit, über einen Zeitraum von zwei Monaten unsere Mandanten auf die neue Benutzeroberfläche umzustellen. Ab Oktober 2016 sollten alle Kunden die neue Benutzeroberfläche nutzen können. Nach der Migration zur neuen Benutzeroberfläche wird die Option zur Ausrichtung von Benachrichtigungsregeln auf eine bestimmte Gruppe nicht mehr angezeigt.
<!---   TFS 1278864--->







### Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->


