---
title: "Einstellungen für Windows-Richtlinien | Microsoft Intune"
description: "Verwenden Sie die allgemeine Windows-Konfigurationsrichtlinie (Windows 8.1 und höher) von Intune, um Einstellungen für registrierte Windows 8- und Windows 8.1-Geräte zu konfigurieren:"
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 809c8dc87e9b7c2f27e8015a55606e376c5319ab


---

# Einstellungen für Windows-Richtlinien in Microsoft Intune
Verwenden Sie die **allgemeine Windows-Konfigurationsrichtlinie (Windows 8.1 und höher)** von Microsoft Intune, um die folgenden Einstellungen für registrierte Windows 8- und Windows 8.1-Geräte zu konfigurieren:

## Anwendbarkeitseinstellungen

|Name der Einstellung|Details|
|----------------|----------------------------------|
|**Alle Konfigurationen auf Windows 10 anwenden**|Erlaubt, dass Einstellungen in dieser Richtlinie zusätzlich zu Windows 8- und Windows 8.1-Geräten auf Windows 10-Geräte angewendet werden.|

## Sicherheitseinstellungen

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|Ja|Ja|
|**Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen. Für iOS-Geräte wird hiermit jedoch die erforderliche Anzahl von Symbolzeichen im Kennwort angegeben.|Ja|Ja|
|**Minimale Kennwortlänge**<sup>1</sup>|Konfiguriert die erforderliche Mindestlänge (in Zeichen) für das Kennwort auf Geräten.|Ja|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Setzt das Gerät zurück, wenn die angegebene Anzahl fehlgeschlagener Anmeldeversuche erreicht ist.|Ja|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Wählen Sie die Anzahl von Minuten aus, die ein Gerät im Leerlauf sein muss, bevor ein Kennwort zum Entsperren erforderlich ist.| Ja|Ja|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|Ja|Ja|
|**Kennwortverlauf speichern**|Gibt an, ob der Benutzer zuvor verwendete Kennwörter konfigurieren kann.|Ja|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|Ja|Ja|
|**Bildkennwort und PIN zulassen**|Ermöglicht die Verwendung eines Bildkennworts und einer PIN auf dem Gerät. Mit einem Bildkennwort kann sich der Benutzer mit Gesten auf einem Bild anmelden. Mit einer PIN kann sich der Benutzer mit einem vierstelligen Code schnell anmelden.|Ja|Ja|
<sup>1</sup> Wenn Sie eine Kennwortlängenrichtlinie für Geräte unter Windows RT bereitstellen, müssen Benutzer ihr Kennwort zurücksetzen, selbst wenn ihr aktuelles Kennwort den Richtlinienanforderungen entspricht.

## Verschlüsselungseinstellungen

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Verschlüsselung auf mobilen Geräten vorschreiben**<sup>1</sup>|Erfordert die Verschlüsselung der Dateien auf dem Gerät.<br>Für Windows Phone 8-Geräte müssen Sie hier **Ja**festlegen.|Ja|Nein|
<sup>1</sup> Zusätzliche Informationen für Geräte unter Windows 8.1

-   Um die Verschlüsselung auf Geräten zu erzwingen, die Windows 8.1 ausführen, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](http://support.microsoft.com/kb/3013816) auf jedem Gerät.

-   Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.

-   Damit die Verschlüsselung funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) erfüllen.

-   Wenn Sie die Verschlüsselung auf einem Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich, auf das dieser über sein eigenes OneDrive-Konto zugreift. Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.

## Malwareeinstellungen

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Netzwerkfirewall erforderlich**|Legen Sie fest, dass die Windows-Firewall aktiviert sein muss.|Ja|Nein|
|**SmartScreen aktivieren**|Legen Sie fest, dass Windows SmartScreen auf Geräten verwendet werden muss.|Ja|Nein|

## Systemeinstellungen

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Automatische Updates erforderlich**|Aktivieren Sie die Einstellung für automatische Updates auf Geräten.|Ja|Nein|
|**Automatische Updates erforderlich – Mindestklassifizierung von Updates, die automatisch installiert werden**|Wählen Sie die Klassifizierungen der Updates, die automatisch installiert werden:<br /><br />-   **Wichtig**: Installiert alle Updates, die als wichtig klassifiziert sind.<br />-   **Empfohlen**: Installiert alle Updates, die als wichtige oder empfohlene klassifiziert sind.|Ja|Nein|
|**Benutzerkontensteuerung**|Legen Sie fest, dass die Benutzerkontensteuerung (User Account Control, UAC) auf Geräten verwendet werden muss.|Ja|Nein|
|**Übermitteln von Diagnosedaten zulassen**|Lassen Sie zu, dass das Gerät Diagnoseinformationen an Microsoft übermittelt.|Ja|Nein|


## Cloudeinstellungen – Dokumente und Daten

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**URL der Arbeitsordner**|Legt die URL des Arbeitsordners so fest, dass Dokumente auf verschiedenen Geräten synchronisiert werden können.|Ja|Nein|

## E-Mail-Einstellungen

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Microsoft-Konto in Windows Mail-Anwendung optional machen**|Hiermit wird der Zugriff auf die Windows Mail-Anwendung ohne Microsoft-Konto zugelassen.|Ja|Nein|

## Anwendungseinstellungen – Browser

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**AutoAusfüllen zulassen**|Benutzer können die Einstellungen für AutoVervollständigen im Browser ändern.|Ja|Nein|
|**Popupblocker zulassen**|Aktiviert oder deaktiviert den Popupblocker des Browsers.|Ja|Nein|
|**Plug-Ins zulassen**|Benutzer können Plug-Ins zu Internet Explorer hinzufügen.|Ja|Nein|
|**Active Scripting zulassen**|Browser können Skripts ausführen, z. B. ActiveX-Skripts.|Ja|Nein|
|**Betrugswarnung zulassen**|Aktivieren oder deaktivieren von Warnungen zu potenziell betrügerischen Websites.|Ja|Nein|
|**Wechsel zu Intranetsite nach Eingabe eines einzelnen Worts zulassen**|Lässt die Verwendung eines einzelnen Worts zu, um Internet Explorer auf eine Website wie „Bing“ weiterzuleiten.|Ja|Nein|
|**Automatische Erkennung des Intranets zulassen**|Hilft bei der Konfiguration der Sicherheit für Intranetsites in Internet Explorer.|Ja|Nein|
|**Sicherheitsstufe für Internet**|Legen Sie die Internet Explorer-Sicherheitsstufe für Internetsites fest.|Ja|Nein|
|**Sicherheitsstufe für Intranet**|Legen Sie die Internet Explorer-Sicherheitsstufe für Intranetsites fest.|Ja|Nein|
|**Sicherheitsstufe für vertrauenswürdige Sites**|Konfigurieren Sie die Sicherheitsstufe für die Zone vertrauenswürdiger Sites.|Ja|Nein|
|**Sicherheitsstufe für eingeschränkte Sites**|Konfigurieren Sie die Sicherheitsstufe für Zone eingeschränkter Sites.|Ja|Nein|
|**Header "Nicht nachverfolgen" senden**|Hiermit wird in Internet Explorer ein DNT-Header (Do Not Track, nicht nachverfolgen) an besuchte Websites gesendet.|Ja|Nein|
|**Menüzugriff im Enterprise-Modus erlauben**|Ermöglicht dem Benutzer, auf die Menüoptionen für den Unternehmensmodus von Internet Explorer zuzugreifen.<br>Wenn diese Einstellung ausgewählt ist, können Sie auch einen **Speicherort des Protokollberichts** angeben. Dieser enthält eine URL zu einem Bericht, in dem Websites angezeigt werden, für die Benutzer Zugriff im Unternehmensmodus aktiviert haben.|Ja|Nein|
|**Ort der Standortliste für Enterprise-Modus**|Geben Sie den Speicherort der Liste der Websites an, die den Unternehmensmodus verwenden, wenn er aktiv ist.|Ja|Nein|

## Einstellungen für Gerätefunktionen - Mobiltelefon

|Name der Einstellung|Details|Windows 8.1 und Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Datenroaming zulassen**|Zulassen des Datenroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Ja|Nein|



### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


