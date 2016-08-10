---
title: "Einstellungen für Windows 10-Richtlinien | Microsoft Intune"
description: "Verwenden Sie die in diesem Thema aufgeführten Richtlinieneinstellungen, um integrierte und benutzerdefinierte Einstellungen für registrierte Windows 10 Desktop- und Windows 10-Mobilgeräte zu konfigurieren."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7ef205aece89667ea84b9b73e42e71fc540fa257
ms.openlocfilehash: cbfd2da544814dc93a818a1ca5bd0496a268634b


---

# Einstellungen für Windows 10-Richtlinien in Microsoft Intune

Verwenden Sie die in diesem Thema aufgeführten Richtlinieneinstellungen, um integrierte und benutzerdefinierte Einstellungen für registrierte Windows 10 Desktop- und Windows 10-Mobilgeräte zu konfigurieren.

> [!IMPORTANT]
> Sie können Windows 10-PCs auf zwei Arten verwalten: durch Registrierung oder durch Installation der Intune-PC-Clientsoftware. Jede Methode bietet verschiedene Funktionen (weitere Informationen finden Sie unter [Auswählen der Methode zum Verwalten von Geräten](/intune/get-started/choose-how-to-manage-devices)).
> Beim Verwalten Ihrer Windows 10-PCs mit der Intune-PC-Clientsoftware können Sie nicht die in diesem Thema beschriebenen Richtlinien und Einstellungen verwenden. Um diese Einstellungen anzuwenden, müssen Ihre Windows 10-Geräte bei Intune registriert sein.

## Allgemeine Konfigurationsrichtlinieneinstellungen

Verwenden Sie die **allgemeine Microsoft Intune-Konfigurationsrichtlinie** für Windows 10, um allgemeine Einstellungen für registrierte Windows 10 Desktop- und Windows 10 Mobile-Geräte zu konfigurieren. 


### Kennwort

|Name der Einstellung|Details|
|----------------|----------------------|
|**Anfordern eines Kennworts zum Entsperren von Geräten**|Auf unterstützten Geräten ein Kennwort erfordern.|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|
|**Erforderlicher Kennworttyp** - **Minimale Anzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen.|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Gerätekennwort enthalten muss.<br>(Nur Windows 10 Mobile)|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Setzt das Gerät zurück, wenn diese Anzahl von Anmeldeversuchen fehlschlägt.|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Gibt den Zeitraum an, für den sich das Gerät im Leerlauf befinden muss, bevor der Bildschirm gesperrt wird.|
|**Kennwortablauf (Tage)**|Gibt die Zeitspanne an, nach der das Kennwort für das Gerät geändert werden muss.|
|**Kennwortverlauf speichern**|Gibt an, ob Sie verhindern möchten, dass der Endbenutzer zuvor verwendete Kennwörter erstellt.|
|**Kennwortverlauf speichern** - **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|
|**Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt**|Ist diese Einstellung aktiviert, muss der Benutzer ein Kennwort zum Entsperren des Geräts nach dem Leerlauf eingeben.<br>(Nur Windows 10 Mobile)|

### Verschlüsselung

|Name der Einstellung|Details|
|----------------|----------------------|
|**Verschlüsselung auf mobilen Geräten vorschreiben**|Ermöglicht die Verschlüsselung auf Zielgeräten.<br>(Nur Windows 10 Mobile)|

### System

|Name der Einstellung|Details|
|----------------|----------------------|
|**Bildschirmaufnahme zulassen**|Ermöglicht dem Benutzer, den Bildschirm des Geräts als Bild zu erfassen.<br>(Nur Windows 10 Mobile)|
|**Manuelles Aufheben der Registrierung zulassen**|Ermöglicht dem Benutzer das manuelle Löschen des Unternehmensbereichskontos vom Gerät.|
|**Manuelle Installation des Stammzertifikats zulassen**|Gibt an, ob der Benutzer Stammzertifikate manuell installieren kann.<br>(Nur Windows 10 Mobile)|
|**Senden von Diagnose- und Verwendungsdaten an Microsoft zulassen**|Bestimmt den Umfang an Diagnose- und Verwendungsdaten, die von Geräten an Microsoft gesendet werden.<br><br>**Nein**: Keine Daten werden an Microsoft gesendet.<br>**Standard**: Das Gerät sendet nur begrenzte Informationen an Microsoft.<br>**Erweitert**: Das Gerät sendet erweiterte Diagnosedaten an Microsoft.<br>**Vollständig (empfohlen)**: Das Gerät sendet die gleichen Daten wie mit **Erweitert** sowie zusätzliche Daten über den Gerätezustand.|


### Konto und Synchronisierung

|Name der Einstellung|Details|
|----------------|----------------------|---------------------|
|**Microsoft-Konto erlauben**|Ermöglicht dem Benutzer, das Gerät einem Microsoft-Konto zuzuordnen.|
|**Manuelles Hinzufügen von Nicht-Microsoft-Konten zulassen**|Ermöglicht dem Benutzer, dem Gerät E-Mail-Konten hinzuzufügen, die nicht mit einem Microsoft-Konto verknüpft sind.|
|**Synchronisierung von Einstellungen für Microsoft-Konten zulassen**|Ermöglicht das Synchronisieren der mit einem Microsoft-Konto verknüpften Geräte- und App-Einstellungen zwischen Geräten.|

### Microsoft Edge

|Name der Einstellung|Details|
|----------------|----------------------|
|**Webbrowser zulassen**|Ermöglichen Sie die Verwendung des Edge-Webbrowsers auf dem Gerät.<br>(Nur Windows 10 Mobile)|
|**Suchvorschläge auf der Adressleiste zulassen**|Ermöglicht dem Suchmodul, Websites während der Eingabe von Suchausdrücken vorzuschlagen.|
|**Senden von Intranetdatenverkehr an Internet Explorer zulassen**|Ermöglicht Benutzern, Intranetwebsites in Internet Explorer zu öffnen.<br>(Nur Windows 10 Desktop)|
|**Nicht verfolgen (Do not track) zulassen**|Konfiguriert den Edge-Browser zum Senden von DNT-Headern (Do Not Track, nicht nachverfolgen) an Websites, die Benutzer besuchen.|
|**SmartScreen aktivieren**|Aktiviert die SmartScreen-Browsereinstellung auf Geräten.|
|**Active Scripting zulassen**|Ermöglicht die Ausführung von Skripts wie JavaScript im Edge-Browser.|
|**Popups zulassen**|Aktiviert oder deaktiviert den Popupblocker des Browsers.<br>(Nur Windows 10 Desktop)|
|**Cookies zulassen**|Aktiviert oder deaktiviert Cookies.|
|**AutoAusfüllen zulassen**|Ermöglicht Benutzern, die Einstellungen für AutoVervollständigen im Browser zu ändern.<br>(Nur Windows 10 Desktop)|
|**Kennwort-Manager zulassen**|Aktivieren oder deaktivieren Sie den Edge-Kennwort-Manager.|
|**Ort der Standortliste für Enterprise-Modus**|Gibt an, wo Sie die Liste der Websites finden, die im Unternehmensmodus geöffnet werden. Benutzer können diese Liste nicht bearbeiten.<br>(Nur Windows 10 Desktop)|

### Apps

|Name der Einstellung|Details|
|----------------|----------------------|---------------------|
|**App Store zulassen**|Ermöglicht dem Benutzer den Zugriff auf den App Store auf dem Gerät.<br>(Nur Windows 10 Mobile)|



### Mobilfunk

|Name der Einstellung|Details|
|----------------|----------------------|---------------------|
|**Datenroaming zulassen**|Ermöglicht beim Zugriff auf Daten das Roaming zwischen Netzwerken.|
|**VPN über Mobilfunk zulassen**|Steuert, ob das Gerät auf VPN-Verbindungen zugreifen kann, wenn es mit einem Mobilfunknetz verbunden ist.|
|**VPN-Roaming über Mobilfunk zulassen**|Steuert, ob das Gerät beim Roaming in einem Mobilfunknetz auf VPN-Verbindungen zugreifen kann.|

### Hardware

|Name der Einstellung|Details|
|----------------|----------------------|
|**Kamera zulassen**|Gibt an, ob die Kamera des Geräts verwendet werden darf.|
|**Wechselspeichermedien zulassen**|Gibt an, ob externe Speichergeräte wie SD-Karten mit dem Gerät verwendet werden können.|
|**WLAN zulassen**|Ermöglicht die Verwendung der WLAN-Funktion der Geräte.<br>(Nur Windows 10 Mobile)|
|**Internetfreigabe zulassen**|Ermöglicht die gemeinsame Nutzung der Internetverbindung auf dem Gerät.|
|**Manuelle WLAN-Konfiguration zulassen**|Steuert, ob die Benutzer eigene WLAN-Verbindungen konfigurieren dürfen oder ob nur über WLAN-Profile konfigurierte Verbindungen verwendet werden dürfen.<br>(Nur Windows 10 Mobile)|
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Ermöglicht automatische Verbindungen des Geräts mit unverschlüsselten WLAN-Hotspots und das automatische Akzeptieren der Geschäftsbedingungen für die Verbindung.|
|**Geolocation zulassen**|Gibt an, ob das Gerät Ortungsdienstinformationen verwenden kann.|
|**NFC zulassen**|Ermöglicht die Verwendung von NFC-Funktionen (Near Field Communications) auf dem Gerät.|
|**Bluetooth zulassen**|Ermöglicht die Verwendung von Bluetooth-Funktionen auf dem Gerät.|
|**Sichtbaren Modus für Bluetooth zulassen**|Ermöglicht die Erkennung dieses Geräts durch andere Bluetooth-Geräte.|
|**Bluetooth-Werbung zulassen**|Ermöglicht Geräten dem Empfang von Werbung über Bluetooth.|
|**Handyzurücksetzung zulassen**|Steuert, ob Benutzer ihre Geräte auf Werkseinstellungen zurücksetzen dürfen.|
|**USB-Verbindung zulassen**|Steuert, ob die Geräte über eine USB-Verbindung auf externe Speichergeräte zugreifen können.|
|**Diebstahlschutzmodus zulassen**|Konfigurieren Sie, ob der Windows-Diebstahlschutzmodus aktiviert ist.|

### Features

|Name der Einstellung|Details|
|----------------|----------------------|---------------------|
|**Kopieren und Einfügen zulassen**|Aktivieren oder deaktivieren Sie die Verwendung von Kopieren und Einfügen auf dem Gerät.<br>(Nur Windows 10 Mobile)|
|**Sprachaufzeichnung zulassen**|Aktivieren oder deaktivieren Sie Funktionen für Sprachaufzeichnungen auf dem Gerät.<br>(Nur Windows 10 Mobile)|
|**Cortana zulassen**|Aktivieren oder deaktivieren Sie den Cortana-Sprach-Assistenten.|
|**Info-Center-Benachrichtigungen zulassen**|Aktivieren oder deaktivieren Sie Wartungscenterbenachrichtigungen auf dem Gerätesperrbildschirm.<br>(Nur Windows 10 Mobile)|

### Defender

Alle Einstellungen gelten für nur Windows 10 Desktop.

|Name der Einstellung|Details|
|-|-|
|**Echtzeitüberwachung zulassen**|Ermöglicht die Echtzeitüberwachung auf Schadsoftware, Spyware und andere unerwünschte Software.|
|**Verhaltensüberwachung zulassen**|Ermöglicht Defender, Geräte auf bestimmte bekannte Muster verdächtiger Aktivitäten zu überprüfen.|
|**Netzwerkinspektionssystem aktivieren**|Das Netzwerkinspektionssystem (NIS) trägt zum Schutz von Geräten vor netzwerkbasierten Sicherheitslücken bei, indem die Signaturen bekannter Sicherheitsrisiken aus dem Endpoint Protection-Center von Microsoft verwendet werden, um schädlichen Datenverkehr zu erkennen und zu blockieren.|
|**Alle Downloads werden überprüft**|Steuert, ob Defender alle aus dem Internet heruntergeladenen Dateien überprüft.|
|**Skriptüberprüfung zulassen**|Ermöglicht Defender die Überprüfung von Skripts, die in Internet Explorer verwendet werden.|
|**Datei- und Programmaktivität überwachen**|Aktivieren Sie diese Einstellung, um Defender die Überwachung der Datei- und Programmaktivität auf Geräten zu ermöglichen.|
|**Tage für Nachverfolgung behandelter Schadsoftware**|Ermöglicht Defender die fortgesetzte Nachverfolgung behandelter Schadsoftware für die angegebene Anzahl von Tagen, damit Sie zuvor betroffene Geräte manuell überprüfen können. Wenn Sie die Anzahl von Tagen auf **0** festlegen, bleibt Schadsoftware im Quarantäneordner und wird nicht automatisch entfernt. |
|**Zugriff auf die Clientbenutzeroberfläche zulassen**|Steuert, ob die Benutzeroberfläche von Windows Defender für Endbenutzer ausgeblendet ist.<br>Wenn diese Einstellung geändert wird, wird die Änderung wirksam, wenn der Endbenutzer-PC das nächste Mal neu gestartet wird.|
|**Eine tägliche Schnellüberprüfung planen**|Ermöglicht Ihnen die Planung einer Schnellüberprüfung, die täglich zum ausgewählten Zeitpunkt erfolgt.|
|**Systemüberprüfung planen**|Sie können eine vollständige Überprüfung oder eine Schnellüberprüfung des Systems planen, die regelmäßig am ausgewählten Tag und zur ausgewählten Zeit auftritt.|
|**Prozessornutzung während der Überprüfung begrenzen auf**|Ermöglicht die Begrenzung des Umfangs an CPU, der bei Überprüfungen genutzt werden darf (von **1** bis **100**).|
|**Archivdateien überprüfen**|Ermöglicht Defender die Überprüfung von Archivdateien wie ZIP- oder CAB-Dateien.|
|**Scannen von E-Mail-Nachrichten**|Ermöglicht Defender das Überprüfen von E-Mail-Nachrichten beim Eingang auf dem Gerät.|
|**Wechseldatenträger überprüfen**|Ermöglicht Defender das Überprüfen von Wechseldatenträgern wie USB-Sticks.|
|**Zugeordnete Netzwerklaufwerke überprüfen**|Ermöglicht Defender das Überprüfen von Dateien auf zugeordneten Netzwerklaufwerken.<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|
|**Dateien überprüfen, die in freigegebenen Netzwerkordnern geöffnet wurden**|Ermöglicht Defender das Überprüfen von Dateien auf freigegebenen Netzlaufwerken (z. B. solche, auf die über einen UNC-Pfad zugegriffen wird).<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.|
|**Intervall zum Aktualisieren von Signaturen**|Geben Sie das Intervall an, in dem Defender auf neue Signaturdateien prüfen soll.|
|**Cloudschutz zulassen**|Lassen Sie zu, oder verhindern Sie, dass Microsoft Active Protection Service Informationen über Schadsoftwareaktivitäten von den von Ihnen verwalteten Geräten erhält. Diese Informationen werden verwendet, um den Dienst in der Zukunft zu verbessern.|
|**Beim Senden von Beispielen beim Benutzer nachfragen**|Steuert, ob die Dateien automatisch an Microsoft gesendet werden, die möglicherweise von Microsoft genauer analysiert werden müssen, um festzustellen, ob sie schädlich sind.|
|**Erkennung möglicherweise unerwünschter Anwendungen**|Mit dieser Einstellung können registrierte Windows-Desktopgeräte gegen die Ausführung von Software geschützt werden, die von Windows Defender als möglicherweise unerwünscht eingestuft wird. Sie können verhindern, dass diese Anwendungen ausgeführt werden, oder den Überwachungsmodus verwenden, um zu melden, wenn eine möglicherweise unerwünschte Anwendung installiert wird.|
|**Von der Überprüfung oder dem Echtzeitschutz auszuschließende Dateien und Ordner**|Fügen Sie Dateien und Ordner wie **C:\Pfad** oder **%ProgramFiles%\Pfad\Dateiname.exe** der Ausschlussliste hinzu. Diese Dateien und Ordner werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|
|**Dateierweiterungen, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Dateierweiterungen wie **JPG** oder **TXT** der Ausschlussliste hinzu. Dateien mit diesen Erweiterungen werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.|
|**Prozesse, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Fügen Sie Prozesse des Typs **.exe**, **.com** oder **.scr** der Ausschlussliste hinzu. Diese Prozesse werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.| 


### Updateeinstellungen

|Name der Einstellung|Details|
|----------------|---------------|
|**Automatische Updates zulassen**|Aktivieren Sie diese Einstellung, um automatische Updates zuzulassen. Konfigurieren Sie dann eine der folgenden Einstellungen, um das Updateverhalten zu steuern:<br /><br />**Download benachrichtigen**<br /><br />**Automatische Installation während der Wartung**<br /><br />**Automatische Installation und Neustart während der Wartung**<br /><br />**Zur festgelegten Zeit automatisch installieren und neu starten** **Hinweis**: Wenn diese Option ausgewählt ist, können Sie auch die folgenden Einstellungen konfigurieren: **Benachrichtigung für Endbenutzer unterdrücken** und **Installationstag für geplante Updates definieren**.<br>(Nur Windows 10 Desktop)|
|**Features der Vorabversion zulassen**|Bietet Microsoft die Möglichkeit, Einstellungen und Features der Vorabversion für Windows 10-Geräte bereitzustellen. Sie können auswählen, ob nur Einstellungen oder alle Einstellungen und Features der Vorabversion installiert werden sollen.|

## Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Microsoft Intune-Konfigurationsrichtlinie** für Windows 10 und Windows 10 Mobile Einstellungen für OMA-URI (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Windows 10- und Windows 10 Mobile-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Windows 10-Einstellungen bereitzustellen, die nicht mit einer allgemeinen Intune-Konfigurationsrichtlinie konfigurierbar sind.



### Allgemeine Einstellungen der benutzerdefinierten Richtlinie

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für die Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
    |**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### OMA-URI-Einstellungen der benutzerdefinierten Richtlinie

|Name der Einstellung|Details|
    |--------|--------------------|
    |**Name der Einstellung**|Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
    |**Beschreibung der Einstellung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**Datentyp**|Wählen Sie den Datumstyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus:<br /><br />-   **Zeichenfolge**<br />-   **Zeichenfolge (XML)**<br />-   **Datum und Uhrzeit**<br />-   **Ganze Zahl**<br />-   **Gleitkomma**<br />-   **Boolesch**|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|


## Benutzerdefinierte URI-Einstellungen für Windows 10-Geräte
In diesem Thema werden die Einstellungen aufgeführt, die Sie für Windows 10- und Windows 10 Mobile-Geräte in einer **benutzerdefinierten Windows 10-Richtlinie** von Microsoft Intune konfigurieren können.

Wenn Sie die benutzerdefinierte Windows-URI-Richtlinie verwenden möchten, müssen alle Geräte bei Intune registriert sein.

### URI-Einstellungen von Richtlinien

|Name der Richtlinie|Details|
|---------------|------------|-----------|
|**​Automatische Aktualisierung zulassen**<br>(nur Desktop)|**Vollständiger URI-Pfad**: ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** - **5** (Standard: **1**)|
|**Installationstag planen**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Täglich (Standard)<br>**1** – Sonntag<br>**2** – Montag<br>**3** – Dienstag<br>**4** – Mittwoch<br>**5** – Donnerstag<br>**6** – Freitag<br>**7** – Samstag|
|**Installationszeit planen**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – **23** Uhr (**0** ist Mitternacht) (Standard: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Der Benutzer kann den Timer für die Kennwort-Toleranzperiode nicht einstellen, und der Wert wird auf „immer“ festgelegt.<br>**1** – Der Benutzer kann den Timer für den Kennwort-Verlängerungszeitraum festlegen.|
|**WiFi/AllowWiFi**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – **WLAN-Verbindung nicht zulassen**.<br>**1** – **WLAN-Verbindung zulassen** (Standard)|
|**WiFi/AllowInternetSharing**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nutzung der Internetverbindung nicht zulassen.<br>**1** – Nutzung der Internetverbindung zulassen (Standard)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**WiFi/AllowManualWiFiConfiguration**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – WLAN-Verbindung außerhalb von MDM-Bereitstellung nicht zulässig.<br>**1** – Hinzufügen von neuen Netzwerk-SSIDs über die bereits mit MDM bereitgestellten hinaus zulässig (Standard)|
|**System/AllowLocation**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**System/AllowTelemetry**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig (nur Enterprise-Einstellung)<br>**1** – Beschränkt<br>**2** – Vollständig (Standard)<br>**3** – Vollständig und Diagnoseinformationen|
|**System/AllowExperimentation**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Nur Einstellungen (Standard)<br>**2** – Einstellungen und Experimente|
|**Security/AntiTheftMode**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Anti-Diebstahl-Modus nicht zulassen<br>**1** – Benutzereinstellung (Standard)|
|**Connectivity/AllowUSBConnection**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**System/AllowUserToResetPhone**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Connectivity/AllowCellularDataRoaming**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Connectivity/AllowVPNOverCellular**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – VPN über Mobiltelefon nicht zulässig<br>**1** – VPN kann beliebige Verbindung einschließlich Mobiltelefon verwenden (Standard).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Connectivity/AllowBluetooth**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulassen, dass der Benutzer Bluetooth aktiviert.<br>**1** – Reserviert. Der Benutzer kann Bluetooth aktivieren und konfigurieren (wird in Windows Phone 8.1 für MDM, EAS, Windows 10 Desktop oder Windows 10 Mobile nicht unterstützt).<br>**2** – Zulässig. Der Benutzer kann Bluetooth aktivieren und konfigurieren (Standard).|
|**Experience/AllowScreenCapture**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Experience/AllowTaskSwitcher**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Experience/AllowVoiceRecording**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Experience/AllowSyncMySettings**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Roaming nicht zulassen<br>**1** – Roaming zulassen (Standard)|
|**Experience/AllowManualMDMUnenrollment**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Security/AllowManualRootCertificateInstallation**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Security/AllowAddProvisioningPackages**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Search/DisableBackoff**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** (Standard)<br>**1**|
|**Search/PreventRemoteQueries**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**<br>**1** (Standard)|
|**Search/AllowUsingDiacritics**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br> **0** (Standard)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** (Standard)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** (Standard)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**<br>**1** (Standard)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** (Standard)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Security/RequireProvisioningPackageSignature**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** (Standard)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**TextInput/AllowIMENetworkAccess**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulassen<br>Offenes erweitertes Wörterbuch ist deaktiviert.<br>Ein Benutzer kann nicht:<br>Ein neues offenes erweitertes Wörterbuch hinzufügen<br /><br />Eine neue Konfigurationsdatei für die Suchintegration hinzufügen<br>Die Cloudkandidat-Funktion verwenden<br>Von Benutzer registriertes Wort senden<br>Darüber hinaus gilt:<br>Ein offenes erweitertes Wörterbuch, das hinzugefügt wurde, bevor Sie diese Richtlinieneinstellung aktiviert haben, wird für die Konvertierung nicht verwendet.<br>Eine Konfigurationsdatei für die Suchintegration, die vor der Aktivierung dieser Richtlinieneinstellung installiert wurde, wird nicht verwendet.<br>**1** – Zulassen<br>Offenes erweitertes Wörterbuch kann hinzugefügt und als Standard verwendet werden. Darüber hinaus kann die Suchintegrationsfunktion als Standard verwendet werden.<br>Ein Benutzer kann:<br>Die Cloudkandidat-Funktion verwenden<br>Von Benutzer registriertes Wort senden|
|**TextInput/AllowIMELogging**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Fehlerkonvertierungsprotokollierung ist deaktiviert. Automatisch optimierte Daten und Eingabeverlaufsdaten werden nicht in einer Datei gespeichert.<br>**1** – Fehlerkonvertierungsprotokollierung ist aktiviert. Automatisch optimierte Daten und Eingabeverlaufsdaten werden in einer Datei gespeichert (Standard).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**TextInput/AllowJapaneseUserDictionary**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS-Zeichen werden gefiltert.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br /><br />**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS0208-Zeichen werden gefiltert.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Zeichen werden nicht gefiltert (Standard).<br>**1** – Alle außer JIS0208- oder EUDC-Zeichen werden gefiltert.|
|**TextInput/AllowInputPanel**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Bluetooth/AllowDiscoverableMode**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Bluetooth/AllowAdvertising**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowDataSense**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowVPN**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowWorkplace**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowDateTime**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowLanguage**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowRegion**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowSignInOptions**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowYourAccount**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowPowerSleep**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Settings/AllowAutoPlay**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Experience/AllowCortana**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Search/SafeSearchPermissions**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Strikte, höchste Filterung nicht jugendfreier Inhalte<br>**1** – Moderate Filterung nicht jugendfreier Inhalte (gültige Suchergebnisse werden nicht gefiltert – Standard)|
|**Experience/AllowCopyPaste**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**Anfängliche Größe erzwingen**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Benutzer kann Größe ändern (Standard).<br>**1** – Nicht-Vollbild erzwingen<br>**2** – Vollbild erzwingen|
|**Update/RequireDeferUpgrade**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Upgrade nicht zurückstellen (Current Branch, CB, beibehalten – Standard)<br>**1** – Zurückstellen von Updates und Upgrades ermöglichen (Gerät befolgt CBB- Regeln, Current Branch for Business)<br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(Desktop und Mobile)|**Beschreibung**: Richtlinie zum Zurückstellen von Softwareupdates für bis zu 4 Wochen<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br> **0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**4**: Anzahl von Wochen für das Zurückstellen von Softwareupdates.<br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(Desktop und Mobile)|**Beschreibung**: Richtlinie zum Zurückstellen von Featureupgrades für bis zu 8 Monate<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**-**8**: Anzahl von Monaten für das Zurückstellen von Featureupgrades.<br /><br />Weitere Informationen finden Sie in folgenden Quellen:<br>[Einführung in die Wartung von Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planen der Windows 10-Bereitstellung](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(Desktop und Mobile)|**Beschreibung**: Mit dieser Einstellung wird der Empfang von Updates und Upgrades auf einem CBB-Computer für bis zu 5 Wochen unterbrochen. Verwenden Sie diese Einstellung, wenn mit einem Update ein Problem auftritt.<br /><br />**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**: Updates umgehend anwenden (Standardeinstellung)<br>**1**: Updates und Upgrades anhalten (läuft nach 5 Wochen ab)|

### Windows Defender-URI-Einstellungen

|Name der Richtlinie|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowBehaviorMonitoring**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowIntrusionPreventionSystem**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowIOAVProtection**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowScriptScanning**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowOnAccessProtection**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**RealTimeScanDirection**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Alle Dateien überwachen (bidirektional – Standard)<br>**1** – Eingehende Dateien überwachen<br>**2** – Ausgehende Dateien überwachen|
|**DaysToRetainCleanedMalware**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** - **90** – Gibt an, wie lange Schadsoftware gespeichert wird.<br>**Standardwert**: **0** – Der Quarantäneordner wird für eine unbegrenzte Zeitdauer aufbewahrt und nicht automatisch entfernt.|
|**AllowUserUIAccess**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**ScanParameter**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**1** – Schnellüberprüfung (Standard)<br>**2** – Vollständige Überprüfung|
|**ScheduleScanDay**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Täglich (Standard)<br>**1** – Montag<br>**2** – Dienstag<br>**3** – Mittwoch<br>**4** – Donnerstag<br>**5** – Freitag<br>**6** – Samstag<br>**7** – Sonntag<br>**8** – Keine geplante Überprüfung|
|**ScheduleScanTime**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – 12:00 Uhr<br>**60** – 1:00 Uhr<br>**120** – 2:00 Uhr (Standard)<br>**180** – 3:00 Uhr<br>**240** – 4:00 Uhr<br>**300** – 5:00 Uhr<br>**360** – 6:00 Uhr<br>**420** – 7:00 Uhr<br>**480** – 8:00 Uhr<br>**540** – 9:00 Uhr<br>**600** – 10:00 Uhr<br>**660** – 11:00 Uhr<br>**720** – 12:00 Uhr<br>**780** – 13:00 Uhr<br>**840** – 14:00 Uhr<br>**900** – 15:00 Uhr<br>**960** – 16:00 Uhr<br>**1020** – 17:00 Uhr<br>**1080** – 18:00 Uhr<br>**1140** – 19:00 Uhr<br>**1200** – 20:00 Uhr<br>**1260** – 21:00 Uhr<br>**1320** – 22:00 Uhr<br>**1381** – Wartungsfenster|
|**ScheduleQuickScanTime**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – 12:00 Uhr<br>**60** – 1:00 Uhr<br>**120** – 2:00 Uhr (Standard)<br>**180** – 3:00 Uhr<br>**240** – 4:00 Uhr<br>**300** – 5:00 Uhr<br>**360** – 6:00 Uhr<br>**420** – 7:00 Uhr<br>**480** – 8:00 Uhr<br>**540** – 9:00 Uhr<br>**600** – 10:00 Uhr<br>**660** – 11:00 Uhr<br>**720** – 12:00 Uhr<br>**780** – 13:00 Uhr<br>**840** – 14:00 Uhr<br>**900** – 15:00 Uhr<br>**960** – 16:00 Uhr<br>**1020** – 17:00 Uhr<br>**1080** – 18:00 Uhr<br>**1140** – 19:00 Uhr<br>**1200** – 20:00 Uhr<br>**1260** – 21:00 Uhr<br>**1320** – 22:00 Uhr<br>**1380** – 23:00 Uhr|
|**AVGCPULoadFactor**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:0** - **100** (Standard: **50**)|
|**AllowArchiveScanning**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowEmailScanning**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Datentyp:** Ganzzahl<br>**Zulässige Werte:**<br>**0** – Nicht zulässig (Standard)<br>**1** – Zulässig|
|**AllowFullScanRemovableDriveScanning**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig (Standard)<br>**1** – Zulässig|
|**AllowFullScanOnMappedNetworkDrives**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**AllowScanningNetworkFiles**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard) – Wird auch ausgeführt, wenn RTP aktiviert und zulässig ist.|
|**SignatureUpdateInterval**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Bei Intervall keine Signaturen überprüfen<br>**1** – Signaturen stündlich überprüfen<br>**2** – Signaturen alle 2 Stunden überprüfen, usw.<br>**24** – Signaturen täglich überprüfen<br>**Standardwert:** 8 – alle 8 Stunden auf Signaturen prüfen|
|**AllowCloudProtection**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulässig (Standard)|
|**SubmitSamplesConsent**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Immer bestätigen (Standard)<br>**1** – Sichere Beispiele automatisch senden<br>**2** – Nie senden<br>**3** – Alle Beispiele automatisch senden|
|**ExcludedExtensions**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br>*&lt;Liste der durch Semikolon getrennten Erweiterungen&gt;* Beispiel: **obj;lib**<br>**Standard:** Keine Erweiterungen ausgeschlossen|
|**ExcludedPaths**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br /><br />*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br /><br />Beispiel: **c:\test;c:\test1.exe**<br /><br />**Standardwert:** Keine Pfade ausgeschlossen|
|**ExcludedProcesses**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:**<br>*&lt;Liste der durch Semikolon getrennten Pfade&gt;*<br>Beispiel: **c:\test.exe;c:\test1.exe**<br>**Standardwert:** Keine Prozesse ausgeschlossen|

### URI-Einstellungen für den Edge-Browser

|Name der Richtlinie|Details|
|---------------|------------|-----------|
|**Browser zulassen**<br>(nur Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**: Browsen deaktiviert<br>**1**: Browsen aktiviert (Standard)|
|**AllowSearchSuggestionsinAddressBar**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**: Keine Suchvorschläge anzeigen<br>**1**: Suchvorschläge anzeigen (Standard)|
|**SendIntranetTraffictoInternetExplorer**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0**: Deaktiviert (Intranetsites im Edge-Browser öffnen – Standard)<br>**1**: Aktiviert (Intranetsites in Internet Explorer öffnen)|
|**Nicht verfolgen (Do not track) zulassen**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Deaktiviert (DNT nicht senden – Standard)<br>**1** – Aktiviert (DNT senden)|
|**SmartScreen konfigurieren**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht zulässig<br>**1** – Zulassen (Standard)|
|**Popups zulassen**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Keine Popups zulassen (Standard)<br>**1** – Popups zulassen|
|**Cookies zulassen**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Nicht blockieren. Cookies von allen Websites zulassen (Standard)<br>**1** – Cookies anderer Anbieter blockieren<br>**2** – Alle Cookies blockieren|
|**Speichern von Kennwörtern zulassen**<br>(Desktop und Mobile)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Kennwort-Manager deaktiviert <br>**1** – Kennwort-Manager aktiviert|
|**AutoAusfüllen zulassen**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Datentyp:** Ganzzahl<br /><br />**Zulässige Werte:**<br>**0** – Deaktiviert (Standard)<br>**1** – Aktiviert|
|**Websiteliste für den Unternehmensmodus konfigurieren**<br>(nur Desktop)|**Vollständiger URI-Pfad:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Datentyp:** Zeichenfolge<br /><br />**Zulässige Werte:<br>0** – Nicht konfiguriert<br>**1** – Websiteliste für den Unternehmensmodus von Internet Explorer verwenden (sofern konfiguriert) – Standard<br>**2** – Speicherort der Websiteliste für den Unternehmensmodus angeben|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Aug16_HO1-->


