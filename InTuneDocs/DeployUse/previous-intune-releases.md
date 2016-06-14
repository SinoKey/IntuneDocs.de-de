---
# required metadata

title: Vorherige Versionen | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vorherige Versionen von Intune

## April 2016
Alle diese Features werden auch für hybride Kundenbereitstellungen (Configuration Manager integriert in Intune) unterstützt.
### App-Verwaltung
- **MAM-Benutzerkompatibilität.**
Sie können nun den [Status](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) von Anwendungsverwaltungsrichtlinien für alle Benutzer in Ihrem Azure Active Directory-Mandanten (AAD) anzeigen. Dies umfasst u. a.:
   - Geräte
   - Apps auf dem Gerät

   Statuswerte:

   **Eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, dass die App im Kontext verwendet wurde und dass sie die Richtlinie erfolgreich empfangen hat.

    **Nicht eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, die App seitdem aber nicht im Arbeitskontext verwendet wurde.


- **MAM-Steuerelemente, um die Synchronisierung von Outlook-Kontakten zu verhindern (Android).**
Eine neue Einstellung ist für die [Verwaltung mobiler Anwendungen](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) ohne Registrierung des Geräts verfügbar. Mit dieser Einstellung kann verhindert werden, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf Android-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, können Zielanwendungen Kontakte nicht mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, können Zielanwendungen Kontakte im nativen Adressbuch speichern. Wenn Sie [ein Gerät oder eine App remote zurücksetzen](wipe-managed-company-app-data-with-Microsoft-Intune.md), werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird zunächst von der Outlook-Anwendung auf Android-Geräten unterstützt.

### Geräteverwaltung
- **Telefonnummeridentifikation für unternehmenseigene Geräte.** Telefone, die als „Unternehmen“ eingestuft sind, werden jetzt mit der vollständigen Telefonnummer identifiziert, wenn Sie beispielsweise einen Inventurbericht für mobile Geräte ausführen. BYOD-Telefonnummern werden weiterhin mit *** maskiert, und nur die letzten vier Ziffern werden angezeigt.


### Aktualisierungen am Unternehmensportal
**Android-Unternehmensportal-App** Benutzer, die ihre Geräte nicht bei Intune registriert haben und die nicht das richtige Zertifikat installiert haben, können sich nicht bei der Android-Unternehmensportal-App anmelden. Ihnen wird die Meldung angezeigt, dass eine Anmeldung nicht möglich sei, da ein erforderliches Zertifikat auf dem Gerät nicht vorhanden sei. Die Meldung enthält einen Link zum Beheben dieses Problems, den Benutzer nutzen können, um eine Anleitung zum Installieren des Zertifikats zu erhalten. Die Schritte, denen die Endbenutzer folgen, um das Problem zu beheben, finden Sie unter [Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS-Unternehmensportal-App** Unterstützung für die Aktion „Zum Aktualisieren ziehen“ wurde hinzugefügt, um den Inhalt auf dem Startbildschirm zu aktualisieren, einschließlich der aufgelisteten Apps und Geräte sowie der IT-Kontaktinformationen. Mit der Aktion „Zum Aktualisieren ziehen“ werden Kompatibilitäts- oder Richtlinieninformationen nicht überprüft. Sie erreichen dies, indem Sie die Kachel für das aktuelle Gerät auswählen und auf die Schaltfläche **Synchronisieren** tippen.

**Windows 10 Mobile- und Windows Phone 8.1-Unternehmensportal-App** Wenn Endbenutzer branchenspezifische Apps installieren, sehen sie jetzt eine verbesserte Benutzeroberfläche für die App-Installation. Wenn die App-Installation sehr lange dauert, können Benutzer das Gerät manuell synchronisieren, um eine Fortsetzung des Synchronisierungsprozesses zu erzwingen. Die Anweisungen für Endbenutzer finden Sie unter [Manuelles Synchronisieren des Geräts, um Anwendungsinstallationen zu beschleunigen](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Unternehmensportal-Website** Wenn Windows 10 Mobile- und Windows Phone 8.1-Benutzer branchenspezifische Apps installieren, sehen sie jetzt die folgenden neuen Status, die ihnen weitere Details zum Status ihrer Installation zur Verfügung zu stellen:

* **Gerätesynchronisierung ausstehend**: Der Benutzer hat auf „Installieren“ getippt hat, und das Gerät versucht nun, eine Synchronisierung mit der Intune-Infrastruktur durchzuführen. Die Synchronisierung ist erforderlich, bevor die Installation abgeschlossen werden kann. Die Meldung „Gerätesynchronisierung ausstehend“ ist außerdem ein Link, auf den Benutzer tippen können, um die [Anweisungen](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) zum manuellen Synchronisieren ihres Geräts mit Intune anzuzeigen, wenn die Synchronisierung sehr lange dauert oder unterbrochen wird.
* **Wird heruntergeladen**: Die Downloadanforderung des Benutzers wird verarbeitet, und das Gerät lädt die App herunter und installiert sie.

Bevor diese Statusangaben hinzugefügt wurden, waren die Benutzer verunsichert, wenn die Installation einer App sehr lange dauerte, da nur ein Status „Wird installiert“ angezeigt wurde – und das möglicherweise für Stunden. Das Hinzufügen der neuen Statusangaben bedeutet, dass sich Benutzer nicht an den Support wenden müssen, sondern auf den Link „Gerätesynchronisierung ausstehend“ tippen und den Anweisungen folgen können, um die Fortsetzung des Synchronisierungsprozesses zu erzwingen.


## März 2016
### Neuheiten seit dem 29. März 2016
Mit Ausnahme des Updates auf die allgemeine Windows 10-Konfigurationsrichtlinie werden alle Funktionen, die am 29. März 2016 freigegeben wurden, auch für hybride Kundenbereitstellungen unterstützt (in Intune integrierter Configuration Manager). Die Hybridunterstützung für die Aktualisierung der allgemeinen Windows 10-Konfigurationsrichtlinie ist bald erhältlich. Beachten Sie, dass für einige dieser Features die neueste Version von Configuration Manager erforderlich sein kann.

### App-Verwaltung
- **MAM-Steuerelemente zum Verhindern der Synchronisierung von Outlook-Kontakten (iOS).** Eine neue Einstellung ist für die Verwaltung mobiler Anwendungen ohne Geräteregistrierung verfügbar. Mit dieser Einstellung kann verhindert werden, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf iOS-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, kann die App keine Kontakte mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, kann die App Kontakte im nativen Adressbuch speichern. Wenn Sie ein Gerät oder eine App selektiv zurücksetzen, werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird von der Outlook-Anwendung auf iOS-Geräten unterstützt. Weitere Informationen zu diesen und anderen Einstellungen finden Sie unter [Erstellen und Bereitstellen von MAM-Richtlinien](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Zugriffssteuerung
- **Skype for Business Online unterstützt bedingten Zugriff.** Sie können eine Richtlinie für bedingten Zugriff für Skype for Business Online festlegen, sodass nur verwaltete und kompatible iOS- und Android-Geräte darauf zugreifen können. Endbenutzer, die versuchen, sich bei der mobilen Skype for Business-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Geräteverwaltung
- **Intune-Unterstützung für iOS 9.3.** Am Montag, dem 21. März, verkündete Apple die Verfügbarkeit von iOS 9.3. Wir haben daran gearbeitet, Microsoft Intune mit der neuesten Version des Apple-Betriebssystems für Mobilgeräte kompatibel zu machen, und [geben hiermit bekannt, dass Intune die Verwaltung von iOS 9.3-Geräten unterstützt](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Alle vorhandenen Intune-Features, die derzeit für die Verwaltung von iOS-Geräten verfügbar sind, werden weiterhin reibungslos funktionieren, wenn Benutzer ihre Geräte auf iOS 9.3 aktualisieren. Außerdem wird iOS 9.3 auch jetzt für hybride Kundenbereitstellungen (Configuration Manager integriert in Intune) unterstützt.

- **Die allgemeine Windows 10-Konfigurationsrichtlinie enthält jetzt Einstellungen für die Verwaltung von Windows Defender auf registrierten Windows 10-PCs.** Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Unternehmensportal

- **Windows-App-Pakete stehen direkt über die Website des Unternehmensportals zur Verfügung.** Benutzer von Windows 8-, Windows 8.1- und Windows RT-PCs können Windows-App-Pakete (mit der Erweiterung APPX) nun direkt von der Website des Unternehmensportals installieren. Zuvor mussten Sie sie bereitstellen, oder die Benutzer mussten die Unternehmensportal-App auf ihren Geräten installieren, um Apps zu installieren.

- **Benutzer können ihre Geräte remote über die Website des Unternehmensportals sperren.** Eine neue Option für Remotesperren wurde der Website des Unternehmensportals hinzugefügt, damit die Benutzer ihr Gerät bei Verlust oder Diebstahl über das Portal remote sperren können. Informationen finden Sie in den [Endbenutzeranweisungen](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Die folgende Tabelle enthält eine Übersicht über die Plattformunterstützung für Remotesperren für eigenständiges Intune und Intune mit Configuration Manager.

|Plattform | Details zur Unterstützung|
|---------|----------------|
|Android |Unterstützt|
|iOS |Unterstützt|
|Windows 10 Mobile |Wird nur unterstützt, wenn für das Telefon eine Kennung festgelegt wurde|
|Windows 10 Desktop |Nicht unterstützt|
|Windows Phone 8.1 |Wird nur unterstützt, wenn für das Telefon eine Kennung festgelegt wurde|
|Windows Phone 8.0 |Nicht unterstützt|
|PC (Windows 8.0 und früher) |Nicht unterstützt|
|PC (Windows 8.1) |Nicht unterstützt|

### Neuheiten seit dem 10. März 2016

### App-Verwaltung

- **Verwenden der Verwaltungsfunktionen für mobile Geräte des Drittanbieters, dass die iOS-Verwaltungsfunktion „Öffnen in“ genutzt wird** Sie können die Verwaltungsfunktionen für mobile Geräte des Drittanbieters so verwenden, dass die iOS-Verwaltungsfunktion „Öffnen in“ genutzt wird. Sie können die Einschränkungen in den Konfigurationsprofileinstellungen festlegen und die App anhand der Informationen unter [Verwalten der Datenübertragung zwischen iOS-Apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) bereitstellen.

     Dieser Ansatz hat zwei wesentliche Vorteile:

     1. Benutzer müssen sich bei ihrem Geschäftskonto anmelden, bevor sie Zugriff auf Unternehmensdaten in Clouddiensten oder anderen Apps erhalten. Dadurch wird sichergestellt, dass die Richtlinien für die Verwaltung mobiler Geräte (Mobile App Management, MAM) gelten, wenn auf die Daten zugegriffen wird.

     2. Verwaltete E-Mail-Profile und andere über die MDM-Lösung eines Drittanbieters verwaltete Apps können Dateien und Daten mit den Apps gemeinsam nutzen, die über Intune MAM-Richtlinien verfügen.

- **Verwalten der Microsoft Outlook-App mit MAM-Richtlinien für nicht in Intune registrierte Geräte** Sie können jetzt die Microsoft Outlook-App auf Geräten verwalten, die nicht mithilfe der Intune-Richtlinie für die Verwaltung mobiler Anwendungen in Intune registriert sind. Die aktualisierte Microsoft Outlook-App mit den MAM-Funktionen ist sowohl für [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8)- als auch für [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)-Geräte verfügbar. Verwenden Sie die Anweisungen im Abschnitt [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps](https://technet.microsoft.com/library/mt627829.aspx), um eine MAM-Richtlinie zu erstellen.  


- **Konfigurationsrichtlinien für mobile Apps bieten mehr Flexibilität beim Angeben von Benutzerinformationen für iOS-Apps** Sie können Benutzereinstellungen angeben, die eine iOS-App beim Öffnen möglicherweise benötigt. Sie können beispielsweise einen Netzwerkport oder Benutzernamen angeben. Weitere Informationen finden Sie unter [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Bereitstellen von Adobe Reader für Microsoft Intune für von Intune verwaltete iOS-Geräte in Ihrem Unternehmen** Die Adobe Reader-App für iOS kann jetzt auf registrierten Geräten mit der Intune-Richtlinie für die Verwaltung mobiler Anwendungen verwaltet werden.

- **Sicherstellen, dass bereitgestellte Webclips im Managed Browser geöffnet werden** Sie können zielabhängige Webclips bereitstellen, die auf iOS- und Android-Geräten nur im Managed Browser geöffnet werden können. Angenommen, Sie stellen Links zu Unternehmensressourcen über das Unternehmensportal bereit. Wenn Benutzer zu den Links navigieren, werden diese direkt im Managed Browser geöffnet, in dem sie durch die MAM-Richtlinie geschützt werden können. Weitere Informationen finden Sie unter [Bereitstellen von Apps](deploy-apps.md).


- **Suchen, Verwalten und Verteilen von Windows Store für Unternehmen-Apps für Windows 10-Geräte in der Intune-Verwaltungskonsole** Intune bietet Unterstützung für Windows Store für Unternehmen und hilft beim Suchen, Verwalten und Verteilen von Apps auf Windows 10-Geräten, die Sie verwalten. Windows Store für Unternehmen ermöglicht Ihnen die Bereitstellung und Überwachung dieser Apps in der Intune-Verwaltungskonsole, die Sie bereits für die Verwaltung anderer Apps nutzen. Insbesondere verwaltet Windows Store für Unternehmen den Inhalt und die Lizenzierung von „online lizenzierten Apps“. Weitere Informationen finden Sie unter [Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Geräteverwaltung
- **Verteilen von PFX-Zertifikaten an iOS-Geräte** Intune-Administratoren können iOS-PFX-Zertifikate für die WLAN-, E-Mail- und VPN-Authentifizierung auf iOS-Geräten erstellen und bereitstellen. Diese Funktion ist bereits für Android- und Windows 10-Geräte verfügbar. Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).


- **Anwenden von Apps und Richtlinien auf verschiedene Gerätegruppen basierend auf der Benutzerkategorieauswahl** Intune-Administratoren können jetzt benutzerdefinierte Gerätekategorien für Benutzer definieren, aus deren während der Registrierung ausgewählt werden kann. Administratoren können beispielsweise die Benutzer bitten anzugeben, ob sie ein Gerät für „Kasse“, „Lieferfahrzeug“ oder „Lagerraum“ registrieren. Die ausgewählte Kategorie sorgt dafür, dass das Gerät Mitglied einer Intune-Gerätegruppe wird, die für die Bereitstellung anderer Apps und Richtlinien für das registrierte Gerät verwendet werden kann. Weitere Informationen finden Sie unter [Kategorisieren von Geräten mithilfe der Zuordnung von Gerätegruppen](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

**Android-Unternehmensportal-App**

* Wenn Ihre Benutzer eine App starten, die durch die mobile Anwendungsverwaltung (MAM) verwaltet wird, wird ihnen eine Meldung angezeigt, die sie darüber benachrichtigt, dass die App von ihrem Unternehmen verwaltet wird. Benutzer können jetzt auf einen Link zu weiteren Informationen tippen, um hier [weitere Informationen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) zur Bedeutung von „verwalteten Apps“ zu erhalten. Sie können auch auf die Option „Nicht mehr anzeigen“ tippen, damit die Nachricht beim Starten der App nicht mehr angezeigt wird.
* Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.


**iOS-Unternehmensportal-App**
* Wenn Ihre Benutzer eine App starten, die durch die mobile Anwendungsverwaltung (MAM) verwaltet wird, wird ihnen eine Meldung angezeigt, die sie darüber benachrichtigt, dass die App von ihrem Unternehmen verwaltet wird. Benutzer können jetzt auf einen Link zu weiteren Informationen tippen, um hier [weitere Informationen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) zur Bedeutung von „verwalteten Apps“ zu erhalten. Sie können auch auf die Option „Nicht mehr anzeigen“ tippen, damit die Nachricht beim Starten der App nicht mehr angezeigt wird.
* Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.




## Februar 2016
### Änderungen und Updates für das Unternehmensportal von Microsoft

In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

#### Android-Unternehmensportal-App
- Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.

#### iOS-Unternehmensportal-App
 - Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.


## Januar 2016

### Nutzen von Windows 10-Features
* **Bedingter Zugriff mit dem Integritätsnachweisdienst** Intune-Administratoren können jetzt den Status des Windows 10-Nachweises zur Geräteintegrität in der Intune-Verwaltungskonsole anzeigen. Mit dem Nachweis der Geräteintegrität kann der Administrator sicherstellen, dass Clientcomputer über vertrauenswürdige BIOS-, TPM- und Bootsoftwarekonfigurationen verfügen. Damit Sie den Nachweis der Geräteintegration unterstützen, müssen die Clientgeräte Windows 10 mit aktiviertem TPM 2 ausführen. Der Nachweis der Geräteintegrität zeigt die Anzahl der Geräte an, die jeweils für Folgendes aktiviert sind:
    * Antischadsoftware-Frühstart
    * BitLocker
    * Sicherer Start
    * Codeintegrität

    Weitere Informationen zum Festlegen der Geräteintegrität, zu erfassten Datenpunkten und zum Integritätsnachweisbericht finden Sie unter [Einführung in Gerätekompatibilitätsrichtlinien für Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). Die [HAS-Dienstdetails](https://msdn.microsoft.com/en-us/library/dn934876.aspx) erläutern den Dienst ausführlich.

* **Windows 10 Passport for Work-Richtlinie und Zertifikatverwaltung** Intune ermöglicht die [Integration in Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dies ist eine alternative Anmeldemethode für Windows 10, die Active Directory oder ein Azure Active Directory-Konto verwendet, um ein Kennwort, eine Smartcard oder eine virtuelle Smartcard zu ersetzen. Mit Passport können Sie anstelle eines Kennworts eine Benutzeraktion zur Anmeldung verwenden. Eine Benutzeraktion kann eine einfache PIN, eine biometrische Authentifizierung wie Windows Hello oder ein externes Gerät sein, z. B. ein Fingerabdruckleser.

* **VPN für bestimmte Apps** Sie können Apps auswählen, die automatisch eine Verbindung zum Unternehmensnetzwerk über VPN herstellen. Erstellen Sie die Liste der Apps bei der Einrichtung des VPN-Profils, wie unter „Benutzer beim Herstellen einer Verbindung zu ihren VPN-Profilen mit Microsoft Intune unterstützen“.

* **Unterstützung für vollständiges Zurücksetzen unter Windows 10** Sie können jetzt eine vollständige Remotezurücksetzung von Windows 10-Desktopgeräten starten, die über die Intune-Verwaltungskonsole bei Intune registriert wurden. Bei der vollständigen Zurücksetzung unter Windows 10 wird das Gerät auf die Werkseinstellungen zurückgesetzt.


### VPP-Update (Apple Volume Purchase Program)
Intune kann Sie jetzt beim [Verwalten von Apps unterstützen, die Sie über das Apple Volume Purchase Program (VPP) for Business erworben haben](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Dies umfasst die Synchronisierung von Lizenzinformationen zwischen Apple und Intune sowie die Nachverfolgung der Anzahl von Kopien, die Sie von jeder App bereitgestellt haben.

### Verwenden von IMEI-Nummern zum Identifizieren von unternehmenseigenen Geräten
Sie können jetzt für mobile Geräteplattformen, die über eine IMEI-Nummer verfügen, die entsprechenden [IMEI-Nummern (International Mobile Equipment Identity) importieren](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md), um die Identifizierung von unternehmenseigenen mobilen Geräten zu unterstützen. Nach der Registrierung in Intune werden Geräte mit importierten IMEI-Nummern als unternehmenseigene Geräte gekennzeichnet, die zum Anwenden von Richtlinien verwendet werden können, die sich von denen unterscheiden, die auf Geräte angewendet werden, die sich im privaten Besitz befinden.

### Weitere Apps sind jetzt mit Intune MAM-Richtlinien kompatibel.
Weitere Apps von Microsoft-Partnern sind jetzt mit Intune-Verwaltungsrichtlinien für mobile Anwendungen (MAM) kompatibel (für Geräte, die von Intune verwaltet werden):
* Box for EMM (von Box Inc) – nur iOS
* Adobe Reader (von Adobe) – nur Android
* Foxit PDF Reader (von der Foxit Corporation) – iOS und Android


### Unterstützung von Internet Explorer 9 endet im Januar
Ab Februar 2016 wird Internet Explorer 9 nicht mehr als offizieller Browser für den Zugriff auf die Microsoft Intune-Unternehmensportalwebsite, das Intune-Kontoportal und die Intune-Verwaltungskonsole unterstützt. Sie müssen zu Internet Explorer 10 oder höher migrieren.

## Dezember 2015
### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

**Android-Unternehmensportal-App**

Die folgenden Änderungen wurden vorgenommen, um neuen Google-Anforderungen zu entsprechen. Auf Geräten mit Android 6.0 und höher werden den Benutzern zwei neue Meldungen angezeigt:
* Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?
* Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?

Ausführliche Informationen über diese beiden Meldungen finden Sie in der folgenden Tabelle.



Meldungstext  |Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?  
---------|---------
Bedeutung der Meldung     |  Erlaubt, dass Telefonnummer und IMEI des Geräts des Benutzers an den Intune-Dienst gesendet und in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt werden.   </br></br>**HINWEIS: Die Unternehmensportal-App tätigt oder verwaltet keine Telefonanrufe!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden. </br></br>Zum Anzeigen der Seite **Hardware** wechseln Sie zu **Gruppen** > **Alle mobilen Geräte** > **Geräte**. Wählen Sie das Gerät des Benutzers aus, und wechseln Sie zu **Eigenschaften anzeigen** > **Hardware**.    
Ort und Zeitpunkt für die Anzeige der Meldung  | Die Meldung wird angezeigt, wenn Benutzer sich zum ersten Mal bei der Unternehmensportal-App anmelden, um mit der Registrierung ihres Geräts zu beginnen.|         
Wenn Benutzer den Zugriff zulassen, ...  |  ... werden Telefonnummer und IMEI des Geräts in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt. |         
Wenn Benutzer den Zugriff nicht zulassen, ...     | ... können sie die Unternehmensportal-App weiterhin verwenden und ihr Gerät registrieren, die Felder für Telefonnummer und IMEI des Geräts des Benutzers auf der Seite „Hardware“ in der Verwaltungskonsole sind jedoch leer.       </br></br> Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.</br></br>Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.</br></br>Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.
Weitere Informationen     |  Für Ihre Benutzer: [Anmelden beim Unternehmensportal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Für IT-Experten: Die Informationen in dieser Tabelle finden Sie auch unter [Hilfe für Ihre Benutzer zum Verständnis der Meldungen der Unternehmensportal-App](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Meldungstext  |Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?  
---------|---------
Bedeutung der Meldung     |  Erlaubt, dass Datenprotokolle auf die SD-Karte des Geräts geschrieben werden, wodurch Protokolle unter Verwendung eines USB-Kabels verschoben werden können.   </br></br>**HINWEIS: Die Unternehmensportal-App greift nicht auf Fotos, Medien und Dateien der Benutzer zu.** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.     
Ort und Zeitpunkt für die Anzeige der Meldung  | Die Meldung wird angezeigt, wenn Benutzer auf **Daten senden** tippen, um Datenprotokolle an ihren IT-Administrator zu senden.|         
Wenn Benutzer den Zugriff zulassen, ...  |  ... werden die Protokolle auf die SD-Karte kopiert. |         
Wenn Benutzer den Zugriff nicht zulassen, ...     | Sie können weiterhin Datenprotokolle senden, aber die Protokolle werden nicht auf die SD-Karte des Geräts kopiert.       </br></br> Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.</br></br>Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie das nächste Mal Protokolle senden.</br></br>Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Speicherung** wechseln, um die Berechtigung zu aktivieren.
Weitere Informationen     |  Für Ihre Benutzer: [Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Für IT-Experten: Die Informationen in dieser Tabelle finden Sie auch unter [Hilfe für Ihre Benutzer zum Verständnis der Meldungen der Unternehmensportal-App](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**iOS-Unternehmensportal-App**
* Benutzer können Diagnoseprotokolle jetzt mit Microsoft Outlook oder anderen E-Mail-Apps an den IT-Administrator senden. Zuvor konnte nur die systemeigene App verwendet werden.
* Die Unterstützung für das Geräteregistrierungsprogramm (DEP) von Apple und im Unternehmen registrierte Geräte wurde verbessert. Weitere Informationen finden Sie unter [Sie werden aufgefordert, Ihr Gerät zu identifizieren, wenn Sie versuchen, sich zu registrieren](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* In der Liste der registrierten Geräte des Benutzers wird neben dem Gerät, das der Benutzer gerade verwendet, jetzt ein grünes Häkchen angezeigt. Bevor dieses Häkchen hinzugefügt wurde, konnten Benutzer nicht erkennen, welches der registrierten Geräte sie gerade verwendeten.

**Windows-Unternehmensportal-App**

Microsoft erfasst automatisch anonyme Daten über die Leistung und die Verwendung des Unternehmensportals, um Microsoft-Produkte und -Dienste zu verbessern. Endbenutzer können die Datenerfassung über die Einstellung "Nutzungsdaten" auf ihrem Gerät deaktivieren, Administratoren haben jedoch keine Kontrolle über die Datenerfassung und können die Auswahl der Endbenutzer für diese Einstellung nicht ändern.



## November 2015
### App-Verwaltung
Intune unterstützt Verwaltungsrichtlinien für mobile Anwendungen, die dabei helfen zu verhindern, dass Verbraucher-Apps und -Dienste auf Unternehmensdaten zugreifen können. In der Vergangenheit wurden diese Richtlinien nur für mobile Apps auf Geräten erzwungen, die auch für die Verwaltung mobiler Geräte in Intune registriert wurden.

Mit dem Update dieses Monats erweitert Intune seine MAM-Funktionen auf neue Geräteklassen. Zusätzlich zu in Intune registrierten Geräten können Sie MAM-Richtlinien jetzt auf Folgendem erzwingen:
* Auf Geräten, die von einer anderen Lösung zur Geräteverwaltung verwaltet werden
* Auf Geräten, die in keinem Geräteverwaltungssystem registriert sind, d. h. in der Regel BYO-Geräte (privater Besitz)

Weitere Informationen zu diesen neuen MAM-Funktionen finden in den folgenden Blogbeiträgen:
* [Erhöhen der verwalteten mobilen Produktivität](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Ankündigung neuer Microsoft Enterprise Mobility-Funktionen](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Darüber hinaus folgen hier einige Highlights und zusätzliche Informationen zu MAM-Funktionen von Intunes:
* Unternehmensdaten werden von den Verbraucherdaten in Apps isoliert, die für Intunes aktiviert sind, einschließlich Office Mobile-Apps, Drittanbieter-Apps, die das Intune-SDK eingeführt haben oder Line-of-Business-Apps, die von Intune umschlossen sind.
* Unternehmensdaten können von Unternehmens-Apps gemeinsam genutzt werden (**Ausschneiden, Kopieren und Einfügen**), während die Freigabe von Unternehmensdaten für private Apps verhindert wird. Weitere Informationen finden Sie unter [Wie App-Daten mit MAM-Richtlinien geschützt werden](https://technet.microsoft.com/library/mt627825.aspx). Dieses Beispielszenario, [Verwenden der Microsoft Word-App für berufliche und private Zwecke](https://technet.microsoft.com/library/mt627827.aspx), veranschaulicht, wie die Freigabe von Unternehmensdaten für private Apps verhindert wird.
* Richtlinien zur Verhinderung des Verlusts von Schlüsseldaten wie anwendungsabhängige PIN, „Speichern unter“-Steuerelemente und die Freigabe verwalteter Daten zwischen Apps. Eine Liste aller Richtlinien finden Sie unter [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Word, Excel, PowerPoint, Outlook, OneNote und OneDrive for Business verfügen jeweils über diese neuen Funktionen und können mit und ohne Geräteregistrierung verwaltet werden. Die Funktionen zum Schutz vor Datenverlust sind nativ in den Office-Apps im Apple Store oder Google Play Store integriert und erfordern kein App-Wrapping oder -Sideloading.
* Informationen zu den ersten Schritten finden Sie unter [Erste Schritte mit Verwaltungsrichtlinien für mobile Apps im Azure-Portal](https://technet.microsoft.com/library/mt627830.aspx). Weitere Informationen zum Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Apps finden Sie unter [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Wenn sich Endbenutzer bei der App mit ihren Unternehmensanmeldeinformationen authentifizieren, werden die Funktionen zum Schutz vor Datenverlust automatisch eingerichtet. Der Abschnitt [Endbenutzer-Erfahrung mit Apps, die den Microsoft Intune-Verwaltungsrichtlinien für mobile Apps unterliegen](https://technet.microsoft.com/library/mt627827.aspx) enthält einige Beispielszenarien für den Zugriff auf OneDrive auf iOS- und Android-Geräten.
* Sie funktionieren für iOS- und Android-Geräte.

Die Liste der [Microsoft-Apps zur Verwendung mit den Microsoft Intune-Verwaltungsrichtlinien für mobile Anwendungen](https://technet.microsoft.com/library/dn708489.aspx) wurde aktualisiert, um die neuesten Apps anzuzeigen.

### Geräteverwaltung
 **Geräteverwaltung unter Mac OS X** Mit Intune können Sie jetzt Mac OS X-Geräte registrieren und verwalten. Mit den Mac OS X-Geräten haben Sie folgende Möglichkeiten:
* Geräte für die Verwaltung mit Intune registrieren. Weitere Informationen finden Sie unter [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Steuern Sie Geräteeinstellungen mit einer allgemeinen Konfigurationsrichtlinie. Weitere Informationen finden Sie unter [Einstellungen für Mac OS X-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Stellen Sie Mac OS X-Einstellungen bereit, die Sie mit Apple Configurator erstellt haben. Weitere Informationen finden Sie unter [Benutzerdefinierte Mac OS X-Richtlinieneinstellungen in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Sammeln Sie Hardware- und Softwareinventurdaten von Mac OS X-Clients. Weitere Informationen finden Sie unter [Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Führen Sie neue Berichte aus, die Details zu den Mac OS X-Geräten anzeigen, die Sie verwalten. Weitere Informationen finden Sie unter [Einblicke in Microsoft Intune-Vorgänge durch Berichte](https://technet.microsoft.com/library/dn646977.aspx).

**Neue Einstellungen für den Edge-Browser für Windows 10-Geräte** Es wurden neue Einstellungen zur allgemeinen Konfigurationsrichtlinie von Windows 10 hinzugefügt, mit denen Sie die Einstellungen und Features des Microsoft Edge-Browsers verwalten können. Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-Mail-Profile** Eine neue Richtlinie für E-Mail-Profile wurde für Windows 10-Desktopgeräte sowie für mobile Windows 10-Geräte hinzugefügt. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](https://technet.microsoft.com/library/dn646984.aspx).

**Neue Einstellungen für die Kompatibilitätsrichtlinie** Die folgenden neuen Einstellungen für die Sicherheits- und Systemrichtlinie wurden zur Liste der Kompatibilitätsrichtlinien hinzugefügt:
* Um sicherzustellen, dass auf Geräten mit Windows 8.1 oder höher, die Zugriff auf Ihre Unternehmensressourcen haben, die neuesten Updates installiert sind, verwenden Sie die Einstellung **Automatische Updates erforderlich**. Sie können auch die Art der Updates angeben, die automatisch installiert werden – entweder alle als wichtig gekennzeichneten Updates oder alle als wichtig oder empfohlen gekennzeichneten Updates. Eine vollständige Liste der Einstellungen für die Kompatibilitätsrichtlinie finden Sie unter [Verwalten von Gerätekompatibilitätsrichtlinien für Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Die Kombination der neuen Einstellung **Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt** mit der vorhandenen Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** ermöglicht es Ihnen, eine Kompatibilitätseinstellung zu erstellen, bei der der Endbenutzer ein Kennwort eingeben muss, um ein Gerät zu verwenden, das für einen bestimmten Zeitraum inaktiv war.

**Neue Richtlinienoptionen für den bedingten Zugriff** Sie können Richtlinien für bedingten Zugriff auf **alle Benutzer** in neuen oder vorhandenen Richtlinien für den bedingten Zugriff anwenden. Alle für Intune und Office 365 lizenzierten Benutzer müssen ihre Geräte registrieren. Wenn Intune die Geräteplattform nicht unterstützt, wird der Zugriff für Clientanwendungen mithilfe der auf der [Active Directory-Authentifizierung basierenden Anmeldung (moderne Authentifizierung)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) blockiert.

Sie können auch angeben, dass die Richtlinie für den bedingten Zugriff für **alle Plattformen** gelten.  Jede Clientanwendung, die die auf der [Active Directory-Authentifizierung basierende Anmeldung (moderne Authentifizierung)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) verwendet, unterliegt der Richtlinie für den bedingten Zugriff, und wenn die Plattform von Intune nicht unterstützt wird, wird sie blockiert.

### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

* **Android**: Es wurde eine Begrüßungsseite zur Android-Unternehmensportal-App hinzugefügt, damit die Benutzer den Zweck der Unternehmensportal-App besser verstehen. Dieser Bildschirm soll Downloads der App durch Benutzer verringern, deren Unternehmen keine Intune-Abonnenten sind.

* **iOS**: Intune unterstützt jetzt die Registrierung von Mac OS X-Geräten über die [Unternehmensportal-Website](https://portal.manage.microsoft.com). Anweisungen finden Sie unter [Registrieren Ihres Mac OS X-Geräts in Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Unternehmensportal-Website**: Benutzer, die ihre Geräte bei Intune registriert haben, können jetzt ihre Kennung auf der Unternehmensportal-Website mithilfe der Option **Kennung zurücksetzen** zurücksetzen. Früher konnten nur IT-Administratoren Benutzerkennungen zurücksetzen. Die Option „Kennung zurücksetzen“ wird auf Geräten mit Windows 8.1 und Windows RT nicht unterstützt, und die Option wird nur angezeigt, wenn Geräte in der Verwaltung mobiler Geräte (MDM) oder MDM mit Exchange ActiveSync angemeldet sind. Anweisungen für Benutzer finden Sie unter [Zurücksetzen der Kennung](https://technet.microsoft.com/library/mt590895.aspx).

### Änderungen an der Lizenzierung globaler Administratoren
Im Oktober haben wir bekannt gegeben, dass globale Administratoren (auch als Mandantenadministratoren bezeichnet) weiterhin alltägliche Verwaltungsaufgaben ausführen können, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen. Wenn globale Administratoren den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie wie alle anderen Benutzer eine Intune- oder EMS-Lizenz. Nachfolgenden finden Sie einige zusätzliche Details.
* Mit dem Intune-Unternehmensportal haben Endbenutzer folgende Möglichkeiten:
    * Registrieren ihres Geräts
    * Anzeigen des Gerätestatus
    * Herunterladen von Software, die ein globaler Administrator für das Unternehmen bereitgestellt hat
    * Verwenden von Links zur Kontaktaufnahme mit der IT-Abteilung, die vom globalen Administrator veröffentlicht wurden

    [Erfahren Sie mehr über das Unternehmensportal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) und über [Methoden zum Anpassen des Unternehmensportals](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Die Person, die im Namen des Unternehmens für den Erwerb von Intune oder EMS unterzeichnet, wird automatisch zum ersten globalen Administrator des Mandanten. Im Herbst hat Intune damit begonnen, dem allerersten globalen Administrator im Rahmen des Wechsels zum [Office 365-Portal](http://portal.office.com/) und der Deaktivierung des [Intune-Kontoportals](http://account.manage.microsoft.com/) automatisch eine Intune- oder EMS-Lizenz zuzuweisen. Alle zusätzlich hinzugefügten globalen Administratoren können die tägliche Verwaltung weiterhin ohne separate Intune- oder EMS-Lizenz durchführen. Wenn sie als Endbenutzer agieren und ihr eigenes (oder unternehmenseigenes) Gerät registrieren oder Software aus dem Unternehmensportal herunterladen, ist wie bei allen anderen Benutzern eine Lizenz erforderlich.
* Die Änderung wird stufenweise ab Januar 2016 eingeführt.
* Diese Änderung sollte sich für Microsoft-Partners nicht auf die Möglichkeit auswirken, den Dienst im Auftrag des Kunden zu verwalten. Für Endbenutzeraufgaben muss ein Benutzer eine Intune- oder EMS-Lizenz besitzen, um ein Gerät zu registrieren und auf Software aus dem Unternehmensportal zuzugreifen bzw. diese herunterzuladen.

Wenn Sie Fragen zu dieser Änderung haben, können Sie sich an das Intune-Supportteam wenden:
* [Microsoft Intune-Supportkanäle](https://technet.microsoft.com/library/jj839713.aspx)
* [Communityunterstützung](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Allgemeines Feedback zu Microsoft Intune, z. B. zur Archivierung von DCRs (Design Change Requests) oder bei Fehlern, finden Sie unter [Intune User Voice](https://microsoftintune.uservoice.com/).


### Neuerungen in der Intune-Dokumentation – November 2015
**Neuer Inhalt**
* [Einstellungen für die Mac OS X-Konfigurationsrichtlinie in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): Steuern von Geräteeinstellungen und Features für Mac OS X-Geräte.
* [Benutzerdefinierte Mac OS X-Richtlinieneinstellungen in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Bereitstellen von Mac OS X-Geräteeinstellungen, die mit dem Apple Configurator-Tool erstellt wurden.
* [Konfigurieren von App-Richtlinien zum Schutz vor Datenverlust mit Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Enthält Informationen zu den Szenarien, die von Richtlinien für die Verwaltung mobiler Apps unterstützt werden, und Informationen zur Funktionsweise der Richtlinie zum Schutz der Daten.
* [Erste Schritte mit Verwaltungsrichtlinien für mobile Apps im Azure-Portal](https://technet.microsoft.com/library/mt627830.aspx): Anforderungen für die ersten Schritte mit dem Azure-Vorschauportal für Verwaltungsrichtlinien für mobile Apps.
* [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Enthält eine schrittweise Anleitung zum Erstellen von Verwaltungsrichtlinien für mobile Apps im Azure-Vorschauportal.
* [Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Informationen zum Überwachen Ihrer Verwaltungsrichtlinien für mobile Apps mithilfe des Azure-Vorschauportals.
* [ Microsoft Intune-Richtlinien für die Verwaltung von mobilen Apps und iOS-Feature „Öffnen in“](https://technet.microsoft.com/library/mt627821.aspx): Informationen zur Funktionsweise der Verwaltungsrichtlinien für mobile Apps mit dem iOS-Feature „Öffnen in“.
* [Endbenutzer-Erfahrung mit Apps, die den Microsoft Intune-Verwaltungsrichtlinien für mobile Apps unterliegen](https://technet.microsoft.com/library/mt627827.aspx): Informationen zum Endbenutzererlebnis bei der Verwendung von Apps, die der Verwaltungsrichtlinie für mobile Apps zugeordnet sind.
* [Löschen verwalteter Unternehmensdaten aus Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): Informationen zum Entfernen von Unternehmensdaten aus Apps.

**Aktualisierter Inhalt**
* [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Es wurden neue Einstellungen für den Edge-Browser hinzugefügt.
* [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Es wurden Informationen zum Registrieren von Mac OS X-Geräten hinzugefügt.
* [Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Es wurden Informationen zum Inventar hinzugefügt, das von Mac OS X-Geräte gesammelt wurde. Zudem wurde das Thema mit den neuesten Informationen für alle Plattformen aktualisiert.
* [Einblicke in Microsoft Intune-Vorgänge durch Berichte](https://technet.microsoft.com/library/dn646977.aspx): Es wurden Informationen zu den beiden neuen Berichten hinzugefügt, mit denen Informationen zu Ihren verwalteten Mac OS X-Geräten angezeigt werden können.
* [Verwalten von Gerätekonformitätsrichtlinien für Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Es wurden Informationen zu den neuen Konformitätsrichtlinien für die Anforderung automatischer Updates und Kennwörter hinzugefügt, wenn ein Gerät aus dem Leerlauf zurückkehrt.
* [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Es wurden Informationen zu der Möglichkeit zum Anwenden der Richtlinie für den bedingten Zugriff für alle Plattformen und alle Benutzer hinzugefügt.
* [Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Es wurden Informationen zu der Möglichkeit zum Anwenden der Richtlinie für den bedingten Zugriff für alle Plattformen und alle Benutzer hinzugefügt.

## Oktober 2015

### Aktualisierungen beim bedingten Zugriff für Exchange lokal
**Sie können jetzt den Zugriff auf Exchange ActiveSync-E-Mail für konforme Geräte zulassen, die bei Intune registriert sind, wenn die globale Exchange-Regel auf „Blockieren“ oder „Isolieren“ festgelegt ist.** Bisher mussten Sie, um den E-Mail-Zugriff auf registrierten und konformen Geräten zuzulassen, die globale Exchange-Standardregel auf **Zulassen** festlegen.

Mit diesem Dienstupdate ist diese Einstellung keine Voraussetzung mehr für den bedingten Zugriff. Wenn Ihre Exchange-Umgebung erfordert, dass Ihre globale Standardregel auf **Blockieren/Isolieren** festgelegt ist, aktivieren Sie einfach das Kontrollkästchen **Standardregel außer Kraft setzen** auf der Seite für den bedingten Zugriff in Exchange lokal. Das Thema [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) enthält mehr Detailinformationen zu den Regeln und den resultierenden Endbenutzerbenachrichtigungen.

**Neue One-Click-Quarantäneumgebung**. Wir haben die E-Mail-Quarantäneumgebung so vereinfacht, dass die Registrierung mit nur einem Klick möglich ist. Mit diesem Dienstupdate können Endbenutzer auf einen einzelnen Link in der Quarantäne-E-Mail klicken, um den Registrierungsprozess in der Unternehmensportal-App abzuschließen.
### Updates für die Verwaltung von mobilen Geräten und Apps
**Android**: Alle Intune-Verwaltungsfeatures unterstützen jetzt Android 6.0 (Marshmallow), wie in diesem Blogbeitrag beschrieben: [Microsoft Intune bietet Day-0-Unterstützung für Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS**: Sie können keine neuen App-Bereitstellungen mehr für iOS-Geräte erstellen, auf denen eine ältere Version als iOS 7.1 ausgeführt wird. Alle vorhandenen App-Bereitstellungen auf Geräten, auf denen eine ältere Version als iOS 7.1 ausgeführt wird, funktionieren weiterhin und werden auch weiterhin von Intune verwaltet.

**Windows 10**: Intune unterstützt jetzt die Bereitstellung von universellen Windows 10-Apps mithilfe des Softwareinstallationsprogramm-Typs **App-Paket für Windows**. Ausführlichere Informationen und die Anforderungen finden Sie unter [Erste Schritte bei der Bereitstellung von Apps in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen: **iOS** Der Unternehmensportal-App wurden neue Schaltflächen hinzugefügt, um Benutzer das Senden von Diagnoseprotokollen an ihre IT-Administratoren zu erleichtern:

|Schaltflächenname|Position in der Oberfläche|
|------------|---------------|
|Bericht|Fehlerwarnmeldungen|
|Diagnosebericht senden|Bildschirm „Info“ in der Unternehmensportal-App|


>[!div class="step-by-step"]

>[&larr; **Neuheiten in Intune**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO3-->


