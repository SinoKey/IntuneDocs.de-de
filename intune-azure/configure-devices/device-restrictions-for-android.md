---
title: "Einstellungen für Geräteeinschränkungen für Android in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Android-Geräten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 0c3a5ef16da3e2c395cb71a0fc8a23d531cfa02c
ms.contentlocale: de-de
ms.lasthandoff: 05/05/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Standardgeräteeinschränkungen für Android- und Samsung KNOX in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Allgemein

|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Kamera**|Ermöglicht die Verwendung der Gerätekamera.|Ja|Ja|
|**Kopieren und Einfügen**|Ermöglicht Kopier- und Einfügefunktionen auf dem Gerät.|Nein|Ja|
|**Freigabe der Zwischenablage zwischen Apps**|Ermöglicht die Verwendung der Zwischenablage zum Kopieren und Einfügen zwischen Apps.|Nein|Ja|
|**Übermittlung von Diagnosedaten**|Hindert den Benutzer an der Übermittlung von Diagnosedaten vom Gerät|Nein|Ja|
|**Zurücksetzen auf Werkseinstellungen**|Ermöglicht dem Benutzer das Zurücksetzen des Geräts auf die Werkseinstellungen.|Nein|Ja|
|**Geolocation**|Erlaubt dem Gerät die Nutzung von Standortinformationen (nur Samsung KNOX Standard)|Nein|Ja|
|**Ausschalten**|Hiermit wird dem Benutzer das Ausschalten des Geräts gestattet.<br>Wenn diese Einstellung deaktiviert ist, funktioniert die Einstellung **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird** für Samsung KNOX Standard-Geräte nicht.|Nein|Ja|
|**Bildschirmaufnahme**|Ermöglicht dem Benutzer, den Bildschirminhalt als Bild zu erfassen.|Nein|Ja|
|**Sprach-Assistent**|Zulassen der Verwendung von Sprach-Assistent-Software auf dem Gerät.|Nein|Ja|
|**YouTube**|Ermöglicht die Verwendung der YouTube-App auf dem Gerät|Nein|Ja|
|**Freigegebene Geräte**|Konfigurieren Sie ein verwaltetes Samsung KNOX-Standardgerät als freigegeben. In diesem Modus können Endbenutzer sich auf dem Gerät mit ihren Azure AD-Anmeldeinformationen an- und wieder abmelden, und das Gerät wird zentral verwaltet, ob es sich in Gebrauch befindet oder nicht.<br>Wenn sich Endbenutzer anmelden, verfügen Sie über Zugriff auf Apps und erhalten zusätzlich alle Richtlinien, die ihnen zugewiesen sind. Wenn sich Benutzer abmelden, werden alle App-Daten gelöscht.|Nein|Ja|

## <a name="password"></a>Kennwort

|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Passwort**|Der Endbenutzer muss ein Passwort eingeben, um auf das Gerät zugreifen zu können.|Ja|Ja|
|**Minimale Kennwortlänge**|Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort verwenden müssen (zwischen 4 und 16 Zeichen).|Ja|Ja|
|**Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung**|Gibt die Anzahl der inaktiven Minuten an, bevor das Gerät automatisch gesperrt wird.|Ja|Ja|
|**Anzahl von fehlgeschlagenen Anmeldungen, bevor das Gerät zurückgesetzt wird**|Gibt die Anzahl zulässiger Anmeldefehler an, bevor das Gerät zurückgesetzt wird.|Ja|Ja|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|Ja|Ja|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Grad der Kennwortkomplexität an. Zudem wird angegeben, ob biometrische Geräte zulässig sind. Wählen Sie aus:<br><br>    -     **Gerätestandard**<br>-     **Biometrie auf niedriger Sicherheitsstufe**<br>    -     **Mindestens numerisch**<br>    -     **Numerisch komplex** (Sich wiederholende oder fortlaufende Ziffern wie „1111“ oder „1234“ sind nicht zulässig.)<sup>1</sup><br>    -     **Mindestens alphabetisch**<br>    -     **Mindestens alphanumerisch**<br>    -     **Mindestens alphanumerisch mit Symbolen**|Ja|Ja|
|**Wiederverwendung vorheriger Kennwörter verhindern**|Hindert den Endbenutzer daran, ein bereits verwendetes Passwort erneut festzulegen.|Ja|Ja|
|**Fingerabdruckentsperrung**|Erlaubt die Verwendung eines Fingerabdrucks zum Entsperren unterstützter Geräte|Nein|Ja|
|**Smart Lock und andere Vertrauens-Agents**|Ermöglicht die Steuerung des Smart Lock-Features auf kompatiblen Android-Geräten (Samsung KNOX Standard 5.0 und höher). Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für den Gerätesperrbildschirm, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z. B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.|Ja (5.0 und höher)|Nein|
|**Verschlüsselung**|Erfordert die Verschlüsselung der Dateien auf dem Gerät.|Ja|Ja|

<sup>1</sup>Bevor Sie diese Einstellung Geräten zuweisen, stellen Sie sicher, dass die Unternehmensportal-App auf den Zielgeräten auf die neueste Version aktualisiert wurde.

Wenn Sie die Einstellung **Numerisch komplex** konfigurieren und sie dann einem Gerät mit einer früheren Android-Version als 5.0 zuweisen, gilt das folgende Verhalten.
- Wenn die Unternehmensportal-App eine frühere Version als 1704 ausführt, wird keine PIN-Richtlinie auf das Gerät angewendet und eine Fehlermeldung im Intune-Portal angezeigt.
- Wenn die Unternehmensportal-App auf die Version 1704 aktualisiert wurde, wird nur eine einfache PIN angewendet. Frühere Android-Versionen als 5.0 unterstützen diese Einstellung nicht. Es wird keine Fehlermeldung im Intune-Portal angezeigt.


## <a name="google-play-store"></a>Google Play Store

|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Google Play Store**|Ermöglicht dem Benutzer den Zugriff auf den Google Play Store auf dem Gerät|Nein|Ja|

## <a name="restricted-apps"></a>Eingeschränkte Apps

In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:

**Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.
**Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.
Geräteprofile, die Einstellungen für eingeschränkte Apps enthalten, müssen Benutzergruppen zugewiesen werden.

Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Angeben der URL zu einer App im Store

Verwenden Sie zum Festlegen einer App-URL in der Liste kompatibler und nicht kompatibler Apps die folgenden Schritte:

Suchen Sie im [Apps-Bereich von Google Play](https://play.google.com/store/apps) nach der App, die Sie verwenden möchten.

Öffnen Sie die Installationsseite für die App, und kopieren Sie dann die URL in die Zwischenablage. Jetzt können Sie diese als URL in der Liste mit kompatiblen oder nicht kompatiblen Apps verwenden.

Beispiel: Suchen Sie in Google Play nach Microsoft Office Mobile. Die URL, die Sie verwenden, ist **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Zusätzliche Optionen

Sie können auch auf **Importieren** klicken, um die Liste mithilfe einer CSV-Datei im Format <*App-URL*>, <*App-Name*>, <*App-Herausgeber*> aufzufüllen. Sie können auch auf **Exportieren** klicken, um eine CSV-Datei mit dem Inhalt der Liste der eingeschränkten Apps im gleichen Format zu erstellen.        

## <a name="browser"></a>Browser
|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Webbrowser**|Gibt an, ob der Standardwebbrowser des Geräts verwendet werden darf.|Nein|Ja|
|**Automatisch ausfüllen**|Ermöglicht die Verwendung der AutoAusfüllen-Funktion des Webbrowsers.|Nein|Ja|
|**Cookies**|Ermöglicht die Verwendung von Cookies durch den Webbrowser des Geräts.|Nein|Ja|
|**JavaScript**|Erlaubt die Ausführung von Java-Skripts im Webbrowser|Nein|Ja|
|**Popups**|Hiermit wird die Verwendung des Popupblockers im Webbrowser zugelassen.|Nein|Ja|

## <a name="cloud-and-storage"></a>Cloud und Speicher
|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Google-Sicherung**|Ermöglicht die Verwendung der Google-Sicherung.|Nein|Ja|
|**Automatische Synchronisierung mit Google-Konto**|Ermöglicht die automatische Synchronisierung der Einstellungen von Google-Konten.|Nein|Ja|
|**Wechselmedien**|Ermöglicht dem Gerät die Verwendung von Wechselmedien, z. B. SD-Karten.|Nein|Ja|
|**Verschlüsselung auf Speicherkarten**|Gibt an, ob die Gerätespeicherkarte verschlüsselt werden muss.|Nein|Ja|

## <a name="cellular-and-connectivity"></a>Mobilfunk und Konnektivität
|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Datenroaming**|Ermöglicht das Datenroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird|Nein|Ja|
|**SMS/MMS-Messaging**|Ermöglicht die Verwendung von SMS- und MMS-Nachrichten auf dem Gerät.|Nein|Ja|
|**Sprachwahlverfahren**|Aktiviert oder deaktiviert die Verwendung des Features „Sprachwahlverfahren“ auf dem Gerät.|Nein|Ja|
|**Sprachroaming**|Ermöglicht das Sprachroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Nein|Ja|
|**Bluetooth**|Hiermit wird die Verwendung von Bluetooth auf dem Gerät zugelassen.|Nein|Ja|
|**NFC**|Erlaubt Vorgänge, die NFC (Near Field Communication) verwenden, sofern dies vom Gerät unterstützt wird.|Nein|Ja|
|**WLAN**|Ermöglicht die Verwendung der WLAN-Funktionen des Geräts.|Nein|Ja|
|**WLAN-Tethering**|Ermöglicht die Verwendung des WLAN-Tetherings auf dem Gerät.|Nein|Ja|

## <a name="kiosk"></a>Kiosk
|||||
|-|-|-|-|
|Name der Einstellung|Details|Android 4.0+|Samsung KNOX Standard|
|**Verwaltete App auswählen**|Wählen Sie die verwaltete App aus, die ausgeführt werden kann, wenn sich das Gerät im Kioskmodus befindet (Apps, die als Link zum Store angegeben sind, werden derzeit nicht unterstützt). Andere Apps dürfen auf dem Gerät nicht ausgeführt werden.|Nein|Ja|
|**Schaltfläche für Standby des Bildschirms**|Aktiviert oder deaktiviert die Taste für Standby/Aktivierung des Bildschirms am Gerät.|Nein|Ja|
|**Lautstärkeregler**|Aktiviert oder deaktiviert die Verwendung der Lautstärkeregler am Gerät.|Nein|Ja |

