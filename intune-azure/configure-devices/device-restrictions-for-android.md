---
title: "Intune-Einstellungen für Geräteeinschränkungen für Android | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Android-Geräten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Einstellungen für Geräteeinschränkungen für Android- und Samsung KNOX Standard in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Allgemein
-   **Kamera:** Erlaubt die Verwendung der Gerätekamera.
-   **Kopieren und einfügen:** Lässt Kopier- und Einfügefunktionen auf dem Gerät zu oder sperrt diese Funktionen.
-   **Gemeinsame Nutzung der Zwischenablage durch Apps:** Erlaubt die Verwendung der Zwischenablage für das Kopieren und Einfügen zwischen Apps (nur Samsung KNOX Standard).
-   **Übermittlung von Diagnosedaten:** Hindert den Benutzer an der Übermittlung von Diagnosedaten vom Gerät.    
-   **Zurücksetzung auf Werkseinstellungen:** Erlaubt dem Benutzer das Zurücksetzen des Geräts auf die Werkseinstellungen.
-   **Geolocation:** Erlaubt dem Gerät die Nutzung von Standortinformationen (nur Samsung KNOX Standard).
-   **Ausschalten:** Erlaubt dem Benutzer das Ausschalten des Geräts.<br>Wenn diese Einstellung deaktiviert ist, funktioniert die Einstellung **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird** für Samsung KNOX Standard-Geräte nicht.
-   **Bildschirmaufnahme:** Erlaubt dem Benutzer, den Bildschirminhalt als Bild zu erfassen.
-   **Sprach-Assistent:** Erlaubt die Verwendung von Sprach-Assistent-Software auf dem Gerät (nur Samsung KNOX Standard).
-   **YouTube:** Erlaubt die Verwendung der YouTube-App auf dem Gerät (nur Samsung KNOX Standard).

## <a name="password"></a>Kennwort
-   **Kennwort erforderlich:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
-   **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort festlegen müssen (zwischen 4 und 16 Zeichen).
-   **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt die Anzahl der Minuten der Inaktivität an, bevor das Gerät automatisch gesperrt wird.
-   **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Gibt die Anzahl zulässiger Anmeldefehler an, bevor das Gerät zurückgesetzt wird.
-   **Kennwortablauf (Tage):** Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.
-   **Erforderlicher Kennworttyp:** Gibt den erforderlichen Grad der Kennwortkomplexität an. Zudem wird angegeben, ob biometrische Geräte zulässig sind.
-   **Wiederverwendung vorheriger Kennwörter verhindern:** Hindert den Endbenutzer daran, ein bereits verwendetes Kennwort erneut festzulegen.
-   **Entsperrung durch Fingerabdruck:** Erlaubt die Verwendung eines Fingerabdrucks zum Entsperren unterstützter Geräte.
-   **Smart Lock und andere Vertrauens-Agents:** Ermöglicht die Steuerung des Smart Lock-Features auf kompatible Android-Geräten (Samsung KNOX Standard 5.0 und höher). Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für den Gerätesperrbildschirm, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z. B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.
-   **Verschlüsselung:** Schreibt vor, dass die Dateien auf den Geräten verschlüsselt werden müssen.

## <a name="google-play-store"></a>Google Play Store

-   **Google Play Store:** Erlaubt dem Benutzer den Zugriff auf den Google Play Store auf dem Gerät (nur Samsung KNOX Standard).

## <a name="restricted-apps"></a>Eingeschränkte Apps

In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:

**Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.
**Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.
Geräteprofile, die Einstellungen für eingeschränkte Apps enthalten, müssen für Benutzergruppen bereitgestellt werden.

Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Angeben der URL zu einer App im Store

Verwenden Sie zum Festlegen einer App-URL in der Liste kompatibler und nicht kompatibler Apps die folgenden Schritte:

Suchen Sie im [Apps-Bereich von Google Play](https://play.google.com/store/apps) nach der App, die Sie verwenden möchten.

Öffnen Sie die Installationsseite für die App, und kopieren Sie dann die URL in die Zwischenablage. Jetzt können Sie diese als URL in der Liste mit kompatiblen oder nicht kompatiblen Apps verwenden.

Beispiel: Suchen Sie in Google Play nach Microsoft Office Mobile. Die URL, die Sie verwenden, ist **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Zusätzliche Optionen

Sie können auch auf **Importieren** klicken, um die Liste mithilfe einer CSV-Datei im Format <*App-URL*>, <*App-Name*>, <*App-Herausgeber*> aufzufüllen. Sie können auch auf **Exportieren** klicken, um eine CSV-Datei mit dem Inhalt der Liste der eingeschränkten Apps im gleichen Format zu erstellen.      

## <a name="browser"></a>Browser
-   **Webbrowser:** Gibt an, ob der Standardwebbrowser des Geräts verwendet werden darf.
-   **AutoAusfüllen:** Erlaubt die Verwendung der AutoAusfüllen-Funktion des Webbrowsers.
-   **Cookies:** Erlaubt die Verwendung von Cookies durch den Webbrowser des Geräts.
-   **Javascript:** Erlaubt die Ausführung von Java-Skripts im Webbrowser.
-   **Popups:** Erlaubt die Verwendung des Popupblockers im Webbrowser.

## <a name="cloud-and-storage"></a>Cloud und Speicher
-   **Google-Sicherung:** Erlaubt die Verwendung der Google-Sicherung.
-   **Automatische Google-Kontosynchronisierung:** Erlaubt die automatische Synchronisierung der Einstellungen von Google-Konten.
-   **Wechselmedien:** Erlaubt dem Gerät Wechselmedien wie SD-Karten zu verwenden (nur Samsung KNOX Standard).
-   **Verschlüsselung auf Speicherkarten:** Gibt an, ob die Gerätespeicherkarte verschlüsselt werden muss.

## <a name="cellular-and-connectivity"></a>Mobilfunk und Konnektivität
-   **Datenroaming:** Erlaubt das Datenroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird (nur Samsung KNOX Standard).
-   **SMS-/MMS-Nachrichten:** Erlaubt die Verwendung von SMS und MMS-Nachrichten auf dem Gerät (nur Samsung KNOX Standard).
-   **Sprachwahlverfahren:** Aktiviert oder deaktiviert die Sprachwahlfunktion auf dem Gerät (nur Samsung KNOX Standard).
-   **Sprachroaming:** Erlaubt das Sprachroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird (nur Samsung KNOX Standard).
-   **Bluetooth:** Erlaubt die Verwendung von Bluetooth auf dem Gerät (nur Samsung KNOX Standard).
-   **NFC:** Erlaubt Vorgänge, die NFC (Near Field Communication, Nahfeldkommunikation) verwenden, sofern dies vom Gerät unterstützt wird (nur Samsung KNOX Standard).
-   **WLAN:** Erlaubt die Verwendung der WLAN-Funktionen des Geräts (nur Samsung KNOX Standard).
-   **WLAN-Tethering:** Erlaubt die Verwendung von WLAN-Tethering auf dem Gerät (nur Samsung KNOX Standard).

## <a name="kiosk"></a>Kiosk
-   **Verwaltete App auswählen:** Wählen Sie die verwaltete App aus, die ausgeführt werden kann, wenn sich das Gerät im Kioskmodus befindet (Apps, die als Link zum Store angegeben sind, werden derzeit nicht unterstützt). Andere Apps dürfen auf dem Gerät nicht ausgeführt werden.
-   **Standbytaste:** Aktiviert oder deaktiviert die Standbytaste am Gerät.
-   **Lautstärketasten** – Aktiviert oder deaktiviert die Verwendung der Lautstärketasten am Gerät.



<!--HONumber=Feb17_HO1-->


