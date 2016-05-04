---
title: Behandlung von Problemen mit dem Zugriff auf Unternehmensressourcen in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 40622ced-6029-4abf-873e-b51d2b51934c
author: Nbigman
---
# Behandlung von Problemen mit dem Zugriff auf Unternehmensressourcen in Microsoft Intune
Verwenden Sie die Fehler- und Statusinformationen Codes in diesem Thema, um Hilfe beim Beheben von Problemen bei einem [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] Aktion wird ein Fehlercode zurückgegeben.

Wenn diese Informationen nicht Ihr Problem behoben wird, finden Sie unter [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) Weitere Möglichkeiten, um Hilfe zu erhalten.

## Statuscodes für MDM-verwaltete Windows-Geräte

|Statuscode|Fehlermeldung|Aktion|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Installation läuft||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|Warten auf Inhalt||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|Inhalt wird abgerufen.|Mögliche Ursache: Der Auftragsstatus 30 gibt an, dass Fehler beim Herunterladen einer App durch einen Benutzer.<br /><br />Mögliche Ursachen können sein:<br /><br />Die Internetverbindung des Geräts wurde während des Downloads unterbrochen.<br /><br />Möglicherweise ist das Zertifikat abgelaufen, das bei der Registrierung für das Gerät ausgestellt wurde.<br /><br />Lösung:<br /><br />Starten Sie die Unternehmens-Apps-Anwendung in der Systemsteuerung auf dem Gerät, um zu prüfen, ob das Gerätezertifikat noch gültig ist. Andernfalls müssen Sie das Gerät erneut registrieren.<br /><br />Vergewissern Sie sich, dass das Gerät mit dem Internet verbunden ist, und rufen Sie die App erneut ab.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|Download abgeschlossen.||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Installation läuft||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|InstallationFehler aufgetreten.|Die heruntergeladene App konnte nicht installiert werden.<br /><br />Das Codesignaturzertifikat, mit dem die Anwendung signiert wurde, ist nicht auf dem Gerät vorhanden.<br /><br />Eine Frameworkabhängigkeit, von der die Anwendung abhängt, ist nicht auf dem Gerät installiert.<br /><br />Stellen Sie sicher, dass das Codesignaturzertifikat, mit dem die App signiert wurde, auf dem Gerät vorhanden ist. Lassen Sie sich zudem vom Administrator bestätigen, dass ein solches Zertifikat für alle im Unternehmen registrierten Windows RT-Geräte vorgesehen war.<br /><br />Falls der Installationsfehler aufgrund einer fehlenden Frameworkabhängigkeit aufgetreten ist, muss der Administrator die Anwendung erneut veröffentlichen und dabei das Framework zusammen mit dem Anwendungspaket verpacken.<br /><br />Das heruntergeladene Anwendungspaket ist kein gültiges Paket, wurde möglicherweise beschädigt oder ist nicht mit der Version des Betriebssystems auf dem Gerät kompatibel.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Installation erfolgreich.||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Deinstallation wird durchgeführt.||
|90 (APP_CI_ENFORCEMENT_ERROR)|Fehler beim Deinstallieren.||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Deinstallation erfolgreich.||
|110 (APP_CI_ENFORCEMENT_ERROR)|Inhaltshash stimmt nicht überein.||
|120 (APP_CI_ENFORCEMENT_ERROR)|Laden des SLK/der Seite nicht aktiviert.||
|130 (APP_CI_ENFORCEMENT_ERROR)|Fehler bei der Installation der MSADP-Lizenz.||
|Kein Statuscode (APP_CI_ENFORCEMENT_UNKNOWN)|Nicht zutreffend|Der Status ist aktuell unbekannt.|

## Zugriff auf Unternehmensressourcen (allgemeine Fehler)

|Statuscode|Hexadezimal-Fehlercode|Fehlermeldung|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|MDM CRP-Anforderung nicht gefunden.|
|-2016281102|0x87D1FDF2|NDES-URL wurde nicht gefunden|
|-2016281103|0x87D1FDF1|MDM CRP-Zertifikatinformationen nicht gefunden.|
|-2016281104|0x87D1FDF0|MDM CI-Zertifikatinformationen nicht gefunden.|
|-2016281105|0x87D1FDEF|Fehler beim Auswerten der Regel.|
|-2016281106|0x87D1FDEE|Nicht anwendbar, da bei der Konfliktauflösung verloren gegangen.|
|-2016281107|0x87D1FDED|Nicht unterstützte Einstellung für Ermittlungsquelle.|
|-2016281108|0x87D1FDEC|Referenzierte Einstellung in CI nicht gefunden.|
|-2016281109|0x87D1FDEB|Fehler bei der Konvertierung des Datentyps.|
|-2016281110|0x87D1FDEA|Ungültiger Parameter für CIM-Einstellung.|
|-2016281111|0x87D1FDE9|Für dieses Gerät nicht anwendbar.|
|-2016281112|0x87D1FDE8|Fehler bei Wiederherstellung.|
|-2016330905|0x87D13B67|App-Status ist unbekannt.|
|-2016330906|0x87D13B66|Die App wird verwaltet, wurde aber vom Benutzer entfernt.|
|-2016330907|0x87D13B65|Einlösungscode wird eingelöst.|
|-2016330908|0x87D13B64|Fehler bei der App-Installation.|
|-2016330909|0x87D13B63|Aktualisieren der App vom Benutzer abgelehnt.|
|-2016330910|0x87D13B62|Installieren der App vom Benutzer abgelehnt.|
|-2016330911|0x87D13B61|Der Benutzer hat die App installiert, bevor eine verwaltete App-Installation stattgefunden hat.|
|-2016330912|0x87D13B60|Die App ist für die Installation geplant, erfordert jedoch einen Einlösecode, um die Transaktion abschließen zu können.|
|-2016341109|0x87D1138B|iOS-Gerät hat einen Fehler zurückgegeben.|
|-2016341110|0x87D1138A|iOS-Gerät hat den Befehl aufgrund eines falschen Formats zurückgewiesen.|
|-2016341111|0x87D11389|iOS-Gerät hat einen unerwarteten Leerlaufstatus zurückgegeben.|
|-2016341112|0x87D11388|iOS-Gerät ist derzeit ausgelastet.|

## iOS-Geräte haben Fehler zurückgegeben.

|Statuscode|Hexadezimal-Fehlercode|Fehlermeldung|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|Interner Fehler.|
|-2016299112|0x87D1B798|Interner Fehler.|
|-2016300111|0x87D1B3B1|36001: (interner Fehler)|
|-2016300112|0x87D1B3B0|36000: Mobilfunknetz wurde bereits konfiguriert.|
|-2016301110|0x87D1AFCA|35002: Mehrere Schriftarten in einer einzelnen Nutzlast.|
|-2016301111|0x87D1AFC9|35001: Fehler bei der Installation der Schriftart.|
|-2016301112|0x87D1AFC8|35000: Ungültige Schriftartdaten.|
|-2016302109|0x87D1ABE3|34003: Kerberos-Prinzipalname ungültig.|
|-2016302110|0x87D1ABE2|34002: Kerberos-Prinzipalname fehlt.|
|-2016302111|0x87D1ABE1|34001: Ungültiges URL-Vergleichsmuster.|
|-2016302112|0x87D1ABE0|34000: Ungültiges App-ID-Übereinstimmungsmuster.|
|-2016304112|0x87D1A410|32000: Zu viele Apps.|
|-2016305111|0x87D1A029|31001: Einstellungen können nicht angewendet werden.|
|-2016305112|0x87D1A028|31000: Anmeldeinformationen können nicht angewendet werden.|
|-2016306111|0x87D19C41|30001: Zeitüberschreitung|
|-2016306112|0x87D19C40|30000: Fehler bei der Authentifizierung.|
|-2016307109|0x87D1985B|29003: Ungültige Zertifikatdaten.|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000: Gerät wird nicht überwacht.|
|-2016308110|0x87D19472|28002: Hintergrundbild kann nicht festgelegt werden.|
|-2016308111|0x87D19471|28001: Ungültiges Hintergrundbild.|
|-2016308112|0x87D19470|28000: Unbekanntes Element.|
|-2016310111|0x87D18CA1|26001: Verschlüsselung auf Dateiebene nicht unterstützt|
|-2016310112|0x87D18CA0|26000: Verschlüsselung auf Blockebene nicht unterstützt.|
|-2016311110|0x87D188BA|25002: Kann nicht entfernt werden.|
|-2016311111|0x87D188B9|25001: Kann nicht installiert werden.|
|-2016311112|0x87D188B8|25000: Ungültiges Profil.|
|-2016312109|0x87D184D3|24003: Ungültiges finales Profil.|
|-2016312110|0x87D184D2|24002: Ungültige Identitätsnutzlast.|
|-2016312111|0x87D184D1|24001: Attributverzeichnis kann nicht signiert werden.|
|-2016312112|0x87D184D0|24000: Attributverzeichnis kann nicht erstellt werden.|
|-2016313110|0x87D180EA|23002: Ungültiges Serverzertifikat.|
|-2016313111|0x87D180E9|23001: Ungültige Serverantwort.|
|-2016313112|0x87D180E8|23000: Ungültige Identität.|
|-2016314099|0x87D17D0D|22013: Ungültige Antwort auf PKI-Vorgang.|
|-2016314100|0x87D17D0C|22012: CA-Zertifikat kann nicht gespeichert werden.|
|-2016314101|0x87D17D0B|22011: CSR kann nicht generiert werden.|
|-2016314102|0x87D17D0A|22010: Temporäre Identität kann nicht gespeichert werden.|
|-2016314103|0x87D17D09|22009: Temporäre Identität kann nicht erstellt werden.|
|-2016314104|0x87D17D08|22008: Identität kann nicht erstellt werden.|
|-2016314105|0x87D17D07|22007: Ungültiges signiertes Zertifikat.|
|-2016314106|0x87D17D06|22006: Nicht genügend CACaps.|
|-2016314107|0x87D17D05|22005: Netzwerkfehler|
|-2016314108|0x87D17D04|22004: Zertifikatkonfiguration nicht unterstützt.|
|-2016314109|0x87D17D03|22003: Ungültige RA-Antwort.|
|-2016314110|0x87D17D02|22002: Ungültige CA-Antwort.|
|-2016314111|0x87D17D01|22001: Schlüsselpaar kann nicht generiert werden.|
|-2016314112|0x87D17D00|22000: Ungültige Schlüsselverwendung.|
|-2016315105|0x87D1791F|21007: Konto kann nicht überprüft werden.|
|-2016315106|0x87D1791E|21006: Zertifikat kann nicht entschlüsselt werden.|
|-2016315107|0x87D1791D|21005: Konto nicht eindeutig.|
|-2016315108|0x87D1791C|21004: Konto kann nicht erstellt werden.|
|-2016315109|0x87D1791B|21003: Kein Hostname.|
|-2016315110|0x87D1791A|21002: Verletzung der Verschlüsselungsrichtlinie vom Server.|
|-2016315111|0x87D17919|21001: Verletzung der Richtlinie vom Server.|
|-2016315112|0x87D17918|21000: Richtlinie kann nicht vom Server abgerufen werden.|
|-2016316110|0x87D17532|20002: Konto nicht eindeutig.|
|-2016316111|0x87D17531|20001: Kein Hostname.|
|-2016316112|0x87D17530|20000: Konto kann nicht erstellt werden.|
|-2016317110|0x87D1714A|19002: Konto nicht eindeutig.|
|-2016317111|0x87D17149|19001: Kein Hostname.|
|-2016317112|0x87D17148|19000: Konto kann nicht erstellt werden.|
|-2016318110|0x87D16D62|18002: Ungültige Anmeldeinformationen.|
|-2016318111|0x87D16D61|18001: Host nicht erreichbar.|
|-2016318112|0x87D16D60|18000: Unbekannter Fehler.|
|-2016319110|0x87D1697A|17002: Konto nicht eindeutig.|
|-2016319111|0x87D16979|17001: Kein Hostname.|
|-2016319112|0x87D16978|17000: Konto kann nicht erstellt werden.|
|-2016320110|0x87D16592|16002: Konto nicht eindeutig.|
|-2016320111|0x87D16591|16001: Kein Hostname.|
|-2016320112|0x87D16590|16000: Abonnement kann nicht erstellt werden.|
|-2016321109|0x87D161AB|15003: Ungültiges Zertifikat.|
|-2016321110|0x87D161AA|15002: Netzwerkkonfiguration kann nicht gesperrt werden.|
|-2016321111|0x87D161A9|15001: VPN kann nicht entfernt werden.|
|-2016321112|0x87D161A8|15000: VPN kann nicht installiert werden.|
|-2016322110|0x87D15DC2|14002: Cloudkonfiguration bereits vorhanden.|
|-2016322111|0x87D15DC1|14001: Gerät gesperrt.|
|-2016322112|0x87D15DC0|14000: Ungültiges Feld.|
|-2016323107|0x87D159DD|13005: Proxy kann nicht eingerichtet werden.|
|-2016323108|0x87D159DC|13004: EAP kann nicht eingerichtet werden.|
|-2016323109|0x87D159DB|13003: WLAN-Konfiguration kann nicht erstellt werden.|
|-2016323110|0x87D159DA|13002: Kennwort erforderlich.|
|-2016323111|0x87D159D9|13001: Benutzername erforderlich.|
|-2016323112|0x87D159D8|13000: Kann nicht installiert werden.|
|-2016324070|0x87D1561A|12042: Unbekannter Gebietsschemacode.|
|-2016324071|0x87D15619|12041: Unbekannter Sprachcode.|
|-2016324072|0x87D15618|12040: Anmeldung bei iTune Store erforderlich.|
|-2016324073|0x87D15617|12039: (Nicht belegt)|
|-2016324074|0x87D15616|12038: App nicht verwaltet.|
|-2016324075|0x87D15615|12037: Ungültiger Einlösecode.|
|-2016324076|0x87D15614|12036: App kann im aktuellen Zustand nicht entfernt werden.|
|-2016324077|0x87D15613|12035: App kann nicht erworben werden.|
|-2016324078|0x87D15612|12034: URL ist nicht HTTPS.|
|-2016324079|0x87D15611|12033: Ungültiges Manifest.|
|-2016324080|0x87D15610|12032: Zu viele Apps im Manifest.|
|-2016324081|0x87D1560F|12031: App-Installation deaktiviert.|
|-2016324082|0x87D1560E|12030: Ungültige URL.|
|-2016324083|0x87D1560D|12029: App nicht verwaltet.|
|-2016324084|0x87D1560C|12028: Auf Einlösung wird nicht gewartet.|
|-2016324085|0x87D1560B|12027: Dies ist keine App.|
|-2016324086|0x87D1560A|12026: App bereits in der Warteschlange.|
|-2016324087|0x87D15609|12025: App wurde bereits installiert.|
|-2016324088|0x87D15608|12024: App-Manifest konnte nicht überprüft werden.|
|-2016324089|0x87D15607|12023: App-ID konnte nicht überprüft werden.|
|-2016324090|0x87D15606|12022: Ungültiges Thema.|
|-2016324091|0x87D15605|12021: Ungültiger Anforderungstyp.|
|-2016324092|0x87D15604|12020: Nicht vom Server autorisiert.|
|-2016324093|0x87D15603|12019: Hinterlegter geheimer Schlüssel kann nicht kopiert werden.|
|-2016324094|0x87D15602|12018: Hinterlegte Schlüsselbunddaten können nicht kopiert werden.|
|-2016324095|0x87D15601|12017: Hinterlegter Schlüsselbund kann nicht erstellt werden.|
|-2016324096|0x87D15600|12016: Fehlende Identität.|
|-2016324097|0x87D155FF|12015: Pushtoken nicht abrufbar.|
|-2016324098|0x87D155FE|12014: Bereitstellungsprofil nicht verwaltet.|
|-2016324099|0x87D155FD|12013: Profil nicht verwaltet.|
|-2016324100|0x87D155FC|12012: MDM-Ersetzung stimmt nicht überein.|
|-2016324101|0x87D155FB|12011: Ungültige MDM-Konfiguration.|
|-2016324102|0x87D155FA|12010: Interner Inkonsistenzfehler.|
|-2016324103|0x87D155F9|12009: Ungültiges Austauschprofil.|
|-2016324104|0x87D155F8|12008: Falsch formatierte Anforderung.|
|-2016324105|0x87D155F7|12007: Nicht autorisiert.|
|-2016324106|0x87D155F6|12006: Umleitung abgelehnt.|
|-2016324107|0x87D155F5|12005: Zertifikat kann nicht gefunden werden.|
|-2016324108|0x87D155F4|12004: Ungültiges Push-Zertifikat.|
|-2016324109|0x87D155F3|12003: Ungültige Rückmeldung für Abfrage.|
|-2016324110|0x87D155F2|12002: Einchecken nicht möglich.|
|-2016324111|0x87D155F1|12001: Mehrere MDM-Instanzen.|
|-2016324112|0x87D155F0|12000: Ungültige Zugriffsrechte.|
|-2016325111|0x87D15209|11001: Benutzerdefinierter APN wurde bereits installiert.|
|-2016325112|0x87D15208|11000: VPN kann nicht installiert werden.|
|-2016326111|0x87D14E21|10001: Ungültiger Signaturgeber.|
|-2016326112|0x87D14E20|10000: Standardeinstellungen können nicht installiert werden.|
|-2016327106|0x87D14A3E|9006: Zertifikat ist keine Identität.|
|-2016327107|0x87D14A3D|9005: Zertifikat hat falsches Format.|
|-2016327108|0x87D14A3C|9004: Stammzertifikat kann nicht gespeichert werden.|
|-2016327109|0x87D14A3B|9003: WAPI-Daten können nicht gespeichert werden.|
|-2016327110|0x87D14A3A|9002: Zertifikat kann nicht gespeichert werden.|
|-2016327111|0x87D14A39|9001: Zu viele Zertifikate in einer Nutzlast.|
|-2016327112|0x87D14A38|9000: Ungültiges Kennwort.|
|-2016328112|0x87D14650|8000: Webclip kann nicht installiert werden.|
|-2016329105|0x87D1426F|7007: SMTP-Konto ist falsch konfiguriert.|
|-2016329106|0x87D1426E|7006: POP-Konto ist falsch konfiguriert.|
|-2016329107|0x87D1426D|7005: IMAP-Konto ist falsch konfiguriert.|
|-2016329108|0x87D1426C|7004: SMIME-Zertifikat ist ungültig.|
|-2016329109|0x87D1426B|7003: SMIME-Zertifikat nicht gefunden.|
|-2016329110|0x87D1426A|7002: Unbekannter Fehler bei der Überprüfung.|
|-2016329111|0x87D14269|7001: Ungültige Anmeldeinformationen.|
|-2016329112|0x87D14268|7000: Host nicht erreichbar.|
|-2016330110|0x87D13E82|6002: Abfrage kann nicht erstellt werden.|
|-2016330111|0x87D13E81|6001: Leere Zeichenfolge.|
|-2016330112|0x87D13E80|6000: Schlüsselbundsystemfehler|
|-2016331097|0x87D13AA7|5015: Toleranzperiode kann nicht festgelegt werden.|
|-2016331098|0x87D13AA6|5014: Kennung kann nicht festgelegt werden.|
|-2016331099|0x87D13AA5|5013: Kennung kann nicht gelöscht werden.|
|-2016331100|0x87D13AA4|5012: (Nicht belegt)|
|-2016331101||5011: Falsche Kennung.|
|-2016331102||5010: Gerät gesperrt.|
|-2016331103|0x87D13AA4|5009: (Nicht belegt)|
|-2016331104|0x87D13AA0|5008: Kennung zu aktuell.|
|-2016331105|0x87D13A9F|5007: Kennung abgelaufen.|
|-2016331106|0x87D13AA3|5006: Kennung muss Buchstaben enthalten.|
|-2016331107|0x87D13A9D|5005: Kennung muss Zahl enthalten.|
|-2016331108|0x87D13A9C|5004: Kennung enthält aufsteigende/absteigende Zeichen.|
|-2016331109|0x87D13A9B|5003: Kennung enthält sich wiederholende Zeichen.|
|-2016331110|0x87D13A9A|5002: Zu wenige komplexe Zeichen.|
|-2016331111|0x87D13A99|5001: Zu wenige eindeutige Zeichen.|
|-2016331112|0x87D13A98|5000: Kennung zu kurz.|
|-2016332093|0x87D136C3|4019: Mehrere App-Sperre-Nutzlasten.|
|-2016332094|0x87D136C2|4018: Mehrere APN- oder Mobilfunknetz-Nutzlasten.|
|-2016332095|0x87D136C1|4017: Mehrere globale HTTPProxy-Nutzlasten.|
|-2016332096|0x87D136C0|4016: (interner Fehler)|
|-2016332097|0x87D136BF|4015: Ersatzprofil enthält keine MDM-Nutzlast.|
|-2016332098|0x87D136BE|4014: Keine Geräteidentität verfügbar.|
|-2016332099|0x87D136BD|4013: Fehler bei Update.|
|-2016332100|0x87D136BC|4012: Profil kann nicht aktualisiert werden.|
|-2016332101|0x87D136BB|4011: Finales Profil ist kein Konfigurationsprofil.|
|-2016332102|0x87D136BA|4010: Aktualisiertes Profil hat nicht denselben Bezeichner.|
|-2016332103|0x87D136B9|4009: Gerät gesperrt.|
|-2016332104|0x87D136B8|4008: Nicht übereinstimmende Zertifikate.|
|-2016332105|0x87D136B7|4007: Dateiformat nicht erkannt.|
|-2016332106|0x87D136B6|4006: Datum für Profilentfernung liegt in der Vergangenheit.|
|-2016332107|0x87D136B5|4005: Kennung nicht kompatibel.|
|-2016332108|0x87D136B4|4004: Installation durch Benutzer abgebrochen.|
|-2016332109|0x87D136B3|4003: Profile für Installation nicht in Warteschlange.|
|-2016332110|0x87D136B2|4002: Doppelte UUID.|
|-2016332111|0x87D136B1|4001: Fehler bei der Installation.|
|-2016332112|0x87D136B0|4000: Profil kann nicht analysiert werden.|
|-2016333111|0x87D132C9|3001: Inkonsistente Wertvergleichserkennung (interner Fehler).|
|-2016333112|0x87D132C8|3000: Inkonsistente Einschränkungserkennung (interner Fehler).|
|-2016334108|0x87D12EE4|2004: Nicht unterstützter Feldwert.|
|-2016334109|0x87D12EE3|2003: Ungültiger Datentyp in Feld.|
|-2016334110|0x87D12EE2|2002: Pflichtfeld fehlt.|
|-2016334111|0x87D12EE1|2001: Nicht unterstützte Nutzlastversion.|
|-2016334112|0x87D12EE0|2000: Nutzlast falsch formatiert.|
|-2016335102|0x87D12B02|1010: Nicht unterstützter Feldwert.|
|-2016335103|0x87D12B01|1009: Fehler bei Profilinstallation.|
|-2016335104|0x87D12B00|1008: Nicht eindeutige Nutzlastbezeichner.|
|-2016335105|0x87D12AFF|1007: Nicht eindeutige UUIDs.|
|-2016335106|0x87D12AFE|1006: Entschlüsseln nicht möglich.|
|-2016335107|0x87D12AFD|1005: Leeres Profil.|
|-2016335108|0x87D12AFC|1004: Ungültige Signatur.|
|-2016335109|0x87D12AFB|1003: Ungültiger Datentyp in Feld.|
|-2016335110|0x87D12AFA|1002: Pflichtfeld fehlt.|
|-2016335111|0x87D12AF9|1001: Nicht unterstützte Profilversion.|
|-2016335112|0x87D12AF8|1000: Falsche Profilsyntax.|

## OMA-Antwortcodes

|Statuscode|Hexadezimal-Fehlercode|Fehlermeldung|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): Zugriff auf Zertifikat verweigert|
|-2016344009|0x87D10837|(1403): das Zertifikat wurde nicht gefunden.|
|-2016344010|0x87D10836|DCMO(1402): Der Vorgang ist fehlgeschlagen.|
|-2016344011|0x87D10835|Dcmo(1401): Der Benutzer hat den Vorgang bei Aufforderung abgelehnt|
|-2016344012|0x87D10834|DCMO(1400): Fehler|
|-2016344108|0x87D107D4|Dcmo(1204): Gerätefunktion ist deaktiviert, und Benutzer wieder zu aktivieren|
|-2016344109|0x87D107D3|Dcmo(1203): Gerätefunktion ist deaktiviert, und Benutzer ist zur Reaktivierung nicht zulässig.|
|-2016344110|0x87D107D2|Dcmo(1202): Aktivierung wurde erfolgreich ausgeführt, doch die Gerätefunktion ist derzeit getrennt.|
|-2016344111|0xF3FB4D95|Dcmo(1201): Aktivierung wurde erfolgreich ausgeführt, und die Gerätefunktion ist derzeit angefügt.|
|-2016344112|0x87D107D0|DCMO(1200): Vorgang wurde erfolgreich ausgeführt.|
|-2016345595|0x87D10205|Syncml(517): Die Antwort auf einen unteilbaren Befehl war zu groß für in einer einzelnen Nachricht.|
|-2016345596|0x87D10204|Syncml(516): Befehl wurde in atomare Element und bei Atomic ist fehlgeschlagen. Der Befehl konnte nicht zurückgesetzt werden.|
|-2016345598|0x87D10202|Syncml(514): Der SyncML-Befehl wurde nicht ausgeführt, da der Vorgang bereits vor der Verarbeitung des Befehls abgebrochen wurde.|
|-2016345599|0x87D10201|Syncml(513): Der Empfänger nicht unterstützt oder die angegebene Version des SyncML-Synchronisierungsprotokolls in der SyncML-Abfragemeldung verweigert.|
|-2016345600|0x87D10200|Syncml(512): Während der synchronisierungssitzung ist ein Fehler aufgetreten.|
|-2016345601|0x87D101FF|Syncml(511): Schwerwiegender Fehler auf dem Server beim Verarbeiten der Anforderung.|
|-2016345602|0x87D101FE|Syncml(510): Fehler beim Verarbeiten der Anforderung. Ursache des Fehlers ist ein Fehler im Datenspeicher des Empfängers.|
|-2016345603|0x87D101FD|Syncml(509): Für zukünftige Verwendung reserviert.|
|-2016345604|0x87D101FC|Syncml(508): Ein Fehler aufgetreten, der der aktuelle synchronisierungszustand des Clients mit dem Server muss aktualisiert werden.|
|-2016345605|0x87D101FB|Syncml(507): Der Fehler verursacht alle SyncML-Befehle in einem unteilbaren Element ausgeführt.|
|-2016345606|0x87D101FA|Syncml(506): Beim Verarbeiten der Anforderung ist ein Fehler aufgetreten.|
|-2016345607|0x87D101F9|Syncml(505): Der Empfänger nicht unterstützt oder weist Sie zurück zur Unterstützung der angegebenen Version der SyncML DTD in der SyncML-Abfragemeldung.|
|-2016345608|0x87D101F8 =|Syncml(504): Der Empfänger beim fungieren als Gateway oder Proxy, erhielt nicht rechtzeitige eine Antwort von den angegebenen URI (z. B. HTTP, FTP, LDAP) oder einem anderen hilfsempfänger (z. B. DNS) auf den beim Versuch, den Vorgang upstreamempfänger.|
|-2016345609|0x87D101F7|Syncml(503): Der Empfänger ist derzeit nicht verarbeitet die Anforderung aufgrund einer zeitweisen Überlastung oder Wartung des Empfängers.|
|-2016345610|0x87D101F6|Syncml(502): Empfing der Empfänger, fungieren als Gateway oder Proxy eine ungültige Antwort vom Upstreamserver Empfänger Zugriff auf, um die Anforderung erfüllen.|
|-2016345611|0x87D101F5|Syncml(501): Der Empfänger unterstützt den zur Erfüllung der Anforderung erforderlichen Befehl nicht.|
|-2016345612|0x87D101F4|Syncml(500): Der Empfänger hat eine unerwartete Bedingung konnte die Anforderung festgestellt.|
|-2016345684|0x87D101AC|Syncml(428): Verschieben Sie Fehler beim.|
|-2016345685|0x87D101AB|Syncml(427): Übergeordnete kann gelöscht werden, da es sich um untergeordnete Elemente enthält.|
|-2016345686|0x87D101AA|Syncml(426): Unvollständiges Element wurde nicht angenommen.|
|-2016345687|0x87D101A9|Syncml(425): Der angeforderte Befehl ist fehlgeschlagen, da der Absender auf dem Empfänger keine ausreichende zugriffssteuerungsberechtigung (ACL) verfügt.|
|-2016345688|0x87D101A8|Syncml(424): Das aufgeteilte Objekt wurde empfangen, aber die Größe des empfangenen Objekts im ersten Teil der Größe nicht entsprach.|
|-2016345689|0x87D101A7|Syncml(423): Der angeforderte Befehl ist fehlgeschlagen, da "der vorläufig gelöschte" Element zuvor "Festplatte gelöscht" auf dem Server wurde.|
|-2016345690|0x87D101A6|Syncml(422): Der angeforderte Befehl konnte auf dem Server, weil das CGI-Skript im LocURI fehlerhaft war.|
|-2016345691|0x87D101A5|Syncml(421): Der angeforderte Befehl konnte auf dem Server, weil die angegebene suchgrammatik unbekannt war.|
|-2016345692|0x87D101A4|Syncml(420): Der Empfänger ist nicht genügend Speicherplatz für die restlichen Synchronisierungsdaten vorhanden.|
|-2016345693|0x87D101A3|Syncml(419): Die Clientanforderung entstand ein Konflikt, der Serverbefehls gelöst wurde.|
|-2016345694|0x87D101A2|Syncml(418): Der angeforderte put- oder Add-Befehl ist fehlgeschlagen, da das Ziel bereits vorhanden ist.|
|-2016345695|0x87D101A1|Syncml(417): Fehler bei der Anforderung zu diesem Zeitpunkt und dem Absender sollte später erneut.|
|-2016345696|0x87D101A0|Syncml(416): Die Anforderung ist fehlgeschlagen, da die angeforderte Bytegröße in der Anforderung zu groß war.|
|-2016345697|0x87D1019F|Syncml(415): Nicht unterstützter Typ oder Format.|
|-2016345698|0x87D1019E|Syncml(414): Der angeforderte Befehl ist fehlgeschlagen, da der Ziel-URI zu lang ist für der Empfänger zu verarbeiten ist.|
|-2016345699|0x87D1019D|Syncml(413): Der Empfänger wird abgelehnt wird, um den angeforderten Befehl auszuführen, da das angeforderte Element größer ist als der für die Verarbeitung ist.|
|-2016345700|0x87D1019C|Syncml(412): Der angeforderte Befehl konnte nicht auf dem Empfänger, da sie unvollständig oder falsch formatiert war.|
|-2016345701|0x87D1019B|Syncml(411): Der angeforderte Befehl bytegrößen- oder bytelängenangabe im Meta-Elementtyp beizufügen.|
|-2016345702|0x87D1019A|Syncml(410): Das angeforderte Ziel ist nicht mehr auf dem Empfänger und weiterleitungs-URI ist unbekannt.|
|-2016345703|0x87D10199|Syncml(409): Die Anforderung konnte kein Update-Konflikt zwischen dem Client und-Server Versionen der Daten.|
|-2016345704|0x87D10198|Syncml(408): Eine erwartete Meldung wurde nicht innerhalb der festgelegten Zeitraums empfangen.|
|-2016345705|0x87D10197|Syncml(407): Der angeforderte Befehl ist fehlgeschlagen, da vom Absender richtige Authentifizierungsdaten bereitgestellt werden muss.|
|-2016345706|0x87D10196|Syncml(406): Der angeforderte Befehl ist fehlgeschlagen, da eine optionale Funktion in der Anforderung nicht unterstützt.|
|-2016345707|0x87D10195|Syncml(405): Der angeforderte Befehl ist auf dem Ziel nicht zulässig.|
|-2016345708|0x87D10194|Syncml(404): Das angeforderte Ziel wurde nicht gefunden.|
|-2016345709|0x87D10193|Syncml(403): Der angeforderte Befehl konnte nicht ausgeführt, aber der Empfänger verstanden.|
|-2016345710|0x87D10192|Syncml(402): Der angeforderte Befehl ist fehlgeschlagen, da die richtige Bezahlung erforderlich ist.|
|-2016345711|0x87D10191|Syncml(401): Der angeforderte Befehl ist fehlgeschlagen, da vom Absender richtige Authentifizierungsdaten bereitgestellt werden muss.|
|-2016345712|0x87D10190|Syncml(400): Der angeforderte Befehl konnte nicht aufgrund eines Syntaxfehlers in der Befehl ausgeführt werden.|
|-2016345807|0x87D10131|Syncml(305): Das angeforderte Ziel muss über den angegebenen Proxy-URI zugegriffen werden.|
|-2016345808|0x87D10130|Syncml (304): Der angeforderte SyncML-Befehl wurde auf dem Ziel nicht ausgeführt.|
|-2016345809|0x87D1012F|Syncml(303): Das angeforderte Ziel besitzt einen anderen URI finden.|
|-2016345810|0x87D1012E|Syncml(302): Das angeforderte Ziel wurde vorübergehend an einen anderen URI verschoben.|
|-2016345811|0x87D1012D|Syncml(301): Das angeforderte Ziel besitzt einen neuen URI.|
|-2016345812|0x87D1012C|Syncml(300): Das angeforderte Ziel ist eine Anzahl von mehreren alternativen angeforderte Ziel.|
|-2016345896|0x87D100D8|Syncml(216): Ein Befehl wurde in atomare Element und bei Atomic ist fehlgeschlagen. Der Befehl konnte nicht zurückgesetzt werden.|
|-2016345897|0x87D100D7|Syncml(215): Ein Befehl wurde nicht ausgeführt, da der Benutzer und der Benutzer hat nicht die Auswahl zu bestätigen.|
|-2016345898|0x87D100D6|Syncml(214): Der Vorgang abgebrochen. Der SyncML-Befehl wurde erfolgreich abgeschlossen, aber in der Sitzung werden keine weiteren Befehle verarbeitet.|
|-2016345899|0x87D100D5|Syncml(213): Aufgeteiltes Element akzeptiert und gepuffert|
|-2016345900|0x87D100D4|Syncml(212): Authentifizierung akzeptiert. Für den Rest der Synchronisierungssitzung ist keine weitere Authentifizierung erforderlich. Dieser Antwortcode kann nur als Antwort auf eine Anforderung verwendet werden, in der die Anmeldeinformationen bereitgestellt wurden.|
|-2016345901|0x87D100D3|Syncml(211): Element wurde nicht gelöscht. Das angeforderte Element wurde nicht gefunden. Es wurde möglicherweise zuvor gelöscht.|
|-2016345902|0x87D100D2|Syncml(210): Ohne archivieren löschen. Die Antwort gibt an, dass die angeforderten Daten erfolgreich gelöscht wurden, ohne sie jedoch vor dem Löschen zu archivieren, da diese OPTIONALE Funktion von der Implementierung nicht unterstützt wurde.|
|-2016345903|0x87D100D1|Konflikt durch Duplizieren behoben. Die Antwort gibt an, dass die Anforderung einen Aktualisierungskonflikt verursacht hat, der durch Duplizieren der in der Serverdatenbank erstellten Clientdaten behoben wurde. Die Antwort enthält im Statuselement beide Ziel-URI des Duplikats. Darüber hinaus wird bei einer bidirektionalen Synchronisierung ein Add-Befehl mit der duplizierten Datendefinition zurückgegeben.|
|-2016345904|0x87D100D0|Konflikt behoben, wobei der Clientbefehl "gewinnt". Die Antwort gibt an, dass ein Aktualisierungskonflikt aufgetreten ist, der behoben wurde, indem der Clientbefehl gewinnt.|
|-2016345905|0x87D100CF|Konflikt durch Zusammenführen behoben. Die Antwort gibt an, dass die Anforderung ein Konflikts erzeugt hat, der durch Zusammenführen der Client- und Serverinstanzen der Daten behoben wurde. Die Antwort enthält im Statuselement die Ziel- und Quell-URL. Darüber hinaus wird ein Replace-Befehl mit zusammengeführten Daten zurückgegeben.|
|-2016345906|0x87D100CE|Die Antwort gibt an, dass nur ein Teil des Befehls abgeschlossen wurde. Wenn der restliche Befehl später abgeschlossen werden kann, SOLLTE nach Abschluss ein weiterer entsprechender Statuscode für die Abschlussanforderung erstellt werden.|
|-2016345907|0x87D100CD|Die Quelle SOLLTE ihren Inhalt aktualisieren. Dem Absender der Anforderung wird mitgeteilt, dass der Inhalt synchronisiert werden SOLLTE, um eine aktuelle Version zu erhalten.|
|-2016345908|0x87D100CC|Die Anforderung wurde erfolgreich abgeschlossen, aber es wurden keine Daten zurückgegeben. Der Antwortcode wird auch als Reaktion auf einen Get-Befehl zurückgegeben, wenn das Ziel keinen Inhalt hat.|
|-2016345909|0x87D100CB|Nicht-autoritative Antwort. Auf die Anforderung reagiert eine andere Entität als der vorgesehene Empfänger. Die Antwort wird nur zurückgegeben, wenn die Anforderung zu einem 200-Antwortcode vom autorisierenden Empfänger geführt hätte.|
|-2016345910|0x87D100CA|Zur Verarbeitung angenommen. Die Anforderung zur Remoteausführung einer Anwendung oder zum Warnen eines Benutzers oder einer Anwendung wurde erfolgreich durchgeführt.|
|-2016345911|0x87D100C9|Das angeforderte Element wurde hinzugefügt.|
|-2016345912|0x87D100C8|Der SyncML-Befehl wurde erfolgreich abgeschlossen.|
|-2016346011|0x87D10065|Der angegebene SyncML-Befehl wird ausgeführt, wurde aber noch nicht abgeschlossen.|

## Siehe auch
[Aktivieren des Zugriffs auf Unternehmensressourcen mit Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md)
[Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md)


<!--HONumber=Mar16_HO4-->


