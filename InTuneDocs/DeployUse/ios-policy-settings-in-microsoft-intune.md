---
title: iOS-Richtlinieneinstellungen | Microsoft Intune
description: "Erstellen Sie Richtlinien, die Einstellungen und Funktionen auf iOS-Geräten steuern, die Sie mit Intune verwalten."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cac39b60226939334032d954eb49d1417493b28d
ms.openlocfilehash: 00e3a1b65c8475384bb05e64a4ef9f5d9de348ff


---

# iOS-Richtlinieneinstellungen in Microsoft Intune

Intune bietet eine Reihe integrierter allgemeiner Einstellungen, die Sie auf iOS-Geräten konfigurieren können. Darüber hinaus können Sie das Apple Configurator-Tool verwenden, um benutzerdefinierte Einstellungen zu erstellen, die nicht von Intune verfügbar sind.

## Allgemeine Konfigurationsrichtlinieneinstellungen

Verwenden Sie die allgemeine **iOS-Konfigurationsrichtlinie** von Microsoft Intune zum Konfigurieren von Einstellungen für:

-   **Allgemeine Geräte- und Sicherheitseinstellungen**: Wählen Sie aus einer Liste mit vordefinierten Einstellungen, mit denen Sie verschiedene Features und Funktionen auf dem Gerät steuern können.

-   **Kioskmodus**: Sie können ein Gerät so konfigurieren, dass nur bestimmte Features funktionieren. Beispielsweise können Sie festlegen, dass auf einem Gerät nur eine von Ihnen angegebene verwaltete App ausgeführt werden kann, oder Sie können die Lautstärkeregler eines Geräts deaktivieren. Diese Einstellungen können für ein Demomodell eines Geräts oder ein Gerät verwendet werden, das nur eine bestimmte Funktion ausführen soll, z. B. ein Point-of-Sale-Gerät.

-   **Kompatible und nicht kompatible Apps**: Geben Sie eine Liste von Apps an, die in Ihrem Unternehmen kompatibel oder nicht kompatibel sind. Auf Android- und iOS-Geräten können Sie mit dem **Bericht über nicht kompatible Apps** überprüfen, ob die von Benutzern installierten Apps zu den von Ihnen in der Liste als kompatibel angegebenen Apps gehören (die Installation der App kann jedoch nicht blockiert werden).

> [!TIP]
> Sie können Bestimmungen konfigurieren. Beispielsweise müssen Benutzer zustimmen, dass die auf ihrem Gerät installierten Apps (einschließlich persönlicher Apps) beurteilt werden und dass nicht kompatible Apps entweder blockiert oder als nicht kompatibel gemeldet werden. Benutzer müssen diese Bestimmungen akzeptieren, bevor sie ihr Gerät registrieren und Apps über das Unternehmensportal abrufen können. Weitere Informationen zur Verwendung von Nutzungsbedingungen finden Sie unter [Einstellungen für Nutzungsbedingungsrichtlinien in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Wenn die gesuchte Einstellung nicht in diesem Thema enthalten ist, können Sie sie ggf. mithilfe einer benutzerdefinierten iOS-Richtlinie erstellen, die Ihnen das Importieren von Einstellungen erlaubt, die Sie mit dem [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)-Tool erstellt haben. Weitere Informationen finden Sie weiter unten in diesem Thema unter „Benutzerdefinierte Richtlinieneinstellungen“.

### Sicherheitseinstellungen
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Gibt an, ob der Benutzer ein Kennwort eingeben muss, um auf sein Gerät zuzugreifen.|
|**Erforderlicher Kennworttyp**|Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.|
|**Erforderliche Anzahl komplexer Zeichen im Kennwort**|Gibt die Anzahl von Symbolzeichen (wie **#** oder **@**) an, die im Kennwort enthalten sein müssen.|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zeichen an, die das Kennwort enthalten muss.|
|**Einfache Kennwörter zulassen**|Lässt einfache Kennwörter wie **0000** und **1234** zu.|
|**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**|Gibt die Anzahl fehlerhafter Anmeldeversuche an, bevor das Gerät durch diese Einstellung zurückgesetzt wird.|
|**Minuten Inaktivität vor erneuter Anforderung des Kennworts**<sup>1</sup>|Gibt an, wie lange das Gerät im Leerlauf bleiben kann, bevor der Benutzer sein Kennwort erneut eingeben muss.|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|
|**Kennwortverlauf speichern**|Gibt an, ob der Benutzer zuvor verwendete Kennwörter wiederverwenden kann.|
|**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.|
|**Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird**<sup>1</sup>|Geben Sie die Anzahl der Minuten an, bevor die Anzeige des Geräts deaktiviert wird.|
|**Fingerabdruckentsperrung zulassen**|Lässt das Entsperren des Geräts mittels Fingerabdruck zu.|
<sup>1</sup> Wenn Sie für iOS-Geräte die Einstellungen **Minuten der Inaktivität, bevor der Bildschirm ausgeschaltet wird** und **Minuten Inaktivität vor erneuter Anforderung des Kennworts** konfigurieren, werden sie nacheinander angewendet. Wenn Sie beispielsweise den Wert für beide Einstellungen auf **5** Minuten einstellen, wird der Bildschirm automatisch nach 5 Minuten deaktiviert, und das Gerät wird nach weiteren 5 Minuten gesperrt. Wenn der Benutzer den Bildschirm jedoch manuell deaktiviert, wird die zweite Einstellung sofort angewendet. Im selben Beispiel wird das Gerät 5 Minuten später gesperrt, nachdem der Benutzer den Bildschirm deaktiviert hat.

### Systemeinstellungen
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Bildschirmfoto zulassen**|Ermöglicht es dem Benutzer, den Bildschirminhalt als Bild zu erfassen.|
|**Kontrollcenter auf Sperrbildschirm zulassen**|Erlaubt dem Benutzer den Zugriff auf die Kontrollcenter-App, während das Gerät gesperrt ist.|
|**Benachrichtigungsansicht auf Sperrbildschirm zulassen**|Erlaubt dem Benutzer den Zugriff auf die Benachrichtigungsansicht, ohne dass das Gerät entsperrt werden muss.|
|**Ansicht "Heute" auf Sperrbildschirm zulassen**|Ermöglicht dem Benutzer das Anzeigen von Benachrichtigungen, während das Gerät gesperrt ist.|
|**Nicht vertrauenswürdige TLS-Zertifikate zulassen**|Hiermit werden nicht vertrauenswürdige TLS-Zertifikate (Transport Layer Security) auf dem Gerät zugelassen.|
|**Übermitteln von Diagnosedaten zulassen**|Ermöglicht dem Gerät das Senden von Diagnosedaten an Apple.|
|**Passbook bei Sperre zulassen**|Erlaubt dem Benutzer den Zugriff auf die Passbook-App, während das Gerät gesperrt ist.|

### Cloudeinstellungen für Dokumente und Daten
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Sicherung in iCloud zulassen**|Ermöglicht es dem Benutzer, das Gerät in iCloud zu sichern.|
|**Dokumentsynchronisierung in iCloud zulassen**|Erlaubt die Dokument- und Schlüssel-/Wertsynchronisierung in Ihrem iCloud-Speicher.|
|**Photo Stream-Synchronisierung in iCloud zulassen**|Erlaubt, dass Fotos auf dem Gerät mit iCloud synchronisiert werden.|
|**Verschlüsselte Sicherung erforderlich**|Fordert an, dass Gerätesicherungen verschlüsselt werden.|
|**Datensynchronisierung mit iCloud durch verwaltete Apps zulassen**|Ermöglicht es Apps, die Sie mit Intune verwalten, Daten mit dem iCloud-Konto des Benutzers zu synchronisieren.|
|**Fortsetzung von Aktivitäten durch HandOff auf einem anderen Gerät zulassen**|Ermöglicht es dem Benutzer, die Arbeit, die er auf einem iOS-Gerät gestartet hat, auf einem anderen iOS- oder Mac OS X-Gerät fortzusetzen.|
|**iCloud-Fotofreigabe zulassen**|Ermöglicht es dem Benutzer, die iOS-Funktion zur Fotofreigabe zuzulassen.|
|**iCloud-Fotomediathek zulassen**|Ermöglicht es dem Benutzer, Fotos auf iCloud zu speichern. Wenn diese Funktion deaktiviert ist, werden bereits auf iCloud gespeicherten Fotos entfernt.|

### Anwendungseinstellungen für den Browser
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Safari zulassen**|Geben Sie an, ob der Safari-Browser auf dem Gerät verwendet werden kann.|
|**AutoAusfüllen zulassen**|Ermöglicht es dem Benutzer, die Einstellungen für AutoVervollständigen im Browser zu ändern.|
|**Popupblocker zulassen**|Aktivieren oder deaktivieren Sie den Popupblocker des Browsers.|
|**Cookies zulassen**|Ermöglicht dem Browser die Verwendung von Cookies.|
|**JavaScript zulassen**|Ermöglichen, dass Java-Skripts im Browser ausgeführt werden.|
|**Betrugswarnung zulassen**|Ermöglicht die Verwendung von Betrugswarnungen im Browser.|

### Anwendungseinstellungen für Apps
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Installation von Apps zulassen**|Ermöglicht dem Gerät den Zugriff auf den App Store und die Installation von Apps.|
|**Kennwort für den Zugriff auf den Anwendungsspeicher erforderlich**|Erzwingt die Kennworteingabe vom Benutzer, bevor er den App Store besuchen kann.|
|**In-App-Einkäufe zulassen**|Zulassen, dass Einkäufe im Store in einer ausgeführten App erfolgen.|
|**Verwaltete Dokumente in anderen nicht verwalteten Apps zulassen**|Hiermit wird die Anzeige von Unternehmensdokumenten in beliebigen Apps zugelassen.<br>**Beispiel:** Sie möchten verhindern, dass Benutzer Dateien aus der OneDrive-App in Dropbox speichern. Legen Sie für diese Einstellung „Nein“ fest. Sobald das Gerät die Richtlinie empfängt (z. B. nach einem Neustart), ist kein Speichern mehr möglich.|
|**Nicht verwaltete Dokumente in anderen verwalteten Apps zulassen**|Hiermit wird die Anzeige beliebiger Dokumente in verwalteten Apps zugelassen.|
|**Videokonferenz zulassen**|Lässt Videokonferenz-Apps wie FaceTime auf dem Gerät zu.|
|**Benutzern das Einstufen von Autoren neuer Unternehmens-Apps als vertrauenswürdig gestatten**|Ermöglicht es dem Benutzer zu entscheiden, ob Apps, die nicht aus dem App Store heruntergeladen wurden, vertraut werden soll.|


### Anwendungseinstellungen für Spiele
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Hinzufügung von Game Center-Freunden zulassen**|Ermöglichen, dass der Benutzer im Game Center Freunde hinzufügt.|
|**Spielen für mehrere Spieler zulassen**|Ermöglichen, dass der Benutzer Spiele für mehrere Spieler auf dem Gerät spielt.|

### Anwendungseinstellungen für Medieninhalte
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Bewertungsregion**|Wählen Sie eine Region aus, und wählen Sie die maximale Bewertung aus, die Benutzer für **Filme**, **Fernsehsendungen** und **Apps** herunterladen können.|
|**Nicht jugendfreie Inhalte im Medienstore zulassen**|Zulassen, dass das Gerät im Store auf nicht jugendfreie Inhalte zugreift.|
|**Benutzern das Herunterladen von iBooks Store-Inhalt mit der Kennzeichnung „Erotik“ gestatten**|Gestattet dem Benutzer das Herunterladen von Büchern aus der Kategorie „Erotik“.|


### Einstellungen für Gerätefunktionen der Hardware
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Kamera zulassen**|Gibt an, ob die Kamera des Geräts verwendet werden darf.|
|**Handgelenkerkennung für gekoppelte Apple Watch-Geräte erzwingen**|Wenn diese Funktion aktiviert ist, zeigt die Apple Watch keine Benachrichtigungen an, wenn sie nicht getragen wird.|
|**Kopplungskennwort für ausgehende AirPlay-Anforderungen erforderlich**|Erfordert ein Kopplungskennwort, wenn der Benutzer AirPlay zum Streamen von Inhalten auf andere Apple-Geräte verwendet.|

### Einstellungen für Gerätefunktionen von Mobiltelefonen
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Sprachroaming zulassen**|Zulassen des Sprachroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|
|**Datenroaming zulassen**|Zulassen des Datenroamings, wenn das Gerät in einem Mobilfunknetz verwendet wird.|
|**Globales Abrufen im Hintergrund beim Roaming zulassen**|Zulassen, dass das Gerät Daten wie E-Mails beim Roaming in einem Mobilfunknetz abruft.|

### Einstellungen für Gerätefunktionen von Features
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|-------|
|**Siri zulassen**|Verwendung des Sprach-Assistenten Siri auf dem Gerät zulassen.|
|**Siri bei gesperrtem Gerät zulassen**|Verwendung des Sprach-Assistenten Siri auf dem Gerät zulassen, während das Gerät gesperrt ist.|
|**Sprachwahl zulassen**|Die Verwendung des Features „Sprachwahlverfahren“ auf dem Gerät erlauben.|
|**Airdrop für verwaltete Apps nicht zulassen**|Verhindert, dass verwaltete Apps Daten über  Airdrop senden.|


### Einstellungen für kompatible und nicht kompatible Anwendungen
Geben Sie in der Liste der **kompatiblen und nicht kompatiblen Apps** anhand der folgenden Informationen eine Liste kompatibler oder nicht kompatibler Apps an.

> [!NOTE]
> Eine einzelne Richtlinie kann nur eine Liste kompatibler Apps oder eine Liste nicht kompatibler Apps enthalten. Sie können nicht beide Typen in derselben Richtlinie angeben.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Nichtkompatibilität melden, wenn Benutzer die aufgelisteten Apps installieren**|Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.|
|**Nichtkonformität melden, wenn Benutzer die nicht aufgelisteten Apps installieren**|Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.|
|**Hinzufügen**|Fügt der ausgewählten Liste eine App hinzu. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an. Weitere Informationen finden Sie unter „Angeben von URLs zu App-Stores“ weiter unten in diesem Thema.|
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer durch Trennzeichen getrennten Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber, App-URL.|
|**Bearbeiten**|Ermöglicht das Bearbeiten des Namens, Herausgebers und der URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|

### Einstellungen für den Kioskmodus

|Name der Einstellung|Details|
|----------------|--------------------|
|**Wählen Sie eine verwalteten App aus, die ausgeführt werden darf, während sich das Gerät im Kiosk-Modus befindet**|Wählen Sie **Durchsuchen** aus, und geben Sie dann die verwaltete App oder eine App aus einem Store an, die ausgeführt werden darf, wenn sich das Gerät im Kioskmodus befindet. Andere Apps dürfen auf dem Gerät nicht ausgeführt werden. Weitere Informationen finden Sie unter „Angeben von URLs zu App-Stores“ weiter unten in diesem Thema.|
|**Toucheingabe zulassen**|Aktiviert oder deaktiviert den Touchscreen des Geräts.|
|**Bildschirmdrehung zulassen**|Aktiviert oder deaktiviert das Ändern der Bildschirmausrichtung, wenn der Benutzer das Gerät dreht.|
|**Lautstärkeregler zulassen**|Aktiviert oder deaktiviert die Verwendung der Lautstärkeregler am Gerät.|
|**Ruftonschalter zulassen**|Aktiviert oder deaktiviert den Ruftonschalter (Stummschaltung) am Gerät.|
|**Schaltfläche für Standby und Aktivieren zulassen**|Aktiviert oder deaktiviert die Schaltfläche für das Standby/die Aktivierung des Bildschirms am Gerät.|
|**Automatische Sperrung zulassen**|Aktiviert oder deaktiviert die automatische Sperrung des Geräts.|
|**Mono-/Audio aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Mono/Audio**.|
|**Voice-over aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **VoiceOver**, die den Text auf dem Gerätedisplay laut vorliest.|
|**Voice-over-Anpassungen aktivieren**|Aktiviert oder deaktiviert Voice-over-Anpassungen, die dem Benutzer das Anpassen der VoiceOver-Funktion ermöglichen (z. B. wie schnell Bildschirmtext laut vorgelesen wird).|
|**Zoom aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Zoom**, die dem Benutzer das Vergrößern des Inhalts auf dem Gerätedisplay durch Tippen ermöglicht.|
|**Zoom-Anpassungen aktivieren**|Aktiviert oder deaktiviert Zoom-Anpassungen zur individuellen Verwendung der Zoomfunktion.|
|**Farben umkehren zulassen**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Farben umkehren**, die die Anzeige für Benutzer mit eingeschränkter Sehfähigkeit anpasst.|
|**Farbumkehr-Anpassungen aktivieren**|Aktiviert oder deaktiviert Farbumkehr-Anpassungen, mit denen der Benutzer die Funktion zur Farbumkehr individuell verwenden kann.|
|**Touch-Unterstützung aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Touch-Unterstützung**, die den Benutzer bei der Ausführung von Bildschirmgesten unterstützt, die ihm u. U. Schwierigkeiten bereiten.|
|**Touch-Unterstützungsanpassungen aktivieren**|Aktiviert oder deaktiviert Touch-Unterstützungsanpassungen, mit denen der Benutzer die Touch-Unterstützung individuell verwenden kann.|
|**Sprachauswahl aktivieren**|Aktiviert oder deaktiviert die Barrierefreiheitseinstellung **Auswahl vorlesen**, mit der der vom Benutzer ausgewählte Text laut vorgelesen werden kann.|
> [!NOTE]
> Die folgenden Hinweise gelten für Kiosk-Moduseinstellungen für iOS-Geräte:
>
> -   Bevor Sie ein iOS-Gerät für den Kioskmodus konfigurieren können, müssen Sie das Gerät mithilfe des [Apple Configurator-Tools](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) oder des Geräteregistrierungs-Managers in den überwachten Modus versetzen. Weitere Informationen zum Apple Configurator-Tool finden Sie in der Apple-Dokumentation.
> -   Wenn die angegebene iOS-App nach der Bereitstellung der Konfigurationsrichtlinie installiert wird, wird das Gerät erst nach einem Neustart in den Kioskmodus versetzt.

### Referenzinformationen für kompatible und nicht kompatible Apps

Im **Bericht über nicht kompatible Apps** können Sie sich über die Konformität zulässiger und blockierter Anwendungen informieren.

##### So führen Sie den Bericht über nicht kompatible Apps aus

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Berichte** &gt; **Bericht über nicht kompatible Apps**.

2.  Wählen Sie die Gerätegruppen aus, die Sie überprüfen möchten, geben Sie an, ob Sie nach kompatiblen und/oder nicht kompatiblen Apps suchen möchten, und wählen Sie dann **Bericht anzeigen** aus.

#### Angeben von URLs zu App-Stores
Um eine App-URL in der Liste mit kompatiblen und nicht kompatiblen Apps oder in der Option **Verwaltete App auswählen, die ausgeführt werden darf, wenn sich das Gerät im Kioskmodus befindet (nur iOS)** anzugeben, verwenden Sie das folgende Format:

1. Suchen Sie mithilfe einer Suchmaschine die gewünschte App im iTunes App Store, und öffnen Sie die Seite für die App.

2. Kopieren Sie die URL der Seite, und verwenden Sie diese als URL zur Konfiguration der Liste kompatibler oder nicht kompatibler Apps oder der App, die Sie im Kioskmodus ausführen möchten.

**Beispiel:** Suchen Sie nach **Microsoft Word für iPad**. Die URL, die Sie verwenden, ist **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Sie können auch die iTunes-Software verwenden, um die App zu suchen, und dann den Befehl **Link kopieren** , um die App-URL abzurufen.

### Registrierungseinstellungen
Alle Einstellungen gelten für iOS 7.1 und höher.

|Name der Einstellung|Details|
|----------------|--------------------|
|**Aktivierungssperre zulassen, wenn sich das Gerät im überwachten Modus befindet**|Aktiviert die Aktivierungssperre auf überwachten iOS-Geräten.|

### Einstellungen für den überwachten Modus
Die folgenden Einstellungen können auf Geräten mit iOS 7.1 und höher konfiguriert werden, die sich im überwachten Modus befinden.

### Einstellungen für den überwachten Modus für Gerätebeschränkungen

|Name der Einstellung|Details|
|----------------|--------------------|
|**Kontoänderung zulassen**|Benutzern die Änderung der Kontoeinstellungen zulassen, z. B. der E-Mail-Konfigurationen.|
|**Änderungen an Mobilfunk-Datennutzungseinstellungen für Apps zulassen**|Gestatten Sie Benutzern die Steuerung, welche Apps Mobilfunkdaten verwenden dürfen.|
|**Verwendung der Option zum Löschen aller Inhalte und Einstellungen auf dem Gerät zulassen**|Erlaubt dem Benutzer die Verwendung der Option zum Löschen aller Inhalte und Einstellungen auf dem Gerät.|
|**Aktivierung von Einschränkungen in den Geräteeinstellungen durch den Benutzer zulassen**|Erlaubt dem Benutzer das Konfigurieren von Geräteeinschränkungen (Jugendschutz) auf dem Gerät.|
|**Steuerung der Geräte, mit denen ein iOS-Gerät gekoppelt werden kann, durch Hostkopplung zulassen**|Ermöglicht die Hostkopplung, damit der Administrator steuern kann, mit welchen Geräten ein iOS-Gerät gekoppelt werden kann.|
|**Installation von Konfigurationsprofilen und Zertifikaten durch den Benutzer zulassen**|Ermöglicht dem Benutzer die Installation von Konfigurationsprofilen und Zertifikaten.|
|**Änderung von Gerätenamen zulassen**|Ermöglicht es dem Benutzer, den Namen des Geräts zu ändern.|
|**Änderung von Kennungen zulassen**|Ermöglicht das Hinzufügen, Ändern oder Entfernen des Gerätekennworts.|
|**Apple Watch-Kopplung zulassen**|Ermöglicht die Gerätekopplung mit einer Apple Watch.|
|**Änderung der Benachrichtigungseinstellungen zulassen**|Ermöglicht es dem Benutzer, die Benachrichtigungseinstellungen des Geräts zu ändern.|
|**Änderung von Hintergrundbildern zulassen**|Ermöglicht es dem Benutzer, das Hintergrundbild auf dem Gerät zu ändern.|

### Einstellungen für den überwachten Modus für Funktionsbeschränkungen

|Name der Einstellung|Details|
|----------------|--------------------|
|**AirDrop zulassen**|Lässt die Verwendung von AirDrop zum Austauschen von Inhalten mit Geräten in der Nähe zu.|
|**Abfrage von benutzergeneriertem Inhalt aus dem Internet durch Siri zulassen**|Erlaubt Siri den Zugriff auf Websites, um Fragen zu beantworten.|
|**Siri-Filter für anstößige Ausdrücke verwenden**|Verhindert, dass Siri anstößige Ausdrücke diktiert oder verwendet.|
|**Zurückgeben von Ergebnissen aus dem Internet über die Spotlight-Suche zulassen**|Erlaubt der Spotlight-Suche, eine Verbindung mit dem Internet herzustellen, um weitere Ergebnisse bereitzustellen.|
|**Suche nach Wortdefinitionen zulassen**|Aktiviert die iOS-Funktion, mit der Sie ein Wort markieren und dessen Definition nachschlagen können.|
|**Tastaturwortvorschläge zulassen**|Ermöglicht Tastaturwortvorschläge, die Wörter vorschlagen, die der Benutzer möglicherweise verwenden möchte.|
|**Autokorrektur zulassen**|Ermöglicht dem Gerät die automatische Korrektur von falsch geschriebenen Wörter.|
|**Rechtschreibprüfung über Tastatur zulassen**|Aktiviert die Rechtschreibprüfung des Geräts.|
|**Tastaturkurzbefehle zulassen**|Ermöglicht die Verwendung von Tastaturkurzbefehlen.|

### Einstellungen für den überwachten Modus für App-Beschränkungen

|Name der Einstellung|Details|
|----------------|--------------------|
|**Änderung von Vertrauensstellungseinstellungen für Unternehmens-Apps zulassen**||
|**Installation von Apps nur mit Apple Configurator und iTunes zulassen**||
|**Automatische App-Downloads zulassen**||
|**Änderungen an den Einstellungen der App „Meine Freunde suchen“ zulassen**|Gestatten Sie Benutzern das Ändern von Einstellungen für die App „Meine Freunde suchen“.|
|**Zugriff auf iBooks Store zulassen**|Gestatten Sie Benutzern die Suche nach Büchern im iBooks-Store sowie den Kauf gefundener Bücher.|
|**Verwendung der Nachrichten-App auf dem Gerät zulassen**|Gestatten Sie die Verwendung der Nachrichten-App zum Senden von SMS.|
|**Verwendung von Podcasts zulassen**|Ermöglicht die Verwendung Podcast-App.|
|**Verwendung des Music-Diensts zulassen**|Ermöglicht die Verwendung der Apple Music-App.|
|**iTunes Radio-Dienst zulassen**|Ermöglicht die Verwendung der iTunes Radio-App.|
|**Apple News zulassen**|Ermöglicht die Verwendung der Apple News-App.|
|**Game Center zulassen**|Gestatten Sie die Verwendung der Game Center-App.|


### Einblenden oder Ausblenden von Apps

Verwenden Sie die **Liste von aus- und eingeblendeten Apps**, um auf überwachten Geräten mit iOS 9.3 oder höher Folgendes zu steuern:

- Angeben einer Liste von Apps, die vor Benutzern verborgen werden. Benutzer können diese Apps weder anzeigen noch starten.
- Angeben einer Liste von Apps, die Benutzer anzeigen und starten können. Es können keine anderen Apps angezeigt oder gestartet werden.


#### So erstellen Sie eine Liste von aus- oder eingeblendeten Apps

Geben Sie die folgenden Einstellungen an:

|Name der Einstellung|Details|
|-|-|
|**Liste von aus- und eingeblendeten Apps**|Aktivieren Sie diese Einstellung, wenn Sie eine Liste von aus- oder eingeblendeten Apps erstellen möchten.|
|**Ausblenden der aufgelisteten Apps vor Benutzern**|Wählen Sie diese Option aus, wenn Sie eine Liste von Apps erstellen möchten, die vor Benutzern ausgeblendet werden.|
|**Einblenden ausschließlich der aufgelisteten Apps für Benutzer**|Wählen Sie diese Option aus, wenn Sie eine Liste von Apps erstellen möchten, die Benutzern angezeigt werden.<br>Beim Erstellen dieses Listentyps werden alle anderen Apps mit Ausnahme der iOS-**Einstellungen** und **Telefon**-Apps (für iPhones) ausgeblendet.<br>Sie müssen der Liste darüber hinaus das Unternehmensportal und alle Apps hinzufügen, die Sie bereitgestellt haben und über Intune verwalten.|
|**Hinzufügen**|Fügt eine App zur ausgewählten Liste hinzu.<br>Für die Liste von ausgeblendeten Apps müssen Sie den **Namen**, den **Herausgeber** und die **App-URL oder Paket-ID** jeder App angeben, die Sie ausblenden möchten.<br>Für die Liste von eingeblendeten Apps können Sie entweder **eine verwaltete App auswählen**, wodurch Ihnen eine Liste von Apps zum Auswählen angezeigt wird, die Sie über Intune verwalten. Alternativ können Sie eine Store-App auswählen, wobei Sie den **Namen**, den **Herausgeber** und die **App-URL oder Paket-ID** jeder App angeben müssen, die Sie anzeigen möchten.|
|**Anwendungen importieren**|Importiert eine Liste von Apps, die Sie in einer CSV-Datei angegeben haben. Verwenden Sie in der Datei das Format Anwendungsname, Herausgeber und App-URL.|
|**Bearbeiten**|Ermöglicht Ihnen das Bearbeiten von Name, Herausgeber und URL der ausgewählten App.|
|**Löschen**|Löscht die ausgewählte App aus der Liste.|

#### App-Informationen für integrierte iOS-Apps

Verwenden Sie die Informationen in dieser Liste zur Identifizierung des Namens, des Herausgebers und der Paket-ID der integrierten iOS-Apps, die Sie ein- oder ausblenden möchten. Wenn Sie alle Apps in der Liste ein- oder ausblenden möchten, können Sie die nachstehenden Daten in eine Textdatei mit der Erweiterung **.csv** kopieren. Verwenden Sie anschließend die Option **Anwendungen importieren**, um alle Apps gleichzeitig zu importieren.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## Benutzerdefinierte Richtlinieneinstellungen

Verwenden Sie die **benutzerdefinierte iOS-Richtlinie** von Microsoft Intune, um Einstellungen, die Sie mit dem [Apple Configurator-Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) erstellt haben, auf iOS-Geräten bereitzustellen. Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren. Sie können dieses Konfigurationsprofil anschließend in eine benutzerdefinierte iOS-Richtlinie von Intune importieren und die Einstellungen für Benutzer und Geräte in Ihrer Organisation bereitstellen.

Diese Funktion ermöglicht die Bereitstellung von iOS-Einstellungen, die nicht mit allgemeinen Intune-Konfigurationsrichtlinien konfigurierbar sind.

### Voraussetzungen
Bevor Sie beginnen, müssen Sie Apple Configurator installiert und eine Konfigurationsdatei mit den Einstellungen erstellt haben, die Sie für Benutzer oder Geräte bereitstellen möchten. Um Apple Configurator herunterzuladen und mehr darüber zu erfahren, besuchen Sie den [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12).

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
|**Profil-Konfigurationsdatei**|Wählen Sie **Importieren** aus, und suchen Sie dann das mit Apple Configurator erstellte Konfigurationsprofil. **Hinweis:** Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der iOS-Version auf den Geräten kompatibel sind, für die Sie die benutzerdefinierte iOS-Richtlinie bereitstellen. Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie auf der [Apple Developer-Website](https://developer.apple.com/) nach der **Referenz zu Konfigurationsprofilen** und der **Referenz zum Protokoll für die Verwaltung mobiler Geräte**.|
    |**Details zum Konfigurationsprofil**|Zeigt den XML-Code des importierten Konfigurationsprofils an.|

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO5-->


