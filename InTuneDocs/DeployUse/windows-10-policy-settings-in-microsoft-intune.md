---
# required metadata

title: Einstellungen für Windows 10-Richtlinien in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einstellungen für Windows 10-Richtlinien in Microsoft Intune

Verwenden Sie die in diesem Thema aufgeführten Richtlinieneinstellungen, um Einstellungen für registrierte Windows 10 Desktop- und Windows 10 Mobile-Geräte zu konfigurieren.

## Allgemeine Konfigurationsrichtlinieneinstellungen

Verwenden Sie die **allgemeine Microsoft-Konfigurationsrichtlinie** für Windows 10, um allgemeine Einstellungen für registrierte Windows 10 Desktop- und Windows 10 Mobile-Geräte zu konfigurieren:


### Kennwort

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Anfordern eines Kennworts zum Entsperren von Geräten**|Auf unterstützten Geräten ein Kennwort erfordern.|Ja|Ja|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|Ja|Ja|
|**Erforderlicher Kennworttyp** - **Minimale Anzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen.|Ja|Ja|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Gerätekennwort enthalten muss.|Nein|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Setzt das Gerät zurück, wenn diese Anzahl von Anmeldeversuchen fehlschlägt.|Ja|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Gibt den Zeitraum an, für den sich das Gerät im Leerlauf befinden muss, bevor der Bildschirm gesperrt wird.|Ja|Ja|
|**Kennwortablauf (Tage)**|Gibt die Zeitspanne an, nach der das Kennwort für das Gerät geändert werden muss.|Ja|Ja|
|**Kennwortverlauf speichern**|Gibt an, ob Sie verhindern möchten, dass der Endbenutzer zuvor verwendete Kennwörter erstellt.|Ja|Ja|
|**Kennwortverlauf speichern** - **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|Ja|Ja|
|**Bildkennwort und PIN zulassen**|Ermöglicht Ihnen die Verwendung einfacher Gesten auf einem Bild oder einer einfachen PIN zur Anmeldung.|Ja|Nein|
|**Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt**|Ist diese Einstellung aktiviert, muss der Benutzer ein Kennwort zum Entsperren des Geräts nach dem Leerlauf eingeben.|Nein|Ja|

### Verschlüsselung

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Verschlüsselung auf mobilem Gerät anfordern**|Ermöglicht die Verschlüsselung auf Zielgeräten.|Nein|Ja|

### System

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Bildschirmaufnahme zulassen**|Ermöglicht dem Benutzer, den Bildschirm des Geräts als Bild zu erfassen.|Nein|Ja|
|**Manuelles Aufheben der Registrierung zulassen**|Ermöglicht dem Benutzer das manuelle Löschen des Unternehmensbereichskontos vom Gerät.|Ja|Ja|
|**Manuelle Installation des Stammzertifikats zulassen**|Gibt an, ob der Benutzer Stammzertifikate manuell installieren kann.|Nein|Ja|
|**Senden von Diagnose- und Verwendungsdaten an Microsoft zulassen**|Bestimmt den Umfang an Diagnose- und Verwendungsdaten, die von Geräten an Microsoft gesendet werden.<br>**Nein**: Keine Daten werden an Microsoft gesendet.<br>**Standard**: Das Gerät sendet nur begrenzte Informationen an Microsoft.<br>**Erweitert**: Das Gerät sendet erweiterte Diagnosedaten an Microsoft.<br>**Vollständig (empfohlen)**: Das Gerät sendet die gleichen Daten wie mit **Erweitert** sowie zusätzliche Daten über den Gerätezustand.|Ja|Ja|


### Konto und Synchronisierung

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft-Konto erlauben**|Ermöglicht dem Benutzer, das Gerät einem Microsoft-Konto zuzuordnen.|Ja|Ja|
|**Manuelles Hinzufügen von Nicht-Microsoft-Konten zulassen**|Ermöglicht dem Benutzer, dem Gerät E-Mail-Konten hinzuzufügen, die nicht mit einem Microsoft-Konto verknüpft sind.|Ja|Ja|
|**Synchronisierung von Einstellungen für Microsoft-Konten zulassen**|Ermöglicht das Synchronisieren der mit einem Microsoft-Konto verknüpften Geräte- und App-Einstellungen zwischen Geräten.|Ja|Ja|

### E-Mail-Einstellungen

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft-Konto in Windows Mail-Anwendung optional machen**|Konfigurieren Sie diese Einstellung, um die Anforderung für ein Microsoft-Konto in Windows Mail zu entfernen.|Ja|Nein|



### Microsoft Edge

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Webbrowser zulassen**|Ermöglichen Sie die Verwendung des Edge-Webbrowsers auf dem Gerät.|Nein|Ja|
|**Suchvorschläge auf der Adressleiste zulassen**|Ermöglicht dem Suchmodul, Websites während der Eingabe von Suchausdrücken vorzuschlagen.|Ja|Ja|
|**Senden von Intranetdatenverkehr an Internet Explorer zulassen**|Ermöglicht Benutzern, Intranetwebsites in Internet Explorer zu öffnen.|Ja|Nein|
|**Do Not Track (nicht verfolgen) zulassen**|Konfiguriert den Edge-Browser zum Senden von DNT-Headern (Do Not Track, nicht nachverfolgen) an Websites, die Benutzer besuchen.|Ja|Ja|
|**SmartScreen aktivieren**|Aktiviert die SmartScreen-Browsereinstellung auf Geräten.|Ja|Ja|
|**Active Scripting zulassen**|Ermöglicht die Ausführung von Skripts wie JavaScript im Edge-Browser.|Ja|Ja|
|**Popups zulassen**|Aktiviert oder deaktiviert den Popupblocker des Browsers.|Ja|Nein|
|**Cookies zulassen**|Aktiviert oder deaktiviert Cookies.|Ja|Ja|
|**AutoAusfüllen zulassen**|Ermöglicht Benutzern, die Einstellungen für AutoVervollständigen im Browser zu ändern.|Ja|Nein|
|**Kennwort-Manager zulassen**|Aktivieren oder deaktivieren Sie den Edge-Kennwort-Manager.|Ja|Ja|
|**Ort der Standortliste für Enterprise-Modus**|Gibt an, wo Sie die Liste der Websites finden, die im Unternehmensmodus geöffnet werden. Benutzer können diese Liste nicht bearbeiten.|Ja|Nein|

### Apps

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**App Store zulassen**|Ermöglicht dem Benutzer den Zugriff auf den App Store auf dem Gerät.|Nein|Ja|



### Mobilfunk

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Datenroaming zulassen**|Ermöglicht beim Zugriff auf Daten das Roaming zwischen Netzwerken.|Ja|Ja|
|**VPN über Mobilfunk zulassen**|Steuert, ob das Gerät auf VPN-Verbindungen zugreifen kann, wenn es mit einem Mobilfunknetz verbunden ist.|Ja|Ja|
|**VPN-Roaming über Mobilfunk zulassen**|Steuert, ob das Gerät beim Roaming in einem Mobilfunknetz auf VPN-Verbindungen zugreifen kann.|Ja|Ja|

### Hardware

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Kamera zulassen**|Gibt an, ob die Kamera des Geräts verwendet werden darf.|Ja|Ja|
|**Wechselspeichermedien zulassen**|Gibt an, ob externe Speichergeräte wie SD-Karten mit dem Gerät verwendet werden können.|Ja|Ja|
|**WLAN zulassen**|Ermöglicht die Verwendung der WLAN-Funktion der Geräte.|Nein|Ja|
|**Internetfreigabe zulassen**|Ermöglicht die gemeinsame Nutzung der Internetverbindung auf dem Gerät.|Ja|Ja|
|**Manuelle WLAN-Konfiguration zulassen**|Steuert, ob die Benutzer eigene WLAN-Verbindungen konfigurieren dürfen oder ob nur über WLAN-Profile konfigurierte Verbindungen verwendet werden dürfen.|Nein|Ja|
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Ermöglicht automatische Verbindungen des Geräts mit unverschlüsselten WLAN-Hotspots und das automatische Akzeptieren der Geschäftsbedingungen für die Verbindung.|Ja|Ja|
|**Geolocation zulassen**|Gibt an, ob das Gerät Ortungsdienstinformationen verwenden kann.|Ja|Ja|
|**NFC zulassen**|Ermöglicht die Verwendung von NFC-Funktionen (Near Field Communications) auf dem Gerät.|Ja|Ja|
|**Bluetooth zulassen**|Ermöglicht die Verwendung von Bluetooth-Funktionen auf dem Gerät.|Ja|Ja|
|**Sichtbaren Modus für Bluetooth zulassen**|Ermöglicht die Erkennung dieses Geräts durch andere Bluetooth-Geräte.|Ja|Ja|
|**Bluetooth-Werbung zulassen**|Ermöglicht Geräten dem Empfang von Werbung über Bluetooth.|Ja|Ja|
|**Verbindungsfähigen Bluetoothmodus zulassen** **Wichtig:** |Diese Einstellung wird von Windows 10 nicht mehr unterstützt und künftig entfernt.|Ja|Ja|
|**Handyzurücksetzung zulassen**|Steuert, ob Benutzer ihre Geräte auf Werkseinstellungen zurücksetzen dürfen.|Ja|Ja|
|**USB-Verbindung zulassen**|Steuert, ob die Geräte über eine USB-Verbindung auf externe Speichergeräte zugreifen können.|Ja|Ja|
|**Diebstahlschutzmodus zulassen**|Konfigurieren Sie, ob der Windows-Diebstahlschutzmodus aktiviert ist.|Ja|Ja|

### Features

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Kopieren und Einfügen zulassen**|Aktivieren oder deaktivieren Sie die Verwendung von Kopieren und Einfügen auf dem Gerät.|Nein|Ja|
|**Sprachaufzeichnung zulassen**|Aktivieren oder deaktivieren Sie Funktionen für Sprachaufzeichnungen auf dem Gerät.|Nein|Ja|
|**Cortana zulassen**|Aktivieren oder deaktivieren Sie den Cortana-Sprach-Assistenten.|Ja|Ja|
|**Info-Center-Benachrichtigungen zulassen**|Aktivieren oder deaktivieren Sie Wartungscenterbenachrichtigungen auf dem Gerätesperrbildschirm.|Nein|Ja|

### Defender

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Echtzeitüberwachung zulassen**|Ermöglicht die Echtzeitüberwachung auf Schadsoftware, Spyware und andere unerwünschte Software.|Ja|Nein|
|**Verhaltensüberwachung zulassen**|Ermöglicht Defender, Geräte auf bestimmte bekannte Muster verdächtiger Aktivitäten zu überprüfen.|Ja|Nein
|**Netzwerkinspektionssystem aktivieren**|Das Netzwerkinspektionssystem (NIS) trägt zum Schutz von Geräten vor netzwerkbasierten Sicherheitslücken bei, indem die Signaturen bekannter Sicherheitsrisiken aus dem Endpoint Protection-Center von Microsoft verwendet werden, um schädlichen Datenverkehr zu erkennen und zu blockieren.|Ja|Nein
|**Alle Downloads werden überprüft**|Steuert, ob Defender alle aus dem Internet heruntergeladenen Dateien überprüft.|Ja|Nein
|**Skriptüberprüfung zulassen**|Ermöglicht Defender die Überprüfung von Skripts, die in Internet Explorer verwendet werden.|Ja|Nein
|**Datei- und Programmaktivität überwachen**|Aktivieren Sie diese Einstellung, um Defender die Überwachung der Datei- und Programmaktivität auf Geräten zu ermöglichen.|Ja|Nein
|**Tage für Nachverfolgung behandelter Schadsoftware**|Ermöglicht Defender die fortgesetzte Nachverfolgung behandelter Schadsoftware für die angegebene Anzahl von Tagen, damit Sie zuvor betroffene Geräte manuell überprüfen können. Wenn Sie die Anzahl von Tagen auf **0** festlegen, bleibt Schadsoftware im Quarantäneordner und wird nicht automatisch entfernt. |Ja|Nein
|**Zugriff auf die Clientbenutzeroberfläche zulassen**|Steuert, ob die Benutzeroberfläche von Windows Defender für Endbenutzer ausgeblendet ist.<br>Wenn diese Einstellung geändert wird, wird die Änderung wirksam, wenn der Endbenutzer-PC das nächste Mal neu gestartet wird.|Ja|Nein
|**Eine tägliche Schnellüberprüfung planen**|Ermöglicht Ihnen die Planung einer Schnellüberprüfung, die täglich zum ausgewählten Zeitpunkt erfolgt.|Ja|Nein
|**Systemüberprüfung planen**|Sie können eine vollständige Überprüfung oder eine Schnellüberprüfung des Systems planen, die regelmäßig am ausgewählten Tag und zur ausgewählten Zeit auftritt.|Ja|Nein
|**Prozessornutzung während der Überprüfung begrenzen auf**|Ermöglicht die Begrenzung des Umfangs an CPU, der bei Überprüfungen genutzt werden darf (von **1** bis **100**)|Ja|Nein
|**Archivdateien überprüfen**|Ermöglicht Defender die Überprüfung von Archivdateien wie ZIP- oder CAB-Dateien.|Ja|Nein
|**Scannen von E-Mail-Nachrichten**|Ermöglicht Defender das Überprüfen von E-Mail-Nachrichten beim Eingang auf dem Gerät.|Ja|Nein
|**Wechseldatenträger überprüfen**|Ermöglicht Defender das Überprüfen von Wechseldatenträgern wie USB-Sticks.|Ja|Nein
|**Zugeordnete Netzwerklaufwerke überprüfen**|Ermöglicht Defender das Überprüfen von Dateien auf zugeordneten Netzwerklaufwerken.<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|Ja|Nein
|**Dateien überprüfen, die in freigegebenen Netzwerkordnern geöffnet wurden**|Ermöglicht Defender das Überprüfen von Dateien auf freigegebenen Netzlaufwerken (z. B. solche, auf die über einen UNC-Pfad zugegriffen wird).<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|Ja|Nein
|**Intervall zum Aktualisieren von Signaturen**|Geben Sie das Intervall an, in dem Defender auf neue Signaturdateien prüfen soll.|Ja|Nein
|**Cloudschutz zulassen**|Lassen Sie zu, oder verhindern Sie, dass Microsoft Active Protection Service Informationen über Schadsoftwareaktivitäten von den von Ihnen verwalteten Geräten erhält. Diese Informationen werden verwendet, um den Dienst in der Zukunft zu verbessern.|Ja|Nein
|**Beim Senden von Beispielen beim Benutzer nachfragen**|Steuert, ob die Dateien automatisch an Microsoft gesendet werden, die möglicherweise von Microsoft genauer analysiert werden müssen, um festzustellen, ob sie schädlich sind.|Ja|Nein
|**Von der Überprüfung oder dem Echtzeitschutz auszuschließende Dateien und Ordner**|Fügen Sie Dateien und Ordner wie **C:\Pfad** oder **%ProgramFiles%\Pfad\Dateiname.exe** der Ausschlussliste hinzu. Diese Dateien und Ordner werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|Ja|Nein
|**Dateierweiterungen, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Dateierweiterungen wie **JPG** oder **TXT** der Ausschlussliste hinzu. Dateien mit diesen Erweiterungen werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|Ja|Nein
|**Prozesse, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Prozesse des Typs **.exe**, **.com** oder **.scr** der Ausschlussliste hinzu. Diese Prozesse werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|Ja|Nein| 


### Updateeinstellungen

|Name der Einstellung|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Automatische Updates zulassen**|Aktivieren Sie diese Einstellung, um automatische Updates zuzulassen. Konfigurieren Sie dann eine der folgenden Einstellungen, um das Updateverhalten zu steuern:<br /><br />**Download benachrichtigen**<br /><br />**Automatische Installation während der Wartung**<br /><br />**Automatische Installation und Neustart während der Wartung**<br /><br />**Zur festgelegten Zeit automatisch installieren und neu starten** **Hinweis:** Wenn diese Option ausgewählt ist, können Sie auch die folgenden Einstellungen konfigurieren: **Benachrichtigung für Endbenutzer unterdrücken** und **Installationstag für geplante Updates definieren**.|Ja|Nein|

## Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Microsoft Intune-Konfigurationsrichtlinie** für Windows 10 und Windows 10 Mobile Einstellungen für OMA-URI (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Windows 10- und Windows 10 Mobile-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Windows 10-Einstellungen bereitzustellen, die nicht mit einer allgemeinen Intune-Konfigurationsrichtlinie konfigurierbar sind. Weitere Informationen zu den Einstellungen, die Sie mit diesen Richtlinien konfigurieren können, finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

Eine Liste der OMA-URI-Einstellungen, die Sie auf registrierten Windows 10-Geräten konfigurieren können, finden Sie unter „Benutzerdefinierte URI-Einstellungen für Windows 10-Geräte“ weiter unten in diesem Thema.

### Allgemeine Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für die Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
    |**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### OMA-URI-Einstellungen

|Name der Einstellung|Details|
    |--------|--------------------|
    |**Name der Einstellung**|Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
    |**Beschreibung der Einstellung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**Datentyp**|Wählen Sie den Datumstyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus:<br /><br />-   **Zeichenfolge**<br />-   **Zeichenfolge (XML)**<br />-   **Datum und Uhrzeit**<br />-   **Ganze Zahl**<br />-   **Gleitkomma**<br />-   **Boolesch**|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|


## Benutzerdefinierte URI-Einstellungen für Windows 10-Geräte
In diesem Thema werden die Einstellungen aufgeführt, die Sie für Windows 10- und Windows 10 Mobile-Geräte in einer **benutzerdefinierten Windows 10-Richtlinie** von Microsoft Intune konfigurieren können..


> [!NOTE]
> In der Spalte **Unterstützt** der folgenden Tabelle werden die folgenden Werte verwendet:
> 
> -   **Desktop** – Diese Einstellung unterstützt nur Windows 10 Professional- und Enterprise-Computer, die bei Intune registriert sind.
> -   **Mobil** – Diese Einstellung unterstützt nur Windows 10 Mobile-Geräte.
> -   **Beide** – Diese Einstellung unterstützt Desktop- und mobile Geräte.
> 
> Wenn Sie die benutzerdefinierte Windows-URI-Richtlinie verwenden möchten, müssen alle Geräte bei Intune registriert sein.

### Richtlinie

|Name der Richtlinie|Unterstützt|Details|
|---------------|------------|-----------|
|**​Automatische Aktualisierung zulassen**|desktop-|**Vollständiger URI-Pfad**: ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** - **5**<br /><br />**Standardwert:** 1|
|**Installationstag planen**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Täglich<br /><br />**1** – Sonntag<br /><br />**2** – Montag<br /><br />**3** – Dienstag<br /><br />**4** – Mittwoch<br /><br />**5** – Donnerstag<br /><br />**6** – Freitag<br /><br />**7** – Samstag<br /><br />**Standardwert:** 0|
|**Installationszeit planen**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0**-**23** Uhr (0 ist Mitternacht)<br /><br />**Standardwert:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Der Benutzer kann den Timer für die Kennwort-Toleranzperiode nicht einstellen, und der Wert wird auf „immer“ festgelegt.<br /><br />**1** – Der Benutzer kann den Timer für die Kennwort-Toleranzperiode einstellen.<br /><br />**Standardwert:** 1|
|**WiFi/AllowWiFi**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – **WLAN-Verbindung nicht zulassen**.<br /><br />**1** – **WLAN-Verbindung zulassen**.<br /><br />**Standardwert:** 1|
|**WiFi/AllowInternetSharing**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nutzung der Internetverbindung nicht zulassen.<br /><br />**1** – Nutzung der Internetverbindung zulassen.<br /><br />**Standardwert:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – WLAN-Verbindung außerhalb von MDM-Bereitstellung nicht zulässig.<br /><br />**1** – Hinzufügen von neuen Netzwerk-SSIDs über die bereits mit MDM bereitgestellten hinaus zulässig.<br /><br />**Standardwert:** 1|
|**System/AllowLocation**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**System/AllowTelemetry**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig (nur Enterprise-Einstellung)<br /><br />**1** – Beschränkt<br /><br />**2** – Vollständig<br /><br />**3** – Vollständig und Diagnoseinformationen<br /><br />**Standardwert:** 2|
|**System/AllowExperimentation**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Nur Einstellungen<br /><br />**2** – Einstellungen und Experimente<br /><br />**Standardwert:** 1|
|**Security/AntiTheftMode**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Anti-Diebstahl-Modus nicht zulassen<br /><br />**1** – Benutzereinstellung<br /><br />**Standardwert:** 1|
|**Connectivity/AllowUSBConnection**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**System/AllowUserToResetPhone**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Connectivity/AllowCellularDataRoaming**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Connectivity/AllowVPNOverCellular**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – VPN über Mobiltelefon nicht zulässig<br /><br />**1** – VPN kann beliebige Verbindung einschließlich Mobiltelefon verwenden.<br /><br />**Standardwert:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Connectivity/AllowBluetooth**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulassen, dass der Benutzer Bluetooth aktiviert.<br /><br />**1** – Reserviert. Der Benutzer kann Bluetooth aktivieren und konfigurieren (wird in Windows Phone 8.1 für MDM, EAS, Windows 10 Desktop oder Windows 10 Mobile nicht unterstützt).<br /><br />**2** – Zulässig. Der Benutzer kann Bluetooth aktivieren und konfigurieren.<br /><br />**Standardwert:** 2|
|**Experience/AllowScreenCapture**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Experience/AllowTaskSwitcher**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Experience/AllowVoiceRecording**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Experience/AllowSyncMySettings**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Roaming nicht zulassen<br /><br />**1** – Roaming zulassen<br /><br />**Standardwert:** 1|
|**Experience/AllowManualMDMUnenrollment**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Security/AllowManualRootCertificateInstallation**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Security/AllowAddProvisioningPackages**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Search/DisableBackoff**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**Search/PreventRemoteQueries**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 1|
|**Search/AllowUsingDiacritics**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**Search/AlwaysUseAutoLangDetection**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**Search/DisableRemovableDriveIndexing**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**Security/AllowRemoveProvisioningPackage**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Security/RequireProvisioningPackageSignature**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**<br /><br />**1**<br /><br />**Standardwert:** 0|
|**AboveLock/AllowActionCenterNotifications**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/AllowIMENetworkAccess**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulassen<br /><br />Offenes erweitertes Wörterbuch ist deaktiviert.<br /><br />Ein Benutzer kann nicht:<br /><br />Ein neues offenes erweitertes Wörterbuch hinzufügen<br /><br />Eine neue Konfigurationsdatei für die Suchintegration hinzufügen<br /><br />Die Cloudkandidat-Funktion verwenden<br /><br />Von Benutzer registriertes Wort senden<br /><br />Darüber hinaus gilt:<br /><br />Ein offenes erweitertes Wörterbuch, das hinzugefügt wurde, bevor Sie diese Richtlinieneinstellung aktiviert haben, wird für die Konvertierung nicht verwendet.<br /><br />Eine Konfigurationsdatei für die Suchintegration, die vor der Aktivierung dieser Richtlinieneinstellung installiert wurde, wird nicht verwendet.<br /><br />**1** – Zulassen<br /><br />Offenes erweitertes Wörterbuch kann hinzugefügt und als Standard verwendet werden. Darüber hinaus kann die Suchintegrationsfunktion als Standard verwendet werden.<br /><br />Ein Benutzer kann:<br /><br />Die Cloudkandidat-Funktion verwenden<br /><br />Von Benutzer registriertes Wort senden<br /><br />**Standardwert:**|
|**TextInput/AllowKoreanExtendedHanja**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/AllowIMELogging**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Fehlerkonvertierungsprotokollierung ist deaktiviert. Automatisch optimierte Daten und Eingabeverlaufsdaten werden nicht in einer Datei gespeichert.<br /><br />**1** – Fehlerkonvertierungsprotokollierung ist aktiviert. Automatisch optimierte Daten und Eingabeverlaufsdaten werden in einer Datei gespeichert.<br /><br />**Standardwert:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/AllowJapaneseUserDictionary**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Alle außer JIS-Zeichen werden gefiltert.<br /><br />**1** – Zeichen werden nicht gefiltert.<br /><br />**Standardwert:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Alle außer JIS0208-Zeichen werden gefiltert.<br /><br />**1** – Zeichen werden nicht gefiltert.<br /><br />**Standardwert:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Alle außer JIS0208- oder EUDC-Zeichen werden gefiltert.<br /><br />**1** – Zeichen werden nicht gefiltert.<br /><br />**Standardwert:** 1|
|**TextInput/AllowInputPanel**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Bluetooth/AllowDiscoverableMode**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Bluetooth/AllowAdvertising**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowDataSense**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowVPN**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowWorkplace**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowDateTime**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowLanguage**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowRegion**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowSignInOptions**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowYourAccount**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowPowerSleep**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Settings/AllowAutoPlay**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Experience/AllowCortana**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Search/SafeSearchPermissions**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Strikte, höchste Filterung nicht jugendfreier Inhalte<br /><br />**1** – Moderate Filterung nicht jugendfreier Inhalte (gültige Suchergebnisse werden nicht gefiltert)<br /><br />**Standardwert:** 1|
|**Experience/AllowCopyPaste**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**Anfängliche Größe erzwingen**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Benutzer kann Größe ändern.<br /><br />**1** – Nicht-Vollbild erzwingen<br /><br />**2** – Vollbild erzwingen<br /><br />**Standardwert:** 0|
|**Update/RequireDeferUpgrade**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Upgrade nicht zurückstellen (Current Branch, CB, beibehalten)<br /><br />**1** – Zurückstellen von Updates und Upgrades ermöglichen (Gerät befolgt CBB- Regeln, Current Branch for Business)<br /><br />**Standardwert: 0**<br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br /><br />[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Beide|**Beschreibung**: Richtlinie zum Zurückstellen von Softwareupdates für bis zu 4 Wochen<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:** 0 – Updates umgehend anwenden; 1-4 – Softwareupdates für die angegebene Anzahl von Wochen zurückstellen.<br /><br />**Standardwert: 0**<br /><br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br /><br />[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Beide|**Beschreibung**: Richtlinie zum Zurückstellen von Featureupgrades für bis zu 8 Monate<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:** 0 – Updates umgehend anwenden; 1-8 – Featureupgrades für die angegebene Anzahl von Monaten zurückstellen.<br /><br />**Standardwert: 0**<br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br /><br />[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Beide|**Beschreibung**: Mit dieser Einstellung wird der Empfang von Updates und Upgrades auf einem CBB-Computer für bis zu 5 Wochen unterbrochen. Verwenden Sie diese Einstellung, wenn mit einem Update ein Problem auftritt.<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0**: Updates umgehend anwenden (Standardeinstellung)<br /><br />**1**: Updates und Upgrades anhalten (läuft nach 5 Wochen ab)<br /><br />**Standardwert: 0**|

### Windows Defender

|Name der Richtlinie|Unterstützt|Details|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowBehaviorMonitoring**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowIntrusionPreventionSystem**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowIOAVProtection**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowScriptScanning**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowOnAccessProtection**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**RealTimeScanDirection**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Alle Dateien (bidirektional) überwachen<br /><br />**1** – Eingehende Dateien überwachen<br /><br />**2** – Ausgehende Dateien überwachen<br /><br />**Standardwert:** 0|
|**DaysToRetainCleanedMalware**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** - **90** – Diese Werte geben an, wie lange Schadsoftware aufbewahrt wird.<br /><br />**Standardwert:** 0 – Der Quarantäneordner wird für eine unbegrenzte Zeitdauer aufbewahrt und nicht automatisch entfernt.|
|**AllowUserUIAccess**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**ScanParameter**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**1** – Schnellüberprüfung<br /><br />**2** – Vollständige Überprüfung<br /><br />**Standardwert:** 1|
|**ScheduleScanDay**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Täglich<br /><br />**1** – Montag<br /><br />**2** – Dienstag<br /><br />**3** – Mittwoch<br /><br />**4** – Donnerstag<br /><br />**5** – Freitag<br /><br />**6** – Samstag<br /><br />**7** – Sonntag<br /><br />**8** – Keine geplante Überprüfung<br /><br />**Standardwert:** 0|
|**ScheduleScanTime**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – 12:00 Uhr<br /><br />**60** – 1:00 Uhr<br /><br />**120** – 2:00 Uhr<br /><br />**180** – 3:00 Uhr<br /><br />**240** – 4:00 Uhr<br /><br />**300** – 5:00 Uhr<br /><br />**360** – 6:00 Uhr<br /><br />**420** – 7:00 Uhr<br /><br />**480** – 8:00 Uhr<br /><br />**540** – 9:00 Uhr<br /><br />**600** – 10:00 Uhr<br /><br />**660** – 11:00 Uhr<br /><br />**720** – 12:00 Uhr<br /><br />**780** – 13:00 Uhr<br /><br />**840** – 14:00 Uhr<br /><br />**900** – 15:00 Uhr<br /><br />**960** – 16:00 Uhr<br /><br />**1020** – 17:00 Uhr<br /><br />**1080** – 18:00 Uhr<br /><br />**1140** – 19:00 Uhr<br /><br />**1200** – 20:00 Uhr<br /><br />**1260** – 21:00 Uhr<br /><br />**1320** – 22:00 Uhr<br /><br />**1381** – Wartungsfenster<br /><br />**Standardwert:** 120|
|**ScheduleQuickScanTime**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – 12:00 Uhr<br /><br />**60** – 1:00 Uhr<br /><br />**120** – 2:00 Uhr<br /><br />**180** – 3:00 Uhr<br /><br />**240** – 4:00 Uhr<br /><br />**300** – 5:00 Uhr<br /><br />**360** – 6:00 Uhr<br /><br />**420** – 7:00 Uhr<br /><br />**480** – 8:00 Uhr<br /><br />**540** – 9:00 Uhr<br /><br />**600** – 10:00 Uhr<br /><br />**660** – 11:00 Uhr<br /><br />**720** – 12:00 Uhr<br /><br />**780** – 13:00 Uhr<br /><br />**840** – 14:00 Uhr<br /><br />**900** – 15:00 Uhr<br /><br />**960** – 16:00 Uhr<br /><br />**1020** – 17:00 Uhr<br /><br />**1080** – 18:00 Uhr<br /><br />**1140** – 19:00 Uhr<br /><br />**1200** – 20:00 Uhr<br /><br />**1260** – 21:00 Uhr<br /><br />**1320** – 22:00 Uhr<br /><br />**1380** – 23:00 Uhr<br /><br />**Standardwert:** 120|
|**AVGCPULoadFactor**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** - **100**<br /><br />**Standardwert:** 50|
|**AllowArchiveScanning**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowEmailScanning**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 0|
|**AllowFullScanRemovableDriveScanning**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 0|
|**AllowFullScanOnMappedNetworkDrives**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**AllowScanningNetworkFiles**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1 – wird auch ausgeführt, wenn RTP aktiviert und zulässig ist|
|**SignatureUpdateInterval**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Bei Intervall keine Signaturen überprüfen<br /><br />**1** – Signaturen stündlich überprüfen<br /><br />**2** – Signaturen alle 2 Stunden überprüfen, usw.<br /><br />**24** – Signaturen täglich überprüfen<br /><br />**Standardwert:** 8 – alle 8 Stunden auf Signaturen prüfen|
|**AllowCloudProtection**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Nicht zulässig<br /><br />**1** – Zulässig<br /><br />**Standardwert:** 1|
|**SubmitSamplesConsent**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Immer bestätigen<br /><br />**1** – Sichere Beispiele automatisch senden<br /><br />**2** – Nie senden<br /><br />**3** – Alle Beispiele automatisch senden<br /><br />**Standardwert:** 0|
|**ExcludedExtensions**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br /><br />*&lt;Liste der durch Semikolon getrennten Erweiterungen&gt;* Beispiel: **obj;lib**<br /><br />**Standardwert:** Keine Erweiterungen ausgeschlossen|
|**ExcludedPaths**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br /><br />*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br /><br />Beispiel: **c:\test;c:\test1.exe**<br /><br />**Standardwert:** Keine Pfade ausgeschlossen|
|**ExcludedProcesses**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br /><br />*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br /><br />Beispiel: **c:\test.exe;c:\test1.exe**<br /><br />**Standardwert:** Keine Prozesse ausgeschlossen|

### Edgebrowser

|Name der Richtlinie|Unterstützt|Details|
|---------------|------------|-----------|
|**Browser zulassen**|Handy|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Durchsuchen deaktiviert; **1** – Durchsuchen aktiviert.<br /><br />**Standardwert:** 1|
|**AllowSearchSuggestionsinAddressBar**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Suchvorschläge nicht anzeigen; **1** – Suchvorschläge anzeigen.<br /><br />**Standardwert:** 1|
|**SendIntranetTraffictoInternetExplorer**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Deaktiviert (Intranetsites in Edge öffnen); **1** – Aktiviert (Intranetsites in Internet Explorer öffnen).<br /><br />**Standardwert:** 0|
|**DNT (Do Not Track) zulassen**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Deaktiviert (DNT nicht gesendet); **1** – Aktiviert (DNT senden)<br /><br />**Standardwert:** 0|
|**SmartScreen konfigurieren**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Nicht zulassen; **1** – Zulassen<br /><br />**Standardwert:** 1|
|**Popups zulassen**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Popups blockieren; **1** – Popups zulassen<br /><br />**Standardwert:** 0|
|**Cookies zulassen**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Nicht blockieren. Cookies von allen Websites zulassen; **1** – Nur Drittanbietercookies blockieren; **2** – Alle Cookies blockieren.<br /><br />**Standardwert:** 0|
|**Speichern von Kennwörtern zulassen**|Beide|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Datentyp:** Ganzzahl<br /><br />**0** – Kennwort-Manager ist deaktiviert. <br />                        **1** – Kennwort-Manager ist aktiviert.<br /><br />**Standardwert:** 1|
|**AutoAusfüllen zulassen**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte: 0** – Deaktiviert; **1** – Aktiviert<br /><br />**Standardwert:** 0|
|**Websiteliste für den Unternehmensmodus konfigurieren**|desktop-|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte: 0** – Nicht konfiguriert; **1** – Websiteliste für den Unternehmensmodus von Internet Explorer verwenden (sofern konfiguriert); **2** – Speicherort für die Websiteliste für den Unternehmensmodus angeben.<br /><br />**Standardwert:** 1|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


