---
# required metadata

title: iOS-Richtlinieneinstellungen | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-Richtlinieneinstellungen in Microsoft Intune

## Allgemeine Konfigurationsrichtlinieneinstellungen

Verwenden Sie die allgemeine **iOS-Konfigurationsrichtlinie** von Microsoft Intune zum Konfigurieren von Einstellungen für:

-   **Sicherheitseinstellungen für mobile Geräte** – Treffen Sie in einer Liste mit vordefinierten Einstellungen eine Auswahl, mit denen Sie eine Reihe von Features und Funktionen auf dem Gerät steuern können.

-   **Kioskmodus**: Sie können ein Gerät so konfigurieren, dass nur bestimmte Features funktionieren. Beispielsweise können Sie festlegen, dass auf einem Gerät nur eine von Ihnen angegebene verwaltete App ausgeführt werden kann, oder Sie können die Lautstärkeregler eines Geräts deaktivieren. Diese Einstellungen können für ein Demomodell eines Geräts oder ein Gerät nützlich sein, das nur eine bestimmte Funktion ausführen soll, wie z. B. ein Point-of-Sale-Gerät.

-   **Kompatible und nicht kompatible Apps**: Geben Sie eine Liste von Apps an, die in Ihrem Unternehmen kompatibel bzw. nicht kompatibel sind. Auf Android- und iOS-Geräten können Sie mit dem **Bericht über nicht kompatible Apps** überprüfen, ob die vom Benutzer installierten Apps zu den als von Ihnen kompatibel angegebenen Apps gehören (die Installation der App kann jedoch nicht blockiert werden).

> [!TIP]
> Sie können Bestimmungen für Benutzer konfigurieren, um sicherzustellen, dass sie bestätigen, dass Apps auf ihrem Gerät, einschließlich persönlicher Apps, ausgewertet werden und dass nicht kompatible Anwendungen entweder blockiert oder als nicht kompatibel gemeldet werden. Benutzer müssen diese Bestimmungen akzeptieren, bevor sie ihr Gerät registrieren und Apps über das Unternehmensportal abrufen können. Weitere Informationen zur Verwendung von Nutzungsbedingungen finden Sie unter [Einstellungen für Nutzungsbedingungsrichtlinien in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Wenn die gesuchte Einstellung nicht in diesem Thema enthalten ist, können Sie sie ggf. mithilfe einer benutzerdefinierten iOS-Richtlinie erstellen, die Ihnen das Importieren von Einstellungen erlaubt, die Sie mit dem Tool [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)erstellt haben. Weitere Informationen finden Sie weiter unten in diesem Thema unter **Benutzerdefinierte Richtlinieneinstellungen**.

### Sicherheitseinstellungen

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Legen Sie fest, ob Benutzer ein Kennwort eingeben müssen, um auf ihr Gerät zugreifen zu können.|Ja|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|Ja|
|**Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen**|Es gibt vier Zeichensätze: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole. Diese Einstellung gibt an, wie viele Zeichensätze im Kennwort enthalten sein müssen. Für iOS-Geräte wird hiermit jedoch die erforderliche Anzahl von Symbolzeichen im Kennwort angegeben.|Ja|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Kennwort enthalten muss.|Ja|
|**Einfache Kennwörter zulassen**|Einfache Kennwörter wie „0000“ und „1234“ zulassen.|Ja|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Setzt das Gerät zurück, wenn diese Anzahl von Anmeldeversuchen fehlschlägt.|Ja|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**<sup>1</sup>|Geben Sie die Anzahl der Minuten an, bevor die Anzeige des Geräts deaktiviert wird.|Ja|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|Ja|
|**Kennwortverlauf speichern**|Gibt an, ob der Benutzer zuvor verwendete Kennwörter wiederverwenden kann.|Ja|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|Ja|
|**Minuten Inaktivität vor erneuter Anforderung des Kennworts**<sup>1</sup>|Gibt an, wie lange das Gerät sich im Leerlauf bleiben kann, bevor der Benutzer sein Kennwort erneut eingeben muss.|Ja|
|**Fingerabdruckentsperrung zulassen**|Lässt das Entsperren des Geräts mittels Fingerabdruck zu.|iOS 7.1 und höher|
<sup>1</sup> Wenn Sie für iOS-Geräte die Einstellungen **Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird** und **Minuten Inaktivität vor erneuter Anforderung des Kennworts** konfigurieren, werden sie nacheinander angewendet. Wenn Sie beispielsweise den Wert für beide Einstellungen auf **5** Minuten einstellen, wird der Bildschirm automatisch nach 5 Minuten deaktiviert, und das Gerät wird nach weiteren 5 Minuten gesperrt. Wenn der Benutzer den Bildschirm jedoch manuell deaktiviert, wird die zweite Einstellung sofort angewendet. Im selben Beispiel wird das Gerät 5 Minuten später gesperrt, nachdem der Benutzer den Bildschirm deaktiviert hat.

### Systemeinstellungen

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Bildschirmfoto zulassen**|Ermöglicht dem Benutzer, den Bildschirminhalt als Bild zu erfassen.|Ja|
|**Kontrollcenter auf Sperrbildschirm zulassen**|Steuert, ob auf die Kontrollcenter-App zugegriffen werden kann, wenn das Gerät gesperrt ist.|iOS 7.1 und höher|
|**Benachrichtigungsansicht auf Sperrbildschirm zulassen**|Erlaubt dem Benutzer den Zugriff auf die Benachrichtigungsansicht, ohne dass das Gerät entsperrt werden muss.|iOS 7.1 und höher|
|**Ansicht "Heute" auf Sperrbildschirm zulassen**|Steuert, ob Benachrichtigungen angezeigt werden können, wenn das Gerät gesperrt ist.|iOS 7.1 und höher|
|**Übermitteln von Diagnosedaten zulassen**|Ermöglicht dem Gerät das Senden von Diagnosedaten an Apple.|Ja|
|**Nicht vertrauenswürdige TLS-Zertifikate zulassen**|Hiermit werden nicht vertrauenswürdige TLS-Zertifikate (Transport Layer Security) auf dem Gerät zugelassen.|Ja|
|**Passbook bei Sperre zulassen**|Erlaubt dem Benutzer den Zugriff auf die Passbook-App, während das Gerät gesperrt ist.|Ja|

### Cloudeinstellungen – Dokumente und Daten

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Sicherung in iCloud zulassen**|Ermöglicht dem Benutzer, das Gerät in iCloud zu sichern.|Ja|
|**Dokumentsynchronisierung in iCloud zulassen**|Erlaubt die Dokument- und Schlüssel-/Wertsynchronisierung in Ihrem iCloud-Speicher. Ja|
|**Photo Stream-Synchronisierung in iCloud zulassen**|Erlaubt, dass Fotos auf dem Gerät mit iCloud synchronisiert werden.|Ja|
|**Verschlüsselte Sicherung erforderlich**|Fordert an, dass Gerätesicherungen verschlüsselt werden.|Ja|

### Anwendungseinstellungen – Browser

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Safari zulassen**|Geben Sie an, ob der Safari-Browser auf dem Gerät verwendet werden kann.|Ja|
|**AutoAusfüllen zulassen**|Benutzer können die Einstellungen für AutoVervollständigen im Browser ändern.|Ja|
|**Popupblocker zulassen**|Aktivieren oder deaktivieren Sie den Popupblocker des Browsers.|Ja|
|**Cookies zulassen**|Ermöglichen, dass der Webbrowser auf dem Gerät Cookies verwendet.|Ja|
|**JavaScript zulassen**|Ermöglichen, dass Java-Skripts im Browser ausgeführt werden.|Ja|
|**Betrugswarnung zulassen**|Betrugswarnungen im Browser auf dem Gerät zulassen.|Ja|

### Anwendungseinstellungen – Apps

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**App Store zulassen**|Ermöglicht dem Gerät den Zugriff auf den App Store.|Ja|
|**Kennwort für den Zugriff auf den Anwendungsspeicher erforderlich**|Ja|
|**In-App-Einkäufe zulassen**|Zulassen, dass Einkäufe im Store in einer ausgeführten App erfolgen.|Ja|
|**Verwaltete Dokumente in anderen nicht verwalteten Apps zulassen**|Hiermit wird die Anzeige von Unternehmensdokumenten in beliebigen Apps zugelassen.<br>**Beispiel:** Sie möchten verhindern, dass Benutzer Dateien aus der OneDrive-App in Dropbox speichern. Legen Sie für diese Einstellung „Nein“ fest. Sobald das Gerät die Richtlinie empfängt (z. B. nach einem Neustart), ist kein Speichern mehr möglich.|iOS 7.1 und höher|
|**Nicht verwaltete Dokumente in anderen verwalteten Apps zulassen**|Hiermit wird die Anzeige beliebiger Dokumente in verwalteten Apps zugelassen.|iOS 7.1 und höher|
|**Videokonferenz zulassen**|Zulassen von Videokonferenz-Apps wie Facetime auf dem Gerät.|Ja|
|**Nicht jugendfreie Inhalte im Medienstore zulassen**|Zulassen, dass das Gerät im Store auf nicht jugendfreie Inhalte zugreift.|Ja|

### Anwendungseinstellungen – Spiele

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Hinzufügung von Game Center-Freunden zulassen**|Ermöglichen, dass der Benutzer im Game Center Freunde hinzufügt.|Ja|
|**Spielen für mehrere Spieler zulassen**|Ermöglichen, dass der Benutzer Spiele für mehrere Spieler auf dem Gerät spielt.|Ja|

### Einstellungen für Gerätefunktionen - Hardware

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Kamera zulassen**|Gibt an, ob die Kamera des Geräts verwendet werden darf.|Ja|

### Einstellungen für Gerätefunktionen - Mobiltelefon

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Sprachroaming zulassen**|Zulassen des Sprachroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Ja|
|**Datenroaming zulassen**|Zulassen des Datenroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|Ja|
|**Globales Abrufen im Hintergrund beim Roaming zulassen**|Zulassen, dass das Gerät Daten wie E-Mails beim Roaming in einem Mobilfunknetz abruft.|Ja|

### Einstellungen für Gerätefunktionen - Funktionen

|Name der Einstellung|Details|iOS|
|----------------|-------|
|**Siri zulassen**|Verwendung des Sprach-Assistenten Siri auf dem Gerät zulassen.|Ja|
|**Siri bei gesperrtem Gerät zulassen**|Verwendung des Sprach-Assistenten Siri auf dem Gerät zulassen, während das Gerät gesperrt ist.|Ja|
|**Sprachwahl zulassen**|Die Verwendung des Features „Sprachwahlverfahren“ auf dem Gerät erlauben.|Ja|


### Einstellungen für kompatible und nicht kompatible Anwendungen
Geben Sie in der Liste der **kompatiblen &amp; nicht kompatiblen Apps** eine Liste kompatibler oder nicht kompatibler Apps mit den folgenden Informationen ein:

> [!NOTE]
> Eine einzelne Richtlinie kann nur eine Liste kompatibler oder eine Liste nicht kompatibler Apps enthalten. Sie können nicht beide Typen in derselben Richtlinie angeben.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Nichtkompatibilität melden, wenn Benutzer die aufgelisteten Apps installieren**|Listet die Apps auf, die nicht von Intune verwaltet werden und die Benutzer nicht installieren und ausführen dürfen.|
|**Nichtkompatibilität nicht melden, wenn Benutzer die aufgelisteten Apps installieren**|Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.|
|**Hinzufügen**|Fügt eine App zur ausgewählten Liste hinzu. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an. Weitere Informationen finden Sie unter **Angeben von URLs zu App-Stores** weiter unten in diesem Thema.|
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer CSV-Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber und App-URL.|
|**Bearbeiten**|Ermöglicht Ihnen das Bearbeiten von Name, Herausgeber und URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|

### Einstellungen für den Kioskmodus

|Name der Einstellung|Details|
|----------------|--------------------|
|**Wählen Sie eine verwalteten App aus, die ausgeführt werden darf, während sich das Gerät im Kiosk-Modus befindet**|Wählen Sie **Durchsuchen**, und geben Sie dann die verwaltete App oder eine App aus einem Store an, die ausgeführt werden darf, wenn sich das Gerät im Kioskmodus befindet. Andere Apps dürfen auf dem Gerät nicht ausgeführt werden. Weitere Informationen finden Sie unter **Angeben von URLs zu App-Stores** weiter unten in diesem Thema.|
|**Toucheingabe zulassen**|Aktiviert oder deaktiviert den Touchscreen des Geräts.|
|**Bildschirmdrehung zulassen**|Aktiviert oder deaktiviert die Funktion zum Ändern der Bildschirmausrichtung, wenn Sie das Gerät drehen.|
|**Lautstärkeregler zulassen**|Aktiviert oder deaktiviert die Verwendung der Lautstärkeregler am Gerät.|
|**Ruftonschalter zulassen**|Aktiviert oder deaktiviert den Ruftonschalter (Stummschaltung) am Gerät.|
|**Schaltfläche für Standby und Aktivieren zulassen**|Aktiviert oder deaktiviert die Taste für Standby/Aktivierung des Bildschirms am Gerät.|
|**Automatische Sperrung zulassen**|Aktiviert oder deaktiviert die automatische Sperrung des Geräts.|
|**Mono-/Audio aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Mono/Audio**.|
|**Voice-over aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **VoiceOver** , die den Text auf dem Gerätedisplay laut vorliest.|
|**Voice-over-Anpassungen aktivieren**|Aktiviert oder deaktiviert Voice-over-Anpassungen, die Ihnen das Anpassen der VoiceOver-Funktion ermöglichen (z. B. wie schnell Bildschirmtext vorgelesen wird).|
|**Zoom aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Zoom** , die Ihnen das Vergrößern des Texts auf dem Gerätedisplay durch Toucheingabe ermöglicht.|
|**Zoom-Anpassungen aktivieren**|Aktiviert oder deaktiviert Zoom-Anpassungen zum individuellen Einrichten der Zoomfunktion.|
|**Farben umkehren zulassen**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Farben umkehren** , die die Anzeige für Benutzer mit eingeschränkter Sehfähigkeit anpasst.|
|**Farbumkehr-Anpassungen aktivieren**|Aktiviert oder deaktiviert Farbumkehr-Anpassungen, mit denen Sie die Funktion zur Farbumkehr individuell einrichten können.|
|**Touch-Unterstützung aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Touch-Unterstützung** , die Benutzer bei der Ausführung von Bildschirmgesten unterstützt, die ihnen Schwierigkeiten bereiten.|
|**Touch-Unterstützungsanpassungen aktivieren**|Aktiviert oder deaktiviert Touch-Unterstützungsanpassungen, mit denen Sie die Funktion der Touch-Unterstützung individuell einrichten können.|
|**Sprachauswahl aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Sprachauswahl** , mit der ausgewählter Text vorgelesen werden kann.|
> [!NOTE] Die folgenden Hinweise gelten für Kioskmoduseinstellungen für iOS-Geräte:
> 
> -   Bevor Sie ein iOS-Gerät für den Kiosk-Modus konfigurieren können, müssen Sie das Gerät mithilfe des [Apple Configurator-Tools](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) oder des Geräteregistrierungs-Managers in den überwachten Modus versetzen. Weitere Informationen zum Apple Configurator-Tool finden Sie in der Apple-Dokumentation.
> -   Wenn die angegebene iOS-App nach der Bereitstellung der Konfigurationsrichtlinie installiert wird, wird das Gerät erst nach einem Neustart in den Kiosk-Modus versetzt.

### Referenzinformationen für kompatible und nicht kompatible Apps

#### Überwachen kompatibler und nicht kompatibler Apps
Im **Bericht über nicht kompatible Apps** können Sie sich über die Konformität zulässiger und blockierter Anwendungen informieren.

##### So führen Sie den Bericht über nicht kompatible Apps aus

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Berichte** &gt; **Bericht über nicht kompatible Apps**.

2.  Wählen Sie die Gerätegruppen aus, die Sie überprüfen möchten, geben Sie an, ob Sie nach kompatiblen und/oder nicht kompatiblen Apps suchen möchten, und wählen Sie dann **Bericht anzeigen**.

#### Angeben von URLs zu App-Stores
Um eine App-URL in der Liste mit kompatiblen und nicht kompatiblen Apps oder in der Option **Verwaltete App auswählen, die ausgeführt werden darf, wenn sich das Gerät im Kioskmodus befindet (nur iOS)** anzugeben, verwenden Sie das folgende Format:

Suchen Sie mithilfe einer Suchmaschine die gewünschte App im iTunes App Store, und öffnen Sie die Seite für die App.

Kopieren Sie die URL der Seite, und verwenden Sie diese als URL zur Konfiguration der Liste kompatibler oder nicht kompatibler Apps oder der App, die Sie im Kioskmodus ausführen möchten.

**Beispiel:** Suchen Sie nach **Microsoft Word für iPad**. Die URL, die Sie verwenden, ist **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE] Sie können auch die iTunes-Software verwenden, um die App zu suchen, und dann den Befehl **Link kopieren**, um die App-URL abzurufen.


## Benutzerdefinierte Richtlinieneinstellungen

Verwenden Sie die **benutzerdefinierte iOS-Richtlinie** von Microsoft Intune zum Bereitstellen von Einstellungen, die Sie mit dem Tool [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) für iOS-Geräte erstellt haben. Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren. Sie können dieses Konfigurationsprofil anschließend in eine benutzerdefinierte iOS-Richtlinie von Intune importieren und die Einstellungen für Benutzer und Geräte in Ihrer Organisation bereitstellen.

Diese Funktion soll es Ihnen ermöglichen, iOS-Einstellungen bereitzustellen, die nicht mit allgemeinen Intune-Konfigurationsrichtlinien konfigurierbar sind.

### Voraussetzungen
Bevor Sie beginnen, müssen Sie Apple Configurator installiert und eine Konfigurationsdatei mit den Einstellungen erstellt haben, die Sie für Benutzer oder Geräte bereitstellen möchten. Um Apple Configurator herunterzuladen und mehr darüber zu erfahren, besuchen Sie den [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)

> [!NOTE]
> Intune meldet nicht die Kompatibilität der einzelnen Einstellungen einer benutzerdefinierten iOS-Richtlinie. Die Gesamtkompatibilität der Richtlinie wird jedoch angegeben.

### Allgemeine Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für die benutzerdefinierte iOS-Richtlinie ein, damit Sie sie leichter in der Intune-Konsole bestimmen können.|
    |**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die benutzerdefinierte iOS-Richtlinie bietet, sowie weitere relevante Informationen, mit denen Sie danach suchen können.|

### Benutzerdefinierte Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
|**Name des benutzerdefinierten Konfigurationsprofils (zur Anzeige beim Benutzer)**|Geben Sie einen Namen für die Richtlinie an, der auf dem Gerät und in Intune-Richtlinienberichten angezeigt wird.|
|**Profil-Konfigurationsdatei**|Wählen Sie **Importieren**, und suchen Sie dann das mit Apple Configurator erstellte Konfigurationsprofil. **Hinweis:** Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der iOS-Version auf den Geräten kompatibel sind, für die Sie die benutzerdefinierte iOS-Richtlinie bereitstellen. Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie nach der **Konfigurationsprofilreferenz** und der **Verwaltungsprotokollreferenz für mobile Geräte** auf der [Apple Developer-Website](https://developer.apple.com/).|
    |**Details zum Konfigurationsprofil**|Zeigt den XML-Code des importierten Konfigurationsprofils an.|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO2-->


