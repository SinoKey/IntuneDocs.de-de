---
title: "Einstellungen für Exchange ActiveSync-Richtlinien | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: 7ab9c5f283f65c82e1713d29923fa16a6a542352


---

# Einstellungen für Exchange ActiveSync-Richtlinien in Microsoft Intune
Verwenden Sie die Microsoft Intune **Exchange ActiveSync**-Richtlinie, um Einstellungen zu konfigurieren, mit denen Sie eine Reihe von Features und Funktionen auf Geräten steuern können, die von Exchange ActiveSync verwaltet werden.


## Kennworteinstellungen

|Name der Einstellung|Details
|----------------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Gibt an, ob Geräte mithilfe eines Kennworts gesperrt werden müssen.<br>(dies trifft nicht auf Geräte zu, auf denen Windows RT ausgeführt wird)|
|**Erforderlicher Kennworttyp**|Gibt den Typ des erforderlichen Kennworts an, z. B. nur numerisch oder alphanumerisch.|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Gerätekennwort enthalten muss.|
|**Einfache Kennwörter zulassen**|Einfache Kennwörter sind z. B. '0000' und '1234'.|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Erlaubt die angegebene Anzahl Versuche zur Eingabe eines richtigen Kennworts, bevor das Gerät zurückgesetzt wird.|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, nach denen das Gerätekennwort geändert werden muss.
|**Kennwortverlauf speichern**|Gibt an, ob dem Benutzer zuvor bereits verwendete Kennwörter erlaubt werden sollen.|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt die Anzahl der zuvor bereits verwendeten Kennwörter an, die nicht erneut verwendet werden können.|
|**Minuten der Inaktivität, bevor ein Kennwort erforderlich ist**|Gibt den Zeitraum an, für den sich das Gerät im Leerlauf befinden muss, bevor der Bildschirm gesperrt wird.

## Verschlüsselungseinstellungen

|Name der Einstellung|Details|
|----------------|
|**Verschlüsselung auf mobilem Gerät anfordern**<sup>1</sup>|Schreibt auf Geräten die Verschlüsselung der Daten vor, um die Unterstützung zuzulassen.<br>Für Windows Phone 8-Geräte müssen Sie hier **Ja**festlegen.<br /><br />Aktivieren Sie zum Verwenden der Verschlüsselung auf iOS-Geräten die Einstellung **Kennwort zum Entsperren mobiler Geräte erforderlich**.|
|**Verschlüsselung auf Speicherkarten vorschreiben**|Schreibt die Verschlüsselung von Daten vor, die auf externen Speichern, wie etwa SD-Karten, gespeichert sind (auf unterstützten Geräten).
<sup>1</sup> Zusätzliche Informationen für Geräte, die Windows 8.1 ausführen

-   Um die Verschlüsselung auf Geräten zu erzwingen, die Windows 8.1 ausführen, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](http://support.microsoft.com/kb/3013816) auf jedem Gerät.

-   Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.

-   Damit die Verschlüsselung funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) erfüllen.

-   Wenn Sie die Verschlüsselung auf einem Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich, auf das dieser über sein eigenes OneDrive-Konto zugreift. Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.

## E-Mail-Einstellungen

|Name der Einstellung|Details
|----------------|
|**Herunterladen von E-Mail-Anhängen für Benutzer zulassen**|Gibt an, ob E-Mail-Anlagen auf das Gerät heruntergeladen werden können.|
|**Synchronisierungszeitraum für E-Mail**|Gibt die Anzahl der Tage an, für die empfangene E-Mails auf das Gerät synchronisiert werden.
|**Synchronisierung mit Exchange ActiveSync für mobile Geräte zulassen, die diese Einstellungen nicht vollständig unterstützen**|Gibt an, ob Exchange der Zugriff auf Geräte erlaubt wird, die eine oder mehrere Exchange ActiveSync-Einstellungen nicht unterstützen.

## Browsereinstellungen

|Name der Einstellung|Details
|----------------|-
|**Webbrowser zulassen**|Gibt an, ob der Webbrowser des Geräts verwendet werden darf.<br>(für Windows 8.1 oder Windows Phone 8.1 nicht verfügbar).

## Hardware-Einstellungen

|Name der Einstellung|Details
|----------------|
|**Kamera zulassen**|Gibt an, ob die Kamera des Geräts verwendet werden darf.<br>(für Windows 8.1 oder Windows Phone 8.1 nicht verfügbar).



### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


