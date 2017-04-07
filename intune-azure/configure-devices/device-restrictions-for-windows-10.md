---
title: "Einstellungen für Geräteeinschränkungen für Windows 10 in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Windows 10-Geräten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 74f99d5e2d4eef8d42ccd2c7bc34e0ed7b6f0d51
ms.lasthandoff: 02/18/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für Windows 10 und höher in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Allgemein
-     **Bildschirmaufnahme:** Erlaubt dem Benutzer, den Bildschirm des Geräts als Bild zu erfassen. (Nur Windows 10 Mobile)
-     **Kopieren und einfügen (nur mobil):** Erlauben Sie Kopier- und Einfügevorgänge zwischen Apps auf dem Gerät.
-     **Manuelle Aufhebung der Registrierung:** Erlaubt dem Benutzer das manuelle Löschen des Unternehmensbereichskontos vom Gerät.
-     **Manuelle Installation von Stammzertifikaten** -     
-     **Übermitteln von Diagnosedaten:** Mögliche Werte:
    -         **Keine:** Es werden keine Daten an Microsoft gesendet.
    -         **Einfach:** Es werden begrenzte Informationen an Microsoft gesendet.
    -         **Erweitert:** Es werden erweiterte Diagnosen an Microsoft gesendet.
    -         **Vollständig:** Das Gerät sendet die gleichen Daten wie mit „Erweitert“ sowie zusätzliche Daten über den Gerätezustand.
-     **Kamera:** Erlauben oder sperren Sie die Verwendung der Kamera auf dem Gerät.
-     **Wechselmedien:** Gibt an, ob externe Speichergeräte wie SD-Karten mit dem Gerät verwendet werden können.
-     **Geolocation:** Gibt an, ob das Gerät Standortdienstinformationen verwenden kann.
-     **Internetfreigabe:** Erlauben Sie die gemeinsame Nutzung der Internetverbindung auf dem Gerät.
-     **Zurücksetzung des Telefons:** Steuert, ob Benutzer ihre Geräte auf die Werkseinstellungen zurücksetzen können.
-     **USB-Verbindung:** Steuert, ob Geräte über eine USB-Verbindung auf externe Speichergeräte zugreifen können.
-     **AntiTheft-Modus:** Konfigurieren Sie, ob der Windows-AntiTheft-Modus aktiviert ist.
-     **Info-Center-Benachrichtigungen**: Aktivieren oder deaktivieren Sie Info-Center-Benachrichtigungen auf dem Gerätesperrbildschirm (nur Windows 10 Mobile).
-     **Cortana:** Aktivieren oder deaktivieren Sie den Cortana-Sprach-Assistenten.
-     **Sprachaufzeichnung:** Erlauben oder sperren Sie die Verwendung der Sprachaufzeichnung des Geräts.

## <a name="password"></a>Kennwort
-     **Kennwort erforderlich:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
-     **Erforderlicher Kennworttyp:** Gibt an, ob das Kennwort nur numerisch sein muss oder alphanumerisch.
-     **Minimale Kennwortlänge:** Gilt nur für Windows 10 Mobile.
-     **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird**: Für Geräte mit Microsoft 10: Wenn auf dem Gerät BitLocker aktiviert ist, wird in den BitLocker-Wiederherstellungsmodus gewechselt, sobald die Anzahl der von Ihnen angegebenen Anmeldefehler erreicht ist. Wenn BitLocker nicht für dieses Gerät aktiviert ist, wird diese Einstellung nicht angewendet.
Für Geräte mit Windows 10 Mobile: Das Gerät wird zurückgesetzt, sobald die Anzahl der von Ihnen angegebenen Anmeldeversuche fehlgeschlagen ist.
-     **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt den Zeitraum der Inaktivität für ein Gerät an, bevor der Bildschirm gesperrt wird.
-     **Kennwortablauf (Tage):** Gibt die Zeitdauer an, nach der das Kennwort für das Gerät geändert werden muss.
-     **Wiederverwendung vorheriger Kennwörter verhindern:** Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.
-     **Kennwort anfordern, wenn Gerät aus Leerlaufzustand zurückkehrt:** Gibt an, dass der Benutzer ein Kennwort zum Entsperren des Geräts eingeben muss (nur Windows 10 Mobile).
-     **Verschlüsselung:** Erlauben Sie die Verschlüsselung auf Zielgeräten (nur Windows 10 Mobile).
## <a name="app-store"></a>App Store

-     **App Store (nur mobil):** Erlauben oder sperren Sie die Verwendung des App Stores auf Windows 10 Mobile-Geräten.
## <a name="edge-browser"></a>Edge-Browser
-     **Microsoft Edge-Browser (nur mobil):** Erlauben Sie die Verwendung des Edge-Webbrowsers auf dem Gerät.
-     **SmartScreen:** Aktiviert oder deaktiviert den SmartScreen, durch den betrügerische Websites blockiert werden.
-     **DNT-Kopfzeilen senden:** Konfiguriert den Edge-Browser zum Senden von DNT-Headern (Do Not Track, nicht nachverfolgen) an Websites, die Benutzer besuchen.
-     **Cookies:** Erlaubt Browsern das Speichern von Internetcookies auf dem Gerät.
-     **Javascript:** Erlaubt die Ausführung von Skripts wie z.B. JavaScript im Edge-Browser.
-     **Popups:** Blockiert Popupfenster im Browser.<br>(Gilt nur für Windows 10 Desktop.)
-     **Suchvorschläge:** Ermöglicht dem Suchmodul, Websites während der Eingabe von Suchausdrücken vorzuschlagen.
-     **Datenverkehr im Intranet an Internet Explorer senden:** Erlaubt Benutzern, Intranetsites in Internet Explorer zu öffnen. <br>(Nur Windows 10 Desktop)
-     **AutoAusfüllen:** Erlauben Sie Benutzern, die Einstellungen für AutoAusfüllen im Browser zu ändern.<br>(Nur Windows 10 Desktop)
-     **Kennwort-Manager:** Aktivieren oder deaktivieren Sie den Edge-Kennwort-Manager.
-     **Speicherort der Websiteliste für den Unternehmensmodus:** Gibt an, wo Sie die Liste der Websites finden, die im Unternehmensmodus geöffnet werden. Benutzer können diese Liste nicht bearbeiten.<br>(Nur Windows 10 Desktop)
## <a name="cloud-and-storage"></a>Cloud und Speicher
-     **Microsoft-Konto:** Erlaubt dem Benutzer, das Gerät einem Microsoft-Konto zuzuordnen.
-     **Nicht-Microsoft-Konto:** Erlaubt dem Benutzer, dem Gerät E-Mail-Konten hinzuzufügen, die nicht mit einem Microsoft-Konto verknüpft sind.
-     **Synchronisierung der Einstellungen für Microsoft-Konto:** Erlaubt das Synchronisieren der mit einem Microsoft-Konto verknüpften Geräte- und App-Einstellungen zwischen Geräten.
## <a name="cellular-and-connectivity"></a>Mobilfunk und Konnektivität
-     **Datenroaming:** Erlaubt beim Zugriff auf Daten das Roaming zwischen Netzwerken.
-     **VPN über Mobilfunknetz:** Steuert, ob das Gerät auf VPN-Verbindungen zugreifen kann, wenn es mit einem Mobilfunknetz verbunden ist.
-     **VPN-Roaming über Mobilfunknetz:** Steuert, ob das Gerät beim Roaming in einem Mobilfunknetz auf VPN-Verbindungen zugreifen kann.
-     **Bluetooth:** Steuert, ob der Benutzer Bluetooth auf dem Gerät aktivieren und konfigurieren kann.
-     **Bluetooth-Erkennbarkeit:** Ermöglicht die Erkennung dieses Geräts durch andere Bluetooth-Geräte.
-     **Bluetooth-Werbung:** Ermöglicht das Empfangen von Werbung per Bluetooth durch das Gerät.
-     **NFC**: Erlaubt dem Benutzer das Aktivieren und Konfigurieren von Funktionen, die auf dem Gerät Nahfeldkommunikation verwenden.
-     **WLAN:** Erlaubt dem Benutzer das Aktivieren und Konfigurieren von WLAN auf dem Gerät (nur Windows 10 Mobile).
-     **Automatische Verbindung mit WLAN-Hotspots herstellen:** Ermöglicht automatische Verbindungen des Geräts mit unverschlüsselten WLAN-Hotspots und das automatische Akzeptieren der Geschäftsbedingungen für die Verbindung.
-     **Manuelle WLAN-Konfiguration:** Steuert, ob die Benutzer eigene WLAN-Verbindungen konfigurieren dürfen oder ob nur über WLAN-Profile konfigurierte Verbindungen verwendet werden dürfen (nur Windows 10 Mobile).
## <a name="defender"></a>Defender

-     **Echtzeitüberwachung:** Aktiviert die Echtzeitüberwachung auf Schadsoftware, Spyware und andere unerwünschte Software.
-     **Verhaltensüberwachung**: Ermöglicht Defender, Geräte auf bestimmte bekannte Muster verdächtiger Aktivitäten zu überprüfen.
-     **Netzwerkinspektionssystem (NIS)**: Das Netzwerkinspektionssystem (NIS) trägt zum Schutz von Geräten vor netzwerkbasierten Sicherheitslücken bei, indem die Signaturen bekannter Sicherheitsrisiken aus dem Endpoint Protection-Center von Microsoft verwendet werden, um schädlichen Datenverkehr zu erkennen und zu blockieren.
-     **Alle Downloads überprüfen:** Steuert, ob Defender alle aus dem Internet heruntergeladenen Dateien überprüft.
-     **In Microsoft-Webbrowsern geladene Skripts überprüfen:** Ermöglicht Defender die Überprüfung von Skripts, die in Internet Explorer verwendet werden.
-     **Endbenutzerzugriff auf Defender**: Steuert, ob die Benutzeroberfläche von Windows Defender für Endbenutzer ausgeblendet ist.
Wenn diese Einstellung geändert wird, wird die Änderung wirksam, wenn der Endbenutzer-PC das nächste Mal neu gestartet wird.
-     **Intervall für Signaturaktualisierung (in Stunden):** Geben Sie das Intervall an, in dem Defender auf neue Signaturdateien prüfen soll.
-     **Datei- und Programmaktivität überwachen:** Ermöglicht Defender die Überwachung der Datei- und Programmaktivität auf Geräten.
-     **Tage bis zum Löschen von in Quarantäne befindlicher Schadsoftware:** Ermöglicht Defender die fortgesetzte Nachverfolgung behandelter Schadsoftware für die angegebene Anzahl von Tagen, damit Sie zuvor betroffene Geräte manuell überprüfen können. Wenn Sie die Anzahl von Tagen auf **0** festlegen, bleibt Schadsoftware im Quarantäneordner und wird nicht automatisch entfernt.
-     **CPU-Nutzungslimit während einer Überprüfung:** Ermöglicht die Begrenzung der CPU-Nutzung, die bei Überprüfungen genutzt werden darf (von **1** bis **100**).
-     **Archivdateien überprüfen:** Ermöglicht Defender die Überprüfung von Archivdateien wie ZIP- oder CAB-Dateien.
-     **Eingehende E-Mail überprüfen**: Ermöglicht Defender das Überprüfen von E-Mail-Nachrichten beim Eingang auf dem Gerät.
-     **Bei einer vollständigen Überprüfung Wechseldatenträger überprüfen:** Ermöglicht Defender das Überprüfen von Wechseldatenträgern wie USB-Sticks.
-     **Bei einer vollständigen Überprüfung zugeordnete Netzlaufwerke überprüfen:** Ermöglicht Defender das Überprüfen von Dateien auf zugeordneten Netzwerklaufwerken.<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.
-     **Über Netzwerkordner geöffnete Dateien überprüfen:** Ermöglicht Defender das Überprüfen von Dateien auf freigegebenen Netzlaufwerken (z.B. solche, auf die über einen UNC-Pfad zugegriffen wird).
Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.
-     **Cloudschutz:** Erlaubt oder sperrt den Empfang von Informationen über Schadsoftwareaktivitäten der von Ihnen verwalteten Geräten durch den Microsoft Active Protection Service. Diese Informationen werden verwendet, um den Dienst in der Zukunft zu verbessern.
-     **Vor dem Senden von Beispielen bei Benutzern nachfragen:** Steuert, ob die Dateien automatisch an Microsoft gesendet werden, die möglicherweise von Microsoft genauer analysiert werden müssen, um festzustellen, ob sie schädlich sind.
-     **Uhrzeit für die Durchführung einer täglichen Schnellüberprüfung:** Ermöglicht Ihnen die Planung einer Schnellüberprüfung, die täglich zum ausgewählten Zeitpunkt erfolgt.
-     **Art der durchzuführenden Systemüberprüfung:** Ermöglicht die Angabe der Überprüfungsebene für eine geplante Systemüberprüfung.
## <a name="defender-exclusions"></a>Defender-Ausschlüsse

-     **Dateien und Ordner, die bei Überprüfungen und Echtzeitschutz ausgeschlossen werden sollen:** Fügt Dateien und Ordner wie **C:\Pfad** oder **%ProgramFiles%\Pfad\Dateiname.exe** der Ausschlussliste hinzu. Diese Dateien und Ordner werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.
-     **Dateierweiterungen, die bei Überprüfungen und Echtzeitschutz ausgeschlossen werden sollen:** Fügen Sie der Ausschlussliste eine oder mehrere Erweiterungen wie **jpg** oder **txt** hinzu. Dateien mit diesen Erweiterungen werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.
-     **Prozesse, die von Überprüfungen und Echtzeitschutz ausgenommen werden sollen:** Fügen Sie der Ausschlussliste einen oder mehrere Prozesse vom Typ **.exe**, **.com** oder **.scr** hinzu. Diese Prozesse werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.

