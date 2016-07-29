---
title: "Sicherheitsrichtlinieneinstellungen für mobile Geräte | Microsoft Intune"
description: "Verwenden Sie Intune, um eine Vielzahl von Einstellungen zu konfigurieren, die Sie für verwaltete Geräte in Ihrer Organisation bereitstellen können."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 648cc02b47682a58195ee927560763818b6d32ac


---

# Sicherheitsrichtlinieneinstellungen für mobile Geräte in Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune bietet jetzt getrennte Konfigurationsrichtlinien für jede Geräteplattform, wobei diese Richtlinien die neuesten Einstellungen berücksichtigen, die Sie verwenden können. Sie können die Sicherheitsrichtlinie für mobile Geräte weiter nutzen, wobei alle vorhandenen Bereitstellungen weiterhin funktionieren. Sie sollten allerdings die Migration zu den neuen Konfigurationsrichtlinien so bald wie möglich planen, da die Sicherheitsrichtlinie für mobile Geräte in Zukunft entfernt werden wird.

Verwenden Sie Intune-Sicherheitsrichtlinien für mobile Geräte, um eine Vielzahl von Einstellungen zu konfigurieren, die Sie für verwaltete Geräte in Ihrer Organisation bereitstellen können. Diese Einstellungen können verwendet werden, um die Funktionalität und die Sicherheit Ihrer Geräte zu steuern.

Sie können die Sicherheitsrichtlinien für mobile Geräte für die folgenden Gerätetypen erstellen und bereitstellen:

-   Windows RT 8.1-Geräte und registrierte Windows 8.1-Geräte

-   Windows RT

-   Windows Phone 8 und Windows Phone 8.1

-   iOS

-   Android und Samsung KNOX

> [!NOTE]
> Einige Einstellungen sind auf einigen Geräten nicht anwendbar. In der nachfolgenden Tabelle finden Sie eine vollständige Liste der Einstellungen, die Sie konfigurieren können.

## Sicherheitseinstellungen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Nein|Nein|Ja|Ja|Ja|
|**Erforderlicher Kennworttyp**<br /><br />(gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch)|Ja|Ja|Ja|Ja|Nein|
|**Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen**<br /><br />Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen. Für iOS-Geräte wird hiermit jedoch die erforderliche Anzahl von Symbolzeichen im Kennwort angegeben.|Ja|Ja|Ja|Ja|Nein|
|**Minimale Kennwortlänge**|Ja|Ja|Ja|Ja|Ja|
|**Einfache Kennwörter zulassen**<br /><br />Einfache Kennwörter enthalten '0000' und '1234'.|Nein|Nein|Ja|Ja|Nein|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Ja|Ja|Ja|Ja|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**<sup>1</sup>|Ja|Ja|Ja|Ja|Ja|
|**Kennwortablauf (Tage)**|Ja|Ja|Ja|Ja|Ja|
|**Kennwortverlauf speichern**|Ja|Ja|Ja|Ja|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Ja|Ja|Ja|Ja|Ja|
|**Kennwortqualität**|Nein|Nein|Nein|Nein|Ja|
|**Bildkennwort und PIN zulassen**|Ja|Ja|Nein|Nein|Nein|
|**Minuten der Inaktivität, bevor ein Kennwort erforderlich ist**|Nein|Nein|Nein|Ja|Nein|
|**Fingerabdruckentsperrung zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
Wenn Sie für iOS-Geräte die Einstellungen **Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird** und **Minuten Inaktivität vor erneuter Anforderung des Kennworts** konfigurieren, werden sie nacheinander angewendet. Wenn Sie beispielsweise den Wert für beide Einstellungen auf **5** Minuten einstellen, wird der Bildschirm automatisch nach 5 Minuten deaktiviert, und das Gerät wird nach weiteren 5 Minuten gesperrt. Wenn der Benutzer den Bildschirm jedoch manuell deaktiviert, wird die zweite Einstellung sofort angewendet. Im selben Beispiel wird das Gerät 5 Minuten später gesperrt, nachdem der Benutzer den Bildschirm deaktiviert hat.

Wenn Sie eine Kennwortlängenrichtlinie für Geräte mit Windows RT bereitstellen, müssen Benutzer ihr Kennwort zurücksetzen, selbst wenn ihr aktuelles Kennwort den Richtlinienanforderungen entspricht.

## Verschlüsselungseinstellungen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Verschlüsselung auf mobilem Gerät anfordern**<sup>1</sup><br /><br />Für Windows Phone 8-Geräte müssen Sie hier **Ja**festlegen.<br /><br />Aktivieren Sie zum Verwenden der Verschlüsselung auf iOS-Geräten die Einstellung **Kennwort zum Entsperren mobiler Geräte erforderlich**.|Ja|Nein|Ja|Nein|Ja|
|**Verschlüsselung auf Speicherkarten vorschreiben**<br /><br />Gilt auch für Geräte, die mit Exchange ActiveSync verwaltet werden.|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend (Apps und zugehörige Daten werden automatisch verschlüsselt)|Nicht zutreffend|Ja|
Zusätzliche Informationen für Geräte die Windows 8.1 ausführen

-   Um die Verschlüsselung auf Geräten zu erzwingen, die Windows 8.1 ausführen, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](http://support.microsoft.com/kb/3013816) auf jedem Gerät.

-   Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.

-   Damit die Verschlüsselung funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) erfüllen.

-   Wenn Sie die Verschlüsselung auf einem Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich, auf das dieser über sein eigenes OneDrive-Konto zugreift. Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.

## Malwareeinstellungen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Netzwerkfirewall erforderlich**|Ja|Nein|Nein|Nein|Nein|
|**SmartScreen aktivieren**|Ja|Nein|Nein|Nein|Nein|

## Systemeinstellungen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Automatische Updates erforderlich**|Ja|Nein|Nein|Nein|Nein|
|**Automatische Updates erforderlich – Mindestklassifizierung von Updates, die automatisch installiert werden**<br /><br />Wählen Sie die Klassifizierungen der Updates, die automatisch installiert werden:<br /><br />**Wichtig**: Installiert alle Updates, die als wichtig klassifiziert sind.<br /><br />**Empfohlen**: Installiert alle Updates, die als wichtige oder empfohlene klassifiziert sind.|Ja|Nein|Nein|Nein|Nein|
|**Bildschirmaufnahme zulassen**|Nein|Nein|Nur Windows Phone 8.1|Ja|Ja (nur Samsung KNOX)|
|**Kontrollcenter auf Sperrbildschirm zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
|**Benachrichtigungsansicht auf Sperrbildschirm zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
|**Ansicht "Heute" auf Sperrbildschirm zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
|**Benutzerkontensteuerung**|Ja|Nein|Nein|Nein|Nein|
|**Übermitteln von Diagnosedaten zulassen**|Ja|Nein|Nur Windows Phone 8.1|Ja|Ja (nur Samsung KNOX)|
|**Nicht vertrauenswürdige TLS-Zertifikate zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Persönliche Wallet-Software während Sperrung zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Zurücksetzen auf Werkseinstellungen zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|


## Cloudeinstellungen – Dokumente und Daten

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sicherung in iCloud zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Dokumentsynchronisierung in iCloud zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Photo Stream-Synchronisierung in iCloud zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Verschlüsselte Sicherung erforderlich**|Nein|Nein|Nein|Ja|Nein|
|**URL der Arbeitsordner**<br /><br />(legt die URL des Arbeitsordners so fest, dass Dokumente auf verschiedenen Geräten synchronisiert werden können)|Ja|Nein|Nein|Nein|Nein|
|**Google-Sicherung zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|

## Cloudeinstellungen – Konten und Synchronisierung

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft-Konto erlauben**|Nein|Nein|Nur Windows Phone 8.1|Nein|Nein|
|**Automatische Synchronisierung mit Google-Konto zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|

## E-Mail-Einstellungen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Herunterladen von E-Mail-Anhängen für Benutzer zulassen**<sup>1</sup>|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|
|**Synchronisierungszeitraum für E-Mail** Gilt auch für Geräte, die mit Exchange ActiveSync verwaltet werden.|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|
|**Synchronisierung mit Exchange (Exchange ActiveSync) für mobile Geräte zulassen, die diese Einstellungen nicht vollständig unterstützen** Gilt auch für Geräte, die mit Exchange ActiveSync verwaltet werden.|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|
|**Microsoft-Konto in Windows Mail-Anwendung optional machen**|Ja|Nein|Nein|Nein|Nein|
|**Benutzerdefinierte E-Mail-Konten erlauben**|Nein|Nein|Nur Windows Phone 8.1|Nein|Nein|

## Anwendungseinstellungen – Browser

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Webbrowser zulassen**|Nein|Nein|Nur Windows Phone 8.1|Ja|Ja (nur Samsung KNOX)|
|**AutoAusfüllen zulassen**|Ja|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Popupblocker zulassen**|Ja|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Cookies zulassen**|Nein|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Plug-Ins zulassen**|Ja|Nein|Nein|Nein|Nein|
|**Active Scripting zulassen**|Ja|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Betrugswarnung zulassen**|Ja|Nein|Nein|Ja|Nein|
|**Wechsel zu Intranetsite nach Eingabe eines einzelnen Worts zulassen**<br /><br />(erlaubt die Verwendung eines einzelnen Wortes, um Internet Explorer auf eine Website wie "Bing" weiterzuleiten)|Ja|Nein|Nein|Nein|Nein|
|**Automatische Erkennung des Intranets zulassen**|Ja|Nein|Nein|Nein|Nein|
|**Sicherheitsstufe für Internet**|Ja|Nein|Nein|Nein|Nein|
|**Sicherheitsstufe für Intranet**|Ja|Nein|Nein|Nein|Nein|
|**Sicherheitsstufe für vertrauenswürdige Sites**|Ja|Nein|Nein|Nein|Nein|
|**Sicherheitsstufe für eingeschränkte Sites**|Ja|Nein|Nein|Nein|Nein|
|**Header "Nicht nachverfolgen" senden**|Ja|Nein|Nein|Nein|Nein|
|**Menüzugriff im Enterprise-Modus erlauben**|Ja|Nein|Nein|Nein|Nein|
|**Ort der Standortliste für Enterprise-Modus**|Ja|Nein|Nein|Nein|Nein|

## Anwendungseinstellungen – Apps

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**App Store zulassen**|Nein|Nein|Nur Windows Phone 8.1|Ja|Ja (nur Samsung KNOX)|
|**Kennwort für den Zugriff auf den Anwendungsspeicher erforderlich**|Nein|Nein|Nein|Ja|Nein|
|**In-App-Einkäufe zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Verwaltete Dokumente in anderen nicht verwalteten Apps zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
|**Nicht verwaltete Dokumente in anderen verwalteten Apps zulassen**|Nein|Nein|Nein|iOS 7 und höher|Nein|
|**Videokonferenz zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Nicht jugendfreie Inhalte im Medienstore zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Anwendungsinstallation zulassen**|Nein|Nein|Nein|iOS 6 und höher|Nein|

## Anwendungseinstellungen – Spiele

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Center-Freunde zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Spielen für mehrere Spieler zulassen**|Nein|Nein|Nein|Ja|Nein|

## Einstellungen für Gerätefunktionen - Hardware

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kamera zulassen**|Nein|Nein|Nur Windows Phone 8.1|Ja|Ja|
|**Wechselspeichermedien zulassen**|Nein|Nein|Ja|Nein|Ja (nur Samsung KNOX)|
|**WLAN zulassen**|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**WLAN-Tethering zulassen**|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Nein|Nein|Nur Windows Phone 8.1|Nein|Nein|
|**Berichterstellung für WLAN-Hotspots zulassen**<br /><br />(Informationen über WLAN-Verbindungen senden, um nahegelegene Verbindungen zu ermitteln)|Nein|Nein|Nur Windows Phone 8.1|Nein|Nein|
|**Geolocation zulassen**<br /><br />(erlaubt dem Gerät die Nutzung von Standortinformationen)|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**NFC zulassen**<br /><br />(erlaubt Vorgänge, die NFC bzw. Near Field Communication verwenden)|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**Bluetooth zulassen**|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**Ausschalten zulassen**<br>Wenn diese Einstellung deaktiviert ist, funktioniert die Einstellung **Anzahl der zulässigen wiederholten Anmeldefehler, bevor die Gerätedaten zurückgesetzt werden** für Samsung KNOX-Geräte nicht.|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|

## Einstellungen für Gerätefunktionen - Mobiltelefon

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sprachroaming zulassen**|Nein|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Datenroaming zulassen**|Ja|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Automatische Synchronisierung beim Roaming zulassen**|Nein|Nein|Nein|Ja|Nein|
|**SMS/MMS-Messaging zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|

## Einstellungen für Gerätefunktionen - Funktionen

|Name der Einstellung|Windows 8.1 und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|iOS|Android und Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sprach-Assistent zulassen**|Nein|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Sprach-Assistent bei gesperrtem Gerät zulassen**|Nein|Nein|Nein|Ja|Nein|
|**Sprachwahl zulassen**|Nein|Nein|Nein|Ja|Ja (nur Samsung KNOX)|
|**Kopieren und Einfügen zulassen**|Nein|Nein|Nur Windows Phone 8.1|Nein|Ja (nur Samsung KNOX)|
|**Freigabe der Zwischenablage zwischen Anwendungen zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|
|**YouTube zulassen**|Nein|Nein|Nein|Nein|Ja (nur Samsung KNOX)|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


