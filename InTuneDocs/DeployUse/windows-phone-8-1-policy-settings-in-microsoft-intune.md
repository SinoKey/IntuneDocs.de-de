---
title: "Einstellungen für Windows Phone 8.1-Richtlinien | Microsoft Intune"
description: "Intune bietet eine Auswahl von integrierten allgemeinen Einstellungen, die Sie auf Windows Phone 8.1-Geräten konfigurieren können. Darüber hinaus können Sie OMA-URI-Werte angeben, um benutzerdefinierte Einstellungen zu erstellen, die über Intune nicht verfügbar sind."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4279ecd098ddaa6d6eb239ee71f9c3f7d450ab3f
ms.openlocfilehash: f2ccc52ceae6bbb63ea76ff4391922099c69f4dd


---

# Einstellungen für Windows Phone 8.1-Richtlinien in Microsoft Intune

Intune bietet eine Auswahl von integrierten allgemeinen Einstellungen, die Sie auf Windows Phone 8.1-Geräten konfigurieren können. Darüber hinaus können Sie OMA-URI-Werte (Open Mobile Alliance Uniform Resource Identifier) angeben, um benutzerdefinierte Einstellungen zu erstellen, die über Intune nicht verfügbar sind.

## Allgemeine Konfigurationseinstellungen

Konfigurieren Sie mithilfe der **allgemeinen Windows Phone-Konfigurationsrichtlinie (Windows Phone 8.1 und höher)** von Microsoft Intune die folgenden Einstellungen für Windows Phone 8.1-Geräte:

-   **Sicherheitseinstellungen für mobile Geräte** – Treffen Sie in einer Liste mit vordefinierten Einstellungen eine Auswahl, mit denen Sie eine Reihe von Features und Funktionen auf dem Gerät steuern können.

-   **Kompatible und nicht kompatible Apps**: Geben Sie eine Liste von Apps an, die in Ihrem Unternehmen kompatibel bzw. nicht kompatibel sind. Die Installation dieser Apps kann auf Windows Phone-Geräten blockiert oder zugelassen werden.

### Anwendbarkeitseinstellungen

|Name der Einstellung|Details|
|----------------|----------------------------------|
|**Alle Konfigurationen auf Windows 10 anwenden**|Erlaubt, dass Einstellungen in dieser Richtlinie zusätzlich zu Windows Phone 8.1-Geräten auf Windows 10 Mobile-Geräte angewendet werden.|

### Kennworteinstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Gibt an, ob Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.|Ja|Ja|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z.B. alphanumerisch oder nur numerisch.|Ja|Ja|
|**Erforderlicher Kennworttyp – Minimale Anzahl von Zeichensätzen**|Gibt an, wie viele verschiedene Zeichensätze im Kennwort enthalten sein müssen. Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Für iOS-Geräte wird hiermit jedoch die erforderliche Anzahl von Symbolzeichen im Kennwort angegeben.|Ja|Ja|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Kennwort enthalten muss.|Ja|Ja|
|**Einfache Kennwörter zulassen**|Gibt an, dass einfache Kennwörter, wie z.B: „0000“ und „1234“ verwendet werden können.|Ja|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Gibt an, wie häufig ein falsches Kennwort eingegeben werden kann, bevor das Gerät zurückgesetzt wird.|Ja|Ja|
|**Inaktivität in Minuten bis zur Abschaltung des Bildschirms**|Gibt die Zeitdauer an, die ein Gerät im Leerlauf bleiben muss, bevor der Bildschirm automatisch gesperrt wird.|Ja|Ja|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|Ja|Ja|
|**Kennwortverlauf speichern**|Gibt an, ob zuvor verwendete Kennwörter gespeichert werden, um zu verhindern, dass der Benutzer sie erneut verwendet.|Ja|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter gespeichert werden.|Ja|Ja|

### Verschlüsselungseinstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Verschlüsselung auf mobilen Geräten vorschreiben**|Schreibt vor, dass die Daten auf unterstützten mobilen Geräten verschlüsselt werden müssen.<br>Für Windows Phone 8-Geräte müssen Sie hier **Ja**festlegen.|Ja|Ja|

### Systemeinstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Bildschirmaufnahme zulassen**|Ermöglicht dem Benutzer, den Bildschirminhalt als Bilddatei zu erfassen.|Nein|Ja|
|**Übermitteln von Diagnosedaten zulassen**|Ermöglicht, dass das Gerät Diagnoseinformationen an Microsoft übermittelt.|Nein|Ja|

### Cloudeinstellungen – Konten und Synchronisierung

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Microsoft-Konto erlauben**|Ermöglicht, dass ein Microsoft-Konto mit dem mobilen Gerät verknüpft werden kann.|Nein|Ja|

### E-Mail-Einstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Benutzerdefinierte E-Mail-Konten erlauben**|Ermöglicht, dass das Gerät eine Verbindung mit nicht von Microsoft stammenden E-Mail-Konten herstellen kann.|Nein|Ja|

### Anwendungseinstellungen – Browser

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Webbrowser zulassen**|Ermöglicht oder blockiert die Verwendung des integrierten Webbrowser auf Geräten.|Nein|Ja|

### Anwendungseinstellungen – Apps

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**App Store zulassen**|Ermöglicht Benutzern, über das Gerät eine Verbindung mit dem App Store herzustellen.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Hardware

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kamera zulassen**|Ermöglicht oder blockiert die Verwendung der Kamera des Geräts.|Nein|Ja|
|**Wechselspeichermedien zulassen**|Ermöglicht dem Gerät, Wechselmedien wie eine SD-Karte zu verwenden.|Ja|Ja|
|**WLAN zulassen**|Aktiviert oder deaktiviert die WLAN-Funktionalität des Geräts.|Nein|Ja|
|**WLAN-Tethering zulassen**|Ermöglicht die Verwendung des WLAN-Tetherings auf dem Gerät.|Nein|Ja
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Ermöglicht, dass das Gerät automatisch eine Verbindung mit unverschlüsselten WLAN-Hotspots herstellen und die Geschäftsbedingungen für die Verbindung automatisch akzeptieren kann.|Nein|Ja|
|**Berichterstellung für WLAN-Hotspots zulassen**|Sendet Informationen über WLAN-Verbindungen, um nahegelegene Verbindungen zu ermitteln.|Nein|Ja|
|**Geolocation zulassen**|Erlaubt dem Gerät die Nutzung von Standortinformationen.|Nein|Ja|
|**NFC zulassen**|Erlaubt Vorgänge, die NFC (Near Field Communication) verwenden.|Nein|Ja|
|**Bluetooth zulassen**|Aktiviert oder deaktiviert die Bluetooth-Funktionalität des Geräts.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Funktionen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kopieren und Einfügen zulassen**|Lässt Kopier- und Einfügefunktionen auf Geräten zu.|Nein|Ja|

### Einstellungen für zulässige und blockierte Apps
Geben Sie in der **Liste zulässiger oder blockierter Apps** eine Liste der jeweiligen Apps mit den folgenden Informationen an:

> [!NOTE]
> Eine einzelne Richtlinie kann nur eine Liste zulässiger oder blockierter Apps enthalten. Sie können nicht beide Typen in derselben Richtlinie angeben.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Öffnen der aufgelisteten Anwendungen durch die Geräte blockieren**|Listet die Apps auf, die nicht von Intune verwaltet werden, und welche Benutzer diese nicht installieren und ausführen dürfen.|
|**Geräten nur erlauben, die aufgelisteten Anwendungen zu installieren**|Listet die Apps auf, die Benutzer installieren dürfen. Benutzer können keine anderen Apps installieren. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.|
|**Hinzufügen**|Fügt eine App zur ausgewählten Liste hinzu. Geben Sie einen Namen Ihrer Wahl, die URL zur App im App-Store und den Herausgeber der App (optional) an. Weitere Informationen finden Sie unter „Angeben von URLs zu App Stores“ weiter unten in diesem Thema.
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer CSV-Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber und App-URL.|
|**Bearbeiten**|Ermöglicht Ihnen das Bearbeiten von Name, Herausgeber und URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|
> [!IMPORTANT]
> Wenn Sie eine Liste von zulässigen Apps für Windows Phone 8.1-Geräte angeben, müssen Sie die Unternehmensportal-App zu dieser Liste hinzufügen, da sie andernfalls blockiert wird.


### Referenzinformationen für zulässige und blockierte Apps

#### Angeben von URLs zu App-Stores
Verwenden Sie das folgende Format, um eine App-URL in der Liste zulässiger und blockierter Apps anzugeben:

Suchen Sie auf der [Windows Phone-Seite für Apps und Spiele](http://www.windowsphone.com/en-us/store/overview) nach der App, die Sie verwenden möchten.

Öffnen Sie die Seite der App, und kopieren Sie die URL in die Zwischenablage. Sie können diese URL nun in der Liste kompatibler oder nicht kompatibler Apps verwenden.

**Beispiel:** Durchsuchen Sie den Store nach der Skype-App. Die URL, die Sie verwenden, ist **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Windows Phone-Konfigurationsrichtlinie** von Microsoft Intune die Einstellungen für OMA-URI bereit, um Features auf **Windows Phone 8.1-Geräten** zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion ermöglicht es Ihnen, Windows Phone-Einstellungen bereitzustellen, die nicht mit einer allgemeinen Intune-Konfigurationsrichtlinie konfigurierbar sind. Weitere Informationen zu den Einstellungen, die Sie mit diesen Richtlinien konfigurieren können, finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Informationen zum Erstellen von OMA-URI-Einstellungen für Windows Phone-Geräte finden Sie in der [MDM-Protokolldokumentation für Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

### Allgemeine Einstellungen

|Name der Einstellung|Details|
|----------------|--------------------|
|**Name**|Geben Sie einen eindeutigen Namen für die Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
|**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### OMA-URI-Einstellungen

Klicken Sie im Abschnitt **OMA-URI-Einstellungen** auf **Hinzufügen**, um eine Einstellung hinzuzufügen. Sie können auch eine vorhandene Einstellung bearbeiten oder löschen.

Geben Sie im Dialogfeld **OMA-URI hinzufügen oder bearbeiten** die folgenden Informationen an:

|Name der Einstellung|Details|
    |--------|--------------------|
    |**Name der Einstellung**|Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
    |**Beschreibung der Einstellung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**Datentyp**|Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus:<br /><br />-   **Zeichenfolge**<br />-   **Zeichenfolge (XML)**<br />-   **Datum und Uhrzeit**<br />-   **Ganze Zahl**<br />-   **Gleitkomma**<br />-   **Boolesch**|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


