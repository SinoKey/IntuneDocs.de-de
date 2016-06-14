---
# required metadata

title: Einstellungen für Android- und Samsung KNOX-Konfigurationsrichtlinien | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einstellungen für Android- und Samsung KNOX-Richtlinien in Microsoft Intune

## Allgemeine Konfigurationsrichtlinie

Verwenden Sie die allgemeine **Android-Konfigurationsrichtlinie** von Microsoft Intune zum Konfigurieren von Einstellungen für:

-   **Sicherheitseinstellungen für mobile Geräte** – Treffen Sie in einer Liste mit vordefinierten Einstellungen eine Auswahl, mit denen Sie eine Reihe von Features und Funktionen auf dem Gerät steuern können.

-   **Kiosk-Modus** (nur für Samsung KNOX-Geräte) – Sperren Sie ein Gerät, sodass nur bestimmte Features ausgeführt werden können. Beispielsweise können Sie festlegen, dass auf einem Gerät nur eine von Ihnen angegebene verwaltete App ausgeführt werden kann, oder Sie können die Lautstärkeregler eines Geräts deaktivieren. Diese Einstellungen können für ein Demomodell eines Geräts oder ein Gerät nützlich sein, das nur eine bestimmte Funktion ausführen soll, wie z. B. ein Point-of-Sale-Gerät.

-   **Kompatible und nicht kompatible Apps**: Geben Sie eine Liste von Apps an, die in Ihrem Unternehmen kompatibel bzw. nicht kompatibel sind. Auf Android- und iOS-Geräten können Sie mit dem **Bericht über nicht kompatible Apps** überprüfen, ob die vom Benutzer installierten Apps zu den als von Ihnen kompatibel angegebenen Apps gehören (die Installation der App kann jedoch nicht blockiert werden).

> [!TIP]
> Sie können Bestimmungen für Benutzer konfigurieren, um sicherzustellen, dass sie bestätigen, dass Apps auf ihrem Gerät, einschließlich persönlicher Apps, ausgewertet werden und dass nicht kompatible Anwendungen entweder blockiert oder als nicht kompatibel gemeldet werden. Benutzer müssen diese Bestimmungen akzeptieren, bevor sie ihr Gerät registrieren und Apps über das Unternehmensportal abrufen können. Weitere Informationen zur Verwendung von Geschäftsbedingungen finden Sie unter [Einstellungen für Geschäftsbedingungensrichtlinien in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Wenn die gesuchte Einstellung nicht in diesem Thema enthalten ist, können Sie sie ggf. mithilfe einer benutzerdefinierten Android-Richtlinie erstellen, die Ihnen das Steuern des Geräts mithilfe von OMA-URI-Einstellungen erlaubt. Weitere Informationen finden Sie weiter unten in diesem Thema unter **Benutzerdefinierte Richtlinieneinstellungen**.

### Kennworteinstellungen

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Auf unterstützten Geräten ein Kennwort erfordern.|Ja|Ja|
|**Minimale Kennwortlänge**|Die Mindestlänge für das Kennwort.|Ja|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Setzt das Gerät zurück, wenn diese Anzahl von Anmeldeversuchen fehlschlägt.|Ja|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**|Geben Sie die Anzahl der Minuten an, bevor das Gerät automatisch gesperrt wird.|Ja|Ja|
|**Kennwortablauf (Tage)**|Die Anzahl der Tage, bevor ein Kennwort geändert werden muss.|Ja|Ja|
|**Kennwortverlauf speichern**|Diese Anzahl zuvor verwendeter Kennwörter speichern.|Ja|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Verhindert die Wiederverwendung zuvor verwendeter Kennwörter.|Ja|Ja|
|**Kennwortqualität**|Wählen Sie den erforderlichen Grad der Kennwortkomplexität aus. Wählen Sie zudem aus, ob biometrische Geräte zulässig sind.|Ja|Ja|
|**Fingerabdruckentsperrung zulassen**|Lässt das Entsperren des Geräts mittels Fingerabdruck zu.|Nein|Ja|

### Verschlüsselungseinstellungen

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Verschlüsselung auf mobilem Gerät anfordern**|Erfordert die Verschlüsselung von Dateien auf dem mobilen Gerät.|Ja|Ja|
|**Verschlüsselung auf Speicherkarten vorschreiben**|Gibt an, ob die Gerätespeicherkarte verschlüsselt werden muss.|Nein|Ja|

### Systemeinstellungen

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Bildschirmaufnahme zulassen**|Ermöglicht dem Benutzer, den Bildschirminhalt als Bild zu erfassen.|Nein|Ja|
|**Übermitteln von Diagnosedaten zulassen**|Ermöglicht, dass das Gerät Diagnoseinformationen an Google übermittelt.|Nein|Ja|
|**Zurücksetzen auf Werkseinstellungen zulassen**|Ermöglicht dem Benutzer das Zurücksetzen des Geräts auf die Werkseinstellungen.|Nein|Ja|

### Cloudeinstellungen – Dokumente und Daten

|Name der Einstellung|Details|Android und Samsung KNOX|Android 4.0+|
|----------------|----------------------------|----------------|
|**Google-Sicherung zulassen**|Ermöglicht die Verwendung der Google-Sicherung.|Nein|Ja|

### Cloudeinstellungen – Konten und Synchronisierung

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Automatische Synchronisierung mit Google-Konto zulassen**|Ermöglicht die automatische Synchronisierung der Einstellungen von Google-Konten.|Nein|Ja|

### Anwendungseinstellungen – Browser

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Webbrowser zulassen**|Gibt an, ob der Webbrowser des Geräts verwendet werden darf.|Nein|Ja|
|**AutoAusfüllen zulassen**|Hiermit wird die Verwendung der AutoAusfüllen-Funktion des Webbrowsers zugelassen.|Nein|Ja|
|**Popupblocker zulassen**|Hiermit wird die Verwendung des Popupblockers im Webbrowser zugelassen.|Nein|Ja|
|**Cookies zulassen**|Hiermit wird die Verwendung von Cookies durch den Webbrowser des Geräts zugelassen.|Nein|Ja|
|**Active Scripting zulassen**|Hiermit wird die Verwendung von Active Scripting durch den Webbrowser des Geräts zugelassen.|Nein|Ja|

### Anwendungseinstellungen – Apps

|Name der Einstellung|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google Play Store zulassen**|Ermöglicht dem Benutzer den Zugriff auf den Google Play Store auf dem Gerät.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Hardware

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Kamera zulassen**|Ermöglicht die Verwendung der Gerätekamera.|Ja|Ja|
|**Wechselspeichermedien zulassen**|Ermöglicht dem Gerät die Verwendung von Wechselmedien, z. B. SD-Karten.|Nein|Ja|
|**WLAN zulassen**|Ermöglicht die Verwendung der WLAN-Funktionen des Geräts.|Nein|Ja|
|**WLAN-Tethering zulassen**|Ermöglicht die Verwendung des WLAN-Tetherings auf dem Gerät.|Nein|Ja|
|**Geolocation zulassen**|Erlaubt dem Gerät die Nutzung von Standortinformationen.|Nein|Ja|
|**NFC zulassen**|Erlaubt Vorgänge, die NFC (Near Field Communication) verwenden, sofern dies vom Gerät unterstützt wird.|Nein|Ja|
|**Bluetooth zulassen**|Hiermit wird die Verwendung von Bluetooth auf dem Gerät zugelassen.|Nein|Ja|
|**Ausschalten zulassen**|Hiermit wird dem Benutzer das Ausschalten des Geräts gestattet.<br /><br />Wenn diese Einstellung deaktiviert ist, funktioniert die Einstellung **Anzahl der zulässigen wiederholten Anmeldefehler, bevor die Gerätedaten zurückgesetzt werden** für Samsung KNOX-Geräte nicht.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Mobiltelefon

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Sprachroaming zulassen**|Zulassen des Sprachroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Nein|Ja|
|**Datenroaming zulassen**|Zulassen des Datenroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Nein|Ja|
|**SMS/MMS-Messaging zulassen**|Zulassen der Verwendung von SMS- und MMS-Nachrichten auf dem Gerät.|Nein|Ja|

### Einstellungen für Gerätefunktionen - Funktionen

|Name der Einstellung|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Sprach-Assistent zulassen**|Zulassen der Verwendung von Sprach-Assistent-Software auf dem Gerät.|Nein|Ja|
|**Sprachwahl zulassen**|Aktiviert oder deaktiviert die Verwendung des Features „Sprachwahlverfahren“ auf dem Gerät.|Nein|Ja|
|**Kopieren und Einfügen zulassen**|Zulassen von Kopier- und Einfügefunktionen auf dem Gerät.|Nein|Ja|
|**Freigabe der Zwischenablage zwischen Anwendungen zulassen**|Verwenden Sie die Zwischenablage zum Kopieren und Einfügen zwischen Apps.|Nein|Ja|
|**YouTube zulassen**|Zulassen der Verwendung von YouTube auf dem Gerät.|Nein|Ja|

### Einstellungen für kompatible und nicht kompatible Anwendungen
Geben Sie in der Liste der **kompatiblen &amp; nicht kompatiblen Apps** eine Liste kompatibler oder nicht kompatibler Apps mit den folgenden Informationen ein:

> [!NOTE]
> Eine einzelne Richtlinie kann nur eine Liste kompatibler oder eine Liste nicht kompatibler Apps enthalten. Sie können nicht beide Typen in derselben Richtlinie angeben.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Nichtkompatibilität melden, wenn Benutzer die aufgelisteten Apps installieren**|Listet die Apps auf, die nicht von Intune verwaltet werden und die Benutzer nicht installieren und ausführen dürfen.|
|**Nichtkompatibilität nicht melden, wenn Benutzer die aufgelisteten Apps installieren**|Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.|
|**Hinzufügen**|Fügt eine App zur ausgewählten Liste hinzu. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an.<br /><br />Informationen finden Sie unter „Angeben von URLs zu App Stores“ weiter unten in diesem Thema.|
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer CSV-Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber und App-URL.|
|**Bearbeiten**|Ermöglicht Ihnen das Bearbeiten von Name, Herausgeber und URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|

### Einstellungen für den Kioskmodus
Geben Sie die folgenden Einstellungen für **Samsung KNOX-Geräte** an:

|Name der Einstellung|Details|
|----------------|--------------------|
|**Wählen Sie eine verwalteten App aus, die ausgeführt werden darf, während sich das Gerät im Kiosk-Modus befindet**|Klicken Sie auf **Durchsuchen**, und wählen Sie dann die verwaltete App aus, die ausgeführt werden darf, wenn sich das Gerät im Kioskmodus befindet (Apps, die als Link zum Store angegeben sind, werden derzeit nicht unterstützt). Andere Apps dürfen auf dem Gerät nicht ausgeführt werden.|
|**Lautstärkeregler zulassen**|Aktiviert oder deaktiviert die Verwendung der Lautstärkeregler am Gerät.|
|**Schaltfläche für Standby und Aktivieren zulassen**|Aktiviert oder deaktiviert die Taste für Standby/Aktivierung des Bildschirms am Gerät.|

### Referenzinformationen für kompatible und nicht kompatible Apps

#### Überwachen kompatibler und nicht kompatibler Apps
Im **Bericht über nicht kompatible Apps** können Sie sich über die Konformität zulässiger und blockierter Anwendungen informieren.

###### So führen Sie den Bericht über nicht kompatible Apps aus

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Berichte** &gt; **Bericht über nicht kompatible Apps**.

2.  Wählen Sie die Gerätegruppen aus, die Sie überprüfen möchten, geben Sie an, ob Sie nach kompatiblen und/oder nicht kompatiblen Apps suchen möchten, und klicken Sie dann auf **Bericht anzeigen**.

#### Angeben von URLs zu App-Stores
Verwenden Sie zum Festlegen einer App-URL in der Liste konformer und nicht konformer Apps das folgende Format:

Suchen Sie im [Apps-Bereich von Google Play](https://play.google.com/store/apps) nach der App, die Sie verwenden möchten.

Öffnen Sie die Installationsseite für die App, und kopieren Sie die URL in die Zwischenablage. Jetzt können Sie diese als URL in der Liste mit kompatiblen oder nicht kompatiblen Apps verwenden.

**Beispiel**: Suchen Sie in Google Play nach Microsoft Office Mobile. Die URL, die Sie verwenden, ist **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Android-Konfigurationsrichtlinie** von Microsoft Intune die Einstellungen für OMA-URI (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Android-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Android-Einstellungen bereitzustellen, die nicht mit Intune-Richtlinien konfigurierbar sind. Weitere Informationen zu den Einstellungen, die Sie mit diesen Richtlinien konfigurieren können, finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

> [!NOTE]
> Derzeit unterstützen benutzerdefinierte Android-Richtlinien unterstützt nur das Konfigurieren von WLAN-Einstellungen für Android-Geräte, die einen vorinstallierten Schlüssel enthalten. Weitere Informationen finden Sie später in diesem Abschnitt unter „Konfigurieren eines benutzerdefinierten WLAN-Profils mit einem vorinstallierten Schlüssel“.

### Allgemeine Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für die benutzerdefinierte Android-Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
    |**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### OMA-URI-Einstellungen

   |Name der Einstellung|Details|
    |--------|--------------------|
    |**Name der Einstellung**|Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
    |**Beschreibung der Einstellung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**Datentyp**|Wählen Sie den Datumstyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge, Zeichenfolge (XML), Datum und Uhrzeit, ganze Zahl, Gleitkomma** oder **Boolesch** aus.|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|

### Beispiel: Konfigurieren eines benutzerdefinierten WLAN-Profils mit einem vorinstallierten Schlüssel
Obwohl Intune WLAN-Profile für Android-Geräte unterstützt, ist derzeit das Einbeziehen eines vorinstallierten Schlüssels in die Konfiguration nicht möglich. In diesem Beispiel erfahren Sie, wie Sie eine benutzerdefinierte Android-Richtlinie erstellen, die ein WLAN-Profil mit einem vorinstallierten Schlüssel auf dem Android-Gerät erstellt.

#### So erstellen Sie ein WLAN-Profil mit einem vorinstallierten Schlüssel

1.  Stellen Sie sicher, dass die Benutzer die neueste Version der [Intune-Unternehmensportal-App](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) für Android verwenden.

2.  Erstellen Sie eine benutzerdefinierte Android-Richtlinie, und fügen Sie die folgende Einstellung hinzu:

|Name der Einstellung|Details|
|----------------|--------------------|
|**Name der Einstellung**|Geben Sie einen Namen Ihrer Wahl für die Einstellung ein.|
|**Beschreibung der Einstellung**|Geben Sie eine Beschreibung für die Einstellung ein.|
|**Datentyp**|Wählen Sie **Zeichenfolge (XML)** aus.|
|**OMA-URI**|Geben Sie Folgendes ein: ./Vendor/MSFT/WiFi/Profile/*&lt;Ihr WLAN-Profil&gt;*/Settings|

3.  Kopieren Sie für **Wert** den folgenden XML-Code und fügen Sie ihn dann ein:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile 
                    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile 
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Wenn Sie fertig sind, speichern Sie die Richtlinie und stellen sie den erforderlichen Android-Geräten bereit. Das neue WLAN-Profil wird in der Liste der Verbindungen auf dem Gerät angezeigt.

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO3-->


