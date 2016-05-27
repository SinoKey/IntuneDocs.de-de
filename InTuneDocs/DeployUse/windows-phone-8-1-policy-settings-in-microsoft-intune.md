---
# required metadata

title: Einstellungen für Windows Phone 8.1-Richtlinien in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einstellungen für Windows Phone 8.1-Richtlinien in Microsoft Intune

## Allgemeine Konfigurationseinstellungen

Konfigurieren Sie mithilfe der **allgemeinen Windows Phone-Konfigurationsrichtlinie** von Microsoft Intune die folgenden Einstellungen für Windows Phone 8.1-Geräte:

-   **Sicherheitseinstellungen für mobile Geräte** – Treffen Sie in einer Liste mit vordefinierten Einstellungen eine Auswahl, mit denen Sie eine Reihe von Features und Funktionen auf dem Gerät steuern können.

-   **Kompatible und nicht kompatible Apps**: Geben Sie eine Liste von Apps an, die in Ihrem Unternehmen kompatibel bzw. nicht kompatibel sind. Die Installation dieser Apps kann auf Windows Phone-Geräten blockiert oder zugelassen werden.

### Kennworteinstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Gibt an, ob Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.|Ja|Ja|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|Ja|Ja|
|**Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen. Für iOS-Geräte wird hiermit jedoch die erforderliche Anzahl von Symbolzeichen im Kennwort angegeben.|Ja|Ja|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Kennwort enthalten muss.|Ja|Ja|
|**Einfache Kennwörter zulassen**|Einfache Kennwörter enthalten '0000' und '1234'.|Ja|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Gibt an, wie häufig ein falsches Kennwort eingegeben werden kann, bis das Gerät zurückgesetzt wird.|Ja|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Gibt die Zeitdauer an, die ein Gerät im Leerlauf bleiben muss, bevor der Bildschirm automatisch gesperrt wird.|Ja|Ja|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|Ja|Ja|
|**Kennwortverlauf speichern**|Gibt an, ob zuvor verwendete Kennwörter gespeichert werden, um zu verhindern, dass der Benutzer sie erneut verwendet.|Ja|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter gespeichert werden.|Ja|Ja|

### Verschlüsselungseinstellungen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Verschlüsselung auf mobilem Gerät anfordern**|Schreibt vor, dass die Daten auf unterstützten mobilen Geräten verschlüsselt werden müssen.<br>Für Windows Phone 8-Geräte müssen Sie hier **Ja** festlegen..|Ja|Ja|

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
|**Webbrowser zulassen**|Ermöglicht oder blockiert den integrierten Webbrowser auf Geräten.|Nein|Ja|

### Anwendungseinstellungen – Apps

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**App Store zulassen**|Ermöglicht Benutzern, über das Gerät eine Verbindung mit dem App Store herzustellen.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Hardware

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kamera zulassen**|Lassen Sie die Kamera des Geräts zu, oder blockieren Sie sie.|Nein|Ja|
|**Wechselspeichermedien zulassen**|Ermöglicht dem Gerät, Wechselmedien wie eine SD-Karte zu verwenden.|Ja|Ja|
|**WLAN zulassen**|Aktiviert oder deaktiviert die WLAN-Funktionalität des Geräts.|Nein|Ja|
|**WLAN-Tethering zulassen**|Ermöglicht die Verwendung des WLAN-Tetherings auf dem Gerät.|Nein|Ja
|**Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen**|Ermöglicht, dass das Gerät automatisch eine Verbindung mit unverschlüsselten WLAN-Hotspots herstellen und die Geschäftsbedingungen für die Verbindung automatisch akzeptieren kann.|Nein|Ja|
|**Berichterstellung für WLAN-Hotspots zulassen**|Senden Sie Informationen über WLAN-Verbindungen, um nahegelegene Verbindungen zu ermitteln.|Nein|Ja|
|**Geolocation zulassen**|Erlaubt dem Gerät die Nutzung von Standortinformationen.|Nein|Ja|
|**NFC zulassen**|Erlaubt Vorgänge, die NFC (Near Field Communication) verwenden.|Nein|Ja|
|**Bluetooth zulassen**|Aktiviert oder deaktiviert die Bluetooth-Funktionalität des Geräts.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Funktionen

|Name der Einstellung|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kopieren und Einfügen zulassen**|Lassen Sie Kopier- und Einfügefunktionen auf Geräten zu.|Nein|Ja|

### Einstellungen für kompatible und nicht kompatible Anwendungen
Geben Sie in der Liste der **kompatiblen und nicht kompatiblen Apps** eine Liste kompatibler oder nicht kompatibler Apps mit den folgenden Informationen ein:

> [!NOTE]
> Eine einzelne Richtlinie kann nur eine Liste kompatibler oder eine Liste nicht kompatibler Apps enthalten. Sie können nicht beide Typen in derselben Richtlinie angeben.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Öffnen der aufgelisteten Anwendungen durch die Geräte blockieren**|Listet die Apps auf, die nicht von Intune verwaltet werden und die Benutzer nicht installieren und ausführen dürfen.|
|**Geräten nur erlauben, die aufgelisteten Anwendungen zu installieren**|Listet die Apps auf, die Benutzer installieren dürfen. Benutzer können keine anderen Apps installieren. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.|
|**Hinzufügen**|Fügt eine App zur ausgewählten Liste hinzu. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an. Weitere Informationen finden Sie unter „Angeben von URLs zu App Stores“ weiter unten in diesem Thema.
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer CSV-Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber und App-URL.|
|**Bearbeiten**|Ermöglicht Ihnen das Bearbeiten von Name, Herausgeber und URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|
> [!IMPORTANT]
> Wenn Sie eine Liste von zulässigen Apps für Windows Phone 8.1-Geräte angeben, müssen Sie die Unternehmensportal-App zu dieser Liste hinzufügen, da sie andernfalls blockiert wird.


### Referenzinformationen für kompatible und nicht kompatible Apps

#### Angeben von URLs zu App-Stores
Verwenden Sie zum Festlegen einer App-URL in der Liste konformer und nicht konformer Apps das folgende Format:

Suchen Sie auf der [Windows Phone-Seite für Apps und Spiele](http://www.windowsphone.com/en-us/store/overview) nach der App, die Sie verwenden möchten.

Öffnen Sie die Seite der App, und kopieren Sie die URL in die Zwischenablage. Jetzt können Sie diese als URL in der Liste mit kompatiblen oder nicht kompatiblen Apps verwenden.

**Beispiel:** Durchsuchen Sie den Store nach der Skype-App. Die URL, die Sie verwenden, ist **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**..

## Benutzerdefinierte Richtlinieneinstellungen 
Stellen Sie mithilfe der **benutzerdefinierten Windows Phone-Richtlinie** von Microsoft Intune Einstellungen für OMA-URI (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf **Windows Phone 8.1-Geräten** zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Windows Phone-Einstellungen bereitzustellen, die nicht mit einer allgemeinen Intune-Konfigurationsrichtlinie konfigurierbar sind. Weitere Informationen zu den Einstellungen, die Sie mit diesen Richtlinien konfigurieren können, finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

Informationen zum Erstellen von OMA-URI-Einstellungen für Windows Phone-Geräte finden Sie in der [MDM-Protokolldokumentation für Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx)..

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
    |**Datentyp**|Wählen Sie den Datumstyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus:<br /><br />-   **Zeichenfolge**<br />-   **Zeichenfolge (XML)**<br />-   **Datum und Uhrzeit**<br />-   **Ganze Zahl**<br />-   **Gleitkomma**<br />-   **Boolesch**|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


