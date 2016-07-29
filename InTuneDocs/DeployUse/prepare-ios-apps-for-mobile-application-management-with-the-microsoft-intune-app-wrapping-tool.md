---
title: "Umschließen von iOS-Apps mit dem App Wrapping Tool | Microsoft Intune"
description: "In diesem Thema lernen Sie, Ihre iOS-Apps zu umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19a5b8f8260bace2bbe3626da3df281306f53024
ms.openlocfilehash: ebd68513da55b8bb1715d2c82636abf791cae1ff


---

# Vorbereiten von iOS-Apps für die Verwaltung mobiler Anwendungen mit dem Intune App Wrapping Tool
Verwenden Sie das **Microsoft Intune App Wrapping Tool für iOS** zur Änderung des Verhaltens interner iOS-Apps, indem Sie die Features der App einschränken, ohne den eigentlichen Code der App zu ändern.

Das Tool ist eine Mac OS-Befehlszeilenanwendung, die einen Wrapper um eine App erstellt (sie umschließt). Sobald eine App verarbeitet wurde, können Sie die App-Funktionalität mit von Ihnen konfigurierten [Verwaltungsrichtlinien für mobile Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ändern.

Informationen zum Herunterladen des Tools finden Sie unter [Microsoft Intune App Wrapping Tool für iOS](http://www.microsoft.com/en-us/download/details.aspx?id=45218).

## Schritt 1: Erfüllen der Voraussetzungen für die Verwendung des App Wrapping Tools

|Anforderungen|Weitere Informationen|
|---------------|--------------------------------|
|Unterstütztes Betriebssystem und Toolset|Sie müssen das App Wrapping Tool auf einem Mac mit OS X 10.8.5 oder höher ausführen, auf dem die Toolsetversion XCode 5 oder höher installiert wurde.|
|Signaturzertifikat und Bereitstellungsprofil|Sie müssen ein Apple-Signaturzertifikat und ein Bereitstellungsprofil besitzen. Weitere Informationen hierzu finden Sie in Ihrer [Apple-Entwicklerdokumentation](https://developer.apple.com/).|
|Verarbeiten einer App mit dem App Wrapping Tool|Apps müssen von Ihrem Unternehmen oder einem unabhängigen Softwareanbieter (ISV) entwickelt und signiert werden. Mit diesem Tool können Sie keine Apps aus dem Apple Store bearbeiten. Apps müssen für iOS 7.0 oder höher geschrieben sein. Apps müssen im PIE-Format (positionsunabhängige ausführbare Datei) vorliegen. Weitere Informationen zum PIE-Format finden Sie in Ihrer Apple-Entwicklerdokumentation. Die App muss die Erweiterung **.app** oder **.ipa** aufweisen.|
|Apps, die vom App Wrapping Tool nicht verarbeitet werden können|Verschlüsselte Apps, nicht signierte Apps und Apps mit erweiterten Dateiattributen.|
|Apps, die die Azure Active Directory-Bibliothek (ADAL) verwenden|Wenn Ihre App ADAL verwendet, muss in der App die ADAL-Version 1.0.2 oder höher integriert sein, und Entwickler müssen ihrer App Zugriff auf die Intune MAM-Ressource (mobile Anwendungsverwaltung) gewähren.<br /><br />Informationen zur Verwendung von ADAL finden Sie in diesem Artikel unter [Informationen für Apps, die die Azure Active Directory-Bibliothek verwenden](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library).|
|Festlegen von Berechtigungen für Ihre App|Sie müssen Berechtigungen festlegen, die der App zusätzliche Berechtigungen und Funktionen über die typischerweise gewährten hinaus erteilen, bevor Sie die App umschließen. Anleitungen finden Sie unter [Festlegen von App-Berechtigungen](#setting-app-entitlements).|

## Schritt 2: Installieren des App Wrapping Tools

1.  Laden Sie von der Seite **Microsoft Intune App Wrapping Tool für iOS** im [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=45218) die Installationsdatei für das App Wrapping Tool auf einen Mac-Computer herunter.

2.  Doppelklicken Sie auf dem Mac-Computer auf die Installationsdatei **Microsoft Intune App Wrapping Tool for iOS.dmg**.

3.  Wählen Sie **Agree**, um den Endbenutzer-Lizenzvertrag (EULA) zu akzeptieren. Das Installationsprogramm wird bereitgestellt und auf dem Mac-Computer angezeigt.

4.  Öffnen Sie das Installationsprogramm, und kopieren Sie die angezeigten Dateien in einen neuen Ordner auf dem Mac-Computer. Sie können jetzt das bereitgestellte Installationslaufwerk trennen.

    Sie können nun das App Wrapping Tool ausführen.

## Schritt 3: Ausführen des App Wrapping Tools

1.  Öffnen Sie auf dem Mac-Computer ein Terminalfenster, und navigieren Sie zu dem Ordner, in dem Sie die Dateien gespeichert haben. Da sich die ausführbare Datei im Paket befindet, müssen Sie den Befehl wie folgt ausführen:
```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Eigenschaft|Weitere Informationen|
  |------------|--------------------|
  |**-h**|Zeigt die verfügbaren Befehlszeileneigenschaften für das App Wrapping Tool an.|
  |**-i**|Gibt den Pfad und den Dateinamen der Eingabe-App an.|
  |**-o**|Gibt den Pfad zum Speichern der verarbeiteten App an.|
  |**-p**|Gibt den Pfad zu Ihrem Bereitstellungsprofil für iOS-Apps an.|
  |**-c**|Gibt den SHA1-Hash des Signaturzertifikats an.|
  |**-a**|Client-ID der Eingabe-App (im GUID-Format), wenn die App Azure Active Directory-Bibliotheken (optional) verwendet.|
  |**-r**|Umleitungs-URI der Eingabe-App, wenn die App Azure Active Directory-Bibliotheken (optional) verwendet.|
  |**-v**|Ausgabe ausführlicher Meldungen an die Konsole (optional).|

2. Nach Abschluss der Verarbeitung wird eine Nachricht wie **Anwendungs-Wrapping erfolgreich** angezeigt.

    Falls ein Fehler auftritt, finden Sie unter [Fehlermeldungen](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) hilfreiche Informationen.

3.  Die per Wrapping umschlossene Anwendung wird im Ausgabeordner gespeichert, den Sie zuvor angegeben haben. Jetzt können Sie die App in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hochladen und eine Richtlinie für die mobile Anwendungsverwaltung zuordnen.

    > [!IMPORTANT]
    > Sie müssen die App als neue App hochladen. Eine ältere, entpackte Version der App kann nicht aktualisiert werden.

    Sie können die App jetzt für Ihre [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Gruppen bereitstellen, und die App wird nun auf dem Gerät mit den von Ihnen angegebenen App-Einschränkungen ausgeführt.

## Fehlermeldungen und Protokolldateien
Verwenden Sie die folgende Informationen, um Problemen mit dem App Wrapping Tool zu behandeln.

### Fehlermeldungen
Wenn das App Wrapping Tool nicht erfolgreich abgeschlossen wurde, wird eine der folgenden Fehlermeldungen angezeigt:

|Fehlermeldung|Weitere Informationen|
|-----------------|--------------------|
|Sie müssen ein gültiges iOS-Bereitstellungsprofil angeben.|Ihr Bereitstellungsprofil ist möglicherweise nicht gültig. Stellen Sie sicher, dass Sie die richtigen Berechtigungen für die Geräte haben und dass Ihr Profil korrekt auf Entwicklung oder Verteilung abzielt. Ihr Bereitstellungsprofil ist möglicherweise auch abgelaufen.|
|Geben Sie einen gültigen Eingabe-Anwendungsnamen an.|Stellen Sie sicher, dass der angegebene Eingabe-App-Name richtig ist.|
|Geben Sie einen gültigen Pfad für die Ausgabeanwendung an.|Stellen Sie sicher, dass der Pfad zur Ausgabe-App, den Sie angeben, vorhanden und korrekt ist.|
|Geben Sie ein gültiges Eingabe-Bereitstellungsprofil an.|Stellen Sie sicher, dass Sie einen gültigen Bereitstellungs-Profilnamen und die Erweiterung angegeben haben. In Ihrem Bereitstellungsprofil fehlen Berechtigungen, oder Sie haben möglicherweise nicht die Befehlszeilenoption **–p** hinzugefügt.|
|Die angegebene Eingabeanwendung wurde nicht gefunden. Geben Sie einen gültigen Eingabe-App-Namen und -Pfad an.|Stellen Sie sicher, dass der Pfad Ihrer Eingabe-App gültig und vorhanden ist. Stellen Sie sicher, dass die Eingabe-App an diesem Speicherort vorhanden ist.|
|Die angegebene Eingabe-Bereitstellungsprofildatei wurde nicht gefunden. Geben Sie eine gültige Eingabe-Bereitstellungsprofildatei an.|Stellen Sie sicher, dass der Pfad der Eingabe-Bereitstellungsprofildatei gültig ist und die angegebene Datei vorhanden ist.|
|Der angegebene Ausgabeordner für die Anwendung wurde nicht gefunden. Geben Sie einen gültigen Pfad für die Ausgabeanwendung an.|Stellen Sie sicher, dass der von Ihnen angegebene Ausgabepfad gültig und vorhanden ist.|
|Die Ausgabe-App hat keine IPA-Erweiterung.|Nur Apps mit der Erweiterung **.app** und **.ipa** werden vom App Wrapping Tool akzeptiert. Stellen Sie sicher, dass die Ausgabedatei eine gültige Erweiterung hat.|
|Es wurde ein ungültiges Signaturzertifikat angegeben. Geben Sie ein gültiges Signaturzertifikat von Apple an.|Stellen Sie sicher, dass Sie das richtige Signaturzertifikat aus dem Apple-Entwicklerportal heruntergeladen haben. Das Zertifikat kann auch abgelaufen sein. Wenn Ihr Apple-Zertifikat und das Bereitstellungsprofil verwendet werden können, um eine App in Xcode ordnungsgemäß zu signieren, sind sie für das App Wrapping Tool gültig.|
|Die angegebene Eingabeanwendung ist ungültig. Geben Sie eine gültige Anwendung an.|Stellen Sie sicher, dass Sie über eine gültige iOS-Anwendung verfügen, die als APP- oder IPA-Datei kompiliert wurde.|
|Die angegebene Eingabeanwendung ist verschlüsselt. Geben Sie eine gültige unverschlüsselte Anwendung an.|Das App Wrapping Tool unterstützt keine verschlüsselten Apps. Geben Sie eine unverschlüsselte App an.|
|Die angegebene Eingabeanwendung liegt nicht im PIE-Format (Positionsunabhängige ausführbare Datei) vor. Geben Sie eine gültige Anwendung im PIE-Format an.|PIE-Apps können beim Ausführen an einer zufälligen Speicheradresse geladen werden, was Sicherheitsvorteile haben kann. Weitere Informationen finden Sie in der Apple-Entwicklerdokumentation.|
|Die angegebene Eingabe-App wurde bereits umschlossen. Geben Sie eine App ohne Wrapping an.|Sie können eine App, die vom Tool bereits verarbeitet wurde, nicht erneut verarbeiten. Wenn Sie eine App erneut verarbeiten möchten, führen Sie das Tool mit der ursprünglichen Version der App aus.|
|Die angegebene Eingabeanwendung ist nicht signiert. Geben Sie eine gültige signierte Anwendung an.|Das App Wrapping Tool erfordert, dass Apps signiert sind. Lesen Sie in der Entwicklerdokumentation, wie Sie eine umschlossene App signieren.|
|Die angegebene Eingabeanwendung muss im IPA- oder APP-Format vorliegen.|Nur APP- und IPA-Erweiterungen werden vom App Wrapping Tool akzeptiert. Stellen Sie sicher, dass Ihre Eingabedatei eine gültige Erweiterung hat und als APP- oder IPA-Datei kompiliert wurde.|
|Die angegebene Eingabe-App wurde bereits umschlossen und verwendet die neueste Version der Richtlinienvorlage.|Das App Wrapping Tool umschließt eine vorhandene umschlossene App mit der neuesten Version der Richtlinienvorlage nicht erneut.|
|Die angegebene Azure Active Directory Client-ID ist keine korrekt geformte GUID. Geben Sie eine gültige Client-ID an.|Wenn Sie den Client-ID-Parameter verwenden, stellen Sie sicher, dass Sie eine gültige Client-ID im GUID-Format bereitgestellt haben.|
|Die angegebene Azure Active Directory-Antwort-URI ist keine korrekt geformte URI. Geben Sie eine gültige Antwort-URI an.|Wenn Sie die Antwort-URI-Befehlszeileneigenschaft verwenden, stellen Sie sicher, dass Sie eine gültige Antwort-URI bereitgestellt haben.|
|WARNUNG: Sie haben kein SHA1-Zertifikathash angegeben. Stellen Sie sicher, dass die umschlossene Anwendung vor der Bereitstellung signiert wird.|Stellen Sie sicher, dass Sie ein gültiges SHA-Hash angeben (mithilfe der Befehlszeileneigenschaft **–c** ).|

### Protokolldateien für das App Wrapping Tool
Anwendungen, die mit dem App Wrapping Tool umschlossen wurden, generieren Protokolle, die in die iOS-Clientgerätekonsole geschrieben werden. Diese Informationen sind hilfreich in Situationen, in denen Sie Probleme mit der App haben und diagnostizieren möchten, ob das Problem mit dem App Wrapping Tool zusammenhängt. Führen Sie die folgenden Schritte aus, um die Informationen abzurufen:

1.  Reproduzieren Sie das Problem durch Ausführen der App.

2.  Sammeln Sie die Konsolenausgabe mit den folgenden Apple-Anweisungen für das [Debuggen bereitgestellter iOS-Apps](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Filtern Sie die gespeicherten Protokolle nach der Ausgabe von App-Einschränkungen, indem Sie das folgende Skript in die Konsole eingeben:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Sie können die gefilterten Protokolle an Microsoft senden.

    > [!NOTE]
    > In der Protokolldatei stellt das Element "Buildversion" die Version von Xcode dar.

    Umschlossene Apps geben auch Benutzern die Möglichkeit, die Protokolle direkt vom Gerät per E-Mail zu versenden, falls die App abstürzt. Benutzer können das Protokoll an Sie senden, damit Sie es überprüfen und ggf. an Microsoft weiterleiten.

## Informationen für Apps, die die Azure Active Directory-Bibliothek verwenden
Die Informationen in diesem Abschnitt gelten nur für Apps, die die Azure Active Directory-Bibliothek (ADAL) verwenden. Wenn Sie nicht wissen, ob Ihre Anwendung diese Bibliothek verwendet, wenden Sie sich an den Entwickler der Anwendung.

In der App muss mindestens ADAL 1.0.2 integriert sein.

Für Apps, die ADAL verwenden, muss Folgendes zutreffen:

-   Die App muss mindestens ADAL-Version 1.0.2 integriert haben.

-   Entwickler müssen ihrer App Zugriff auf die Intune MAM-Ressource (Mobile Application Management, mobile Anwendungsverwaltung) gewähren, wie unter [Für Apps, die ADAL verwenden, zu befolgende Schritte](#steps-to-follow-for-apps-that-use-adal) beschrieben.

### Übersicht über die Bezeichner, die Sie abrufen müssen
Apps, die ADAL verwenden, müssen über das Azure-Verwaltungsportal registriert werden, um zwei eindeutige IDs für ihre App zu erhalten:

|ID|Weitere Informationen|Standardwert|
|--------------|--------------------|-----------------|
|**Client-ID**|Eine eindeutige GUID wird für jede App generiert, nachdem sie bei Azure Active Directory registriert wurde.<br /><br />Wenn Sie die spezifische Client-ID der App kennen, können Sie diesen Wert angeben. Andernfalls muss der Standardwert verwendet werden.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Umleitungs-URI**|Ein URI-Wert, den Entwickler bei der Registrierung ihrer App bei Azure Active Directory angeben können, um sicherzustellen, dass die Authentifizierungstoken speziell für diesen Endpunkt zurückgegeben werden.<br /><br />Das Angeben einer Umleitungs-URI ist ein optionaler Parameter für das App Wrapping Tool. Wenn sie nicht angegeben ist, wird eine Standard-URI verwendet.|urn:ietf:wg:oauth:2.0:oob|


### Für Apps, die ADAL verwenden, zu befolgende Schritte

1.  Lesen Sie [Übersicht über die Bezeichner, die Sie abrufen müssen](#overview-of-identifiers-you-need-to-get), um die abzurufenden Werte zu ermitteln.

2.  Konfigurieren Sie den Zugriff auf die Verwaltung von mobilen Anwendungen in Azure Active Directory auf folgende Weise:

    1. Melden Sie sich bei einem vorhandenen Azure Active Directory-Konto im Azure-Verwaltungsportal an.

    2.  Klicken Sie in Azure Active Directory auf die Option zur **Registrierung von vorhandenen Branchen-Apps** .

    3.  Wählen Sie im Abschnitt "Konfigurieren" die Option **Zugriff auf Web-APIs in anderen Anwendungen konfigurieren**aus.

    4.  Im Abschnitt **Berechtigungen für andere Anwendungen** wählen Sie aus der ersten Dropdownliste den Eintrag **Mobile Anwendungsverwaltung mit Intune** aus.

        Jetzt können Sie die Client-ID der App im App Wrapping Tool verwenden. Die Client-ID der App finden Sie im Azure Active Directory-Verwaltungsportal, wie im Abschnitt [Übersicht über die Bezeichner, die Sie abrufen müssen](#overview-of-identifiers-you-need-to-get) beschrieben.

3.  Verwenden Sie die Werte **Client-ID** (unter Verwendung der Eigenschaft **-a**) und **Redirect-URI** als Befehlszeileneigenschaften im App Wrapping Tool. Wenn Sie dieser Werte nicht haben, werden die Standardwerte verwendet. Sie müssen beide Werte angeben, sonst ist der Endbenutzer nicht in der Lage, die verarbeitete App erfolgreich zu authentifizieren.

### Anforderungen an Zertifikat, Bereitstellungsprofil und Authentifizierung

|Anforderungen|Details|
|---------------|-----------|
|Bereitstellungsprofil|**Stellen Sie sicher, dass das Bereitstellungsprofil gültig ist, bevor Sie es einfügen.** Das App Wrapping Tool überprüft bei der Verarbeitung einer iOS-App nicht, ob das Bereitstellungsprofil abgelaufen ist. Wenn ein abgelaufenes Bereitstellungsprofil angegeben wird, umfasst das App Wrapping Tool das abgelaufene Bereitstellungsprofil; Sie wissen erst dann, dass ein Problem vorliegt, wenn die Anwendung nicht mehr auf einem iOS-Gerät installiert werden kann.|
|Zertifikat|**Stellen Sie sicher, dass das Zertifikat gültig ist, bevor Sie es angeben.** Das Tool überprüft bei der Verarbeitung von iOS-Apps nicht, ob ein Zertifikat abgelaufen ist. Wenn ein Hash für ein abgelaufenes Zertifikat bereitgestellt wird, kann das Tool die App verarbeiten und signieren, jedoch die Installation auf Geräten schlägt fehl.<br /><br />**Stellen Sie sicher, dass das Zertifikat zum Signieren der verpackten Anwendung eine Übereinstimmung im Bereitstellungsprofil aufweist.** Das Tool überprüft nicht, ob das Bereitstellungsprofil eine Übereinstimmung für das zum Signieren der umschlossenen Anwendung bereitgestellte Zertifikat aufweist.|
|Authentifizierung|Ein Gerät muss eine PIN festgelegt haben, damit die Verschlüsselung funktioniert. Auf Geräten, auf denen Sie eine umschlossene Anwendung bereitgestellt haben, muss sich der Benutzer beim Berühren der Statusleiste auf dem Gerät erneut bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] authentifizieren. Die Standardrichtlinie in einer umschlossenen Anwendung lautet *Authentifizierung bei Neustart*. iOS verarbeitet externe Benachrichtigungen (z. B. einen Telefonanruf), indem die Anwendung verlassen und dann neu gestartet wird.<br /><br />Für umschlossene Apps wird der erste Benutzer, der sich bei einer umschlossenen App von selben Herausgeber anmeldet, zwischengespeichert. Nach diesem Zeitpunkt darf nur dieser Benutzer auf die App zugreifen. Zum Zurücksetzen des Benutzers muss das Gerät abgemeldet und dann neu angemeldet werden.|

### Fehlerbehebung und technische Hinweise zu ADAL

-   Wenn keine ADAL-Ressourcen gefunden werden, umfasst das Tool die dynamische ADAL-Bibliothek. Das Tool sucht nach der ADAL-Bibliothek mit dem Namen **ADALiOS.bundle** im Stammordner.

-   Das Tool sucht nicht nach ADAL-Binärdateien (sofern vorhanden) innerhalb der App. Wenn die App mit einer veralteten Version verknüpft ist, treten möglicherweise Laufzeitfehler während der Anmeldung auf, falls Authentifizierungsrichtlinien aktiviert sind.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ruft das AAD-Token zur [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM-Ressourcen-ID für die Authentifizierung ab. Es wird jedoch in keinem Aufruf verwendet, der wiederum die Gültigkeit des Tokens verifizieren würde. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] liest nur den UPN (User Principal Name, Benutzerprinzipalname) des angemeldeten Benutzers, um den Zugriff auf die App zu bestimmen. Das AAD-Token wird nicht für weitere Dienstaufrufe verwendet.

-   Authentifizierungstoken werden zwischen Apps von einem einzigen Herausgeber gemeinsam genutzt, da sie in einem freigegebenen Schlüssel gespeichert sind. Wenn Sie eine bestimmte App isolieren möchten, müssen Sie ein anderes Signaturzertifikat und ein Bereitstellungsprofil für diese App verwenden.

-   Doppelte Anmelde-Eingabeaufforderungen werden verhindert, wenn Sie die Client-ID und die Umleitungs-URI für die Clientanwendung bereitstellen. Diese Client-ID muss für den Zugriff auf die veröffentlichte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM Ressourcen-ID im AAD-Dashboard registriert werden. Falls Sie dies nicht tun, tritt ein Fehler bei der Anmeldung auf, wenn die App ausgeführt wird.

## Festlegen von App-Berechtigungen
Vor dem Umschließen Ihrer App können Sie **Berechtigungen** erteilen, um der App zusätzliche Berechtigungen und Funktionen zu gewähren, die in der Regel über das hinaus gehen, was einer App typischerweise gestattet ist.  Eine **Berechtigungsdatei** wird während der Codesignatur verwendet, um spezielle Berechtigungen innerhalb Ihrer App anzugeben (z. B. Zugriff auf einen freigegebenen Schlüsselbund). Bestimmte App-Dienste, als **Funktionen** bezeichnet, werden während der App-Entwicklung innerhalb von Xcode aktiviert. Nach ihrer Aktivierung werden die Funktionen in Ihrer Berechtigungsdatei wiedergegeben. Weitere Informationen zu Berechtigungen und Funktionen finden Sie unter [Hinzufügen von Funktionen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in der iOS-Entwicklerbibliothek. Eine vollständige Liste der unterstützten Funktionen finden Sie unter [Unterstützte Funktionen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### Unterstützte Funktionen für das App Wrapping Tool für iOS

|Funktion|Beschreibung|Empfohlene Vorgehensweise|
|--------------|---------------|------------------------|
|Gruppen hinzufügen|Verwenden Sie App-Gruppen, um mehreren Apps den Zugriff auf freigegebene Container zu gestatten, und um die zusätzliche, prozessübergreifende Kommunikation zwischen Apps zu ermöglichen.<br /><br />Um App-Gruppen zu aktivieren, öffnen Sie den Bereich **Funktionen**, und klicken Sie im Abschnitt **App-Gruppen** auf den Schalter **EIN**. Sie können App-Gruppen hinzufügen oder vorhandene auswählen.|Bei Verwendung von App-Gruppen verwenden Sie Reverse-DNS-Notation:<br /><br />*group.com.companyName.AppGroup*|
|Hintergrundmodi|Durch das Aktivieren von Hintergrundmodi kann Ihre iOS-App weiter im Hintergrund ausgeführt werden.||
|Schutz von Daten|Der Schutz von Daten erhöht die Sicherheit der von Ihrer iOS-App auf einem Datenträger gespeicherten Dateien. Der Schutz von Daten verwendet die integrierte Verschlüsselungshardware, die auf bestimmten Geräten vorhanden ist, um Dateien in einem verschlüsselten Format auf dem Datenträger zu speichern. Ihre App muss bereitgestellt sein, um den Schutz von Daten verwenden zu können.||
|In-App-Käufe|In-App-Käufe bettet einen Store direkt in Ihre App ein, indem Ihnen ermöglicht wird, eine Verbindung mit dem Store herzustellen und Zahlungen des Benutzers sicher zu verarbeiten. Mithilfe von In-App-Käufe können Sie die Zahlungen für erweiterte Funktionen abwickeln oder für zusätzliche Inhalte, die von Ihrer App verwendet werden können.||
|Schlüsselbundfreigabe|Durch die Aktivierung der Schlüsselbundfreigabe kann Ihre App Kennwörter im Schlüsselbund gemeinsam mit anderen Apps verwenden, die von Ihrem Team entwickelt wurden.|Bei Verwendung der Schlüsselbundfreigabe verwenden Sie Reverse-DNS-Notation:<br /><br />*com.companyName.KeychainGroup*|
|Persönliches VPN|Aktivieren Sie persönliches VPN, um Ihrer App das Erstellen und Kontrollieren einer benutzerdefinierten VPN-Systemkonfiguration unter Verwendung des Netzwerkerweiterungs-Frameworks zu gestatten.||
|Pushbenachrichtigungen|Der Apple-Pushbenachrichtigungsdienst (APNs) ermöglicht einer App, die nicht im Vordergrund ausgeführt wird, die Benachrichtigung des Benutzers darüber, dass sie Informationen für den Benutzer besitzt.|Damit Pushbenachrichtigungen funktionieren, müssen Sie ein App-spezifisches Bereitstellungsprofil verwenden.<br /><br />Befolgen Sie die Schritte in der [Apple-Entwicklerdokumentation](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Konfiguration drahtlosen Zubehörs|Die Aktivierung der Konfiguration drahtlosen Zubehörs fügt Ihrem Projekt das externe Zubehörframework hinzu und ermöglicht Ihrer App, die Konfiguration von WLAN-Zubehör.||

### Schritte zur Aktivierung von Berechtigungen

1.  Aktivieren Sie Funktionen in Ihrer App:

    1.  Navigieren Sie in Xcode zum Ziel Ihrer App, und klicken Sie auf den Bereich **Funktionen**.

    2.  Aktivieren Sie die entsprechenden Funktionen. Ausführlichere Informationen zu jeder einzelnen Funktion und wie Sie die richtigen Werte bestimmen, finden Sie unter [Hinzufügen von Funktionen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in der iOS-Entwicklerbibliothek.

    3.  Notieren Sie sich alle IDs, die Sie während des Prozesses erstellt haben.

    4.  Erstellen und signieren Sie Ihre App, die umschlossen werden soll.

2.  Aktivieren Sie Berechtigungen in Ihrem Bereitstellungsprofil:

    1.  Melden Sie sich beim „Apple Developer Member Center“ an.

    2.  Erstellen Sie ein Bereitstellungsprofil für Ihre App. Anleitungen hierzu finden Sie unter [Abrufen der erforderlichen Komponenten für das Intune App Wrapping Tool für iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

    3.  Aktivieren Sie in Ihrem Bereitstellungsprofil dieselben Berechtigungen, die Sie in Ihrer App haben. Sie müssen dieselben IDs angeben, die Sie während der Entwicklung Ihrer App angegeben haben.

    4.  Schließen Sie den Bereitstellungsprofil-Assistenten ab, und laden Sie Ihre Datei herunter.

3.  Stellen Sie sicher, dass Sie alle Voraussetzungen erfüllt haben, und umschließen Sie dann die App.

### Behandlung allgemeiner Fehler mit Berechtigungen
Wenn das App Wrapping Tool für iOS einen Berechtigungsfehler anzeigt, probieren Sie die folgenden Problembehandlungsschritte.

|Problem|Ursache|Lösung|
|---------|---------|--------------|
|Fehler beim Analysieren der von der Eingabeanwendung generierten Berechtigungen.|Das App Wrapping Tool kann die Berechtigungsdatei, die aus der App extrahiert wurde, nicht lesen. Die Berechtigungsdatei ist möglicherweise falsch formatiert.|Untersuchen Sie die Berechtigungsdatei für Ihre App. Befolgen Sie hierzu die weiter unten dargelegten Anweisungen. Überprüfen Sie beim Untersuchen der Berechtigungsdatei auf falsch formatierte Syntax. Die Datei sollte im XML-Format sein.|
|Berechtigungen fehlen im Bereitstellungsprofil (fehlende Berechtigungen sind aufgeführt). Packen Sie die App neu mit einem Bereitstellungsprofil, das diese Berechtigungen enthält.|Zwischen den im Bereitstellungsprofil aktivierten Berechtigungen und den in der App aktivierten Funktionen besteht ein Konflikt . Dieser Konflikt gilt auch für die IDs, die bestimmten Funktionen (d. h. App-Gruppen, Schlüsselbundzugriff usw.) zugeordnet sind.|Im Allgemeinen können Sie ein neues Bereitstellungsprofil erstellen, das dieselben Funktionen wie die App aktiviert. Wenn die IDs zwischen dem Profil und der App nicht übereinstimmen, ersetzt das App Wrapping Tool die IDs, wenn es dazu in der Lage ist. Wenn der Fehler auch nach dem Erstellen eines neuen Bereitstellungsprofils auftritt, können Sie versuchen, das Problem zu beseitigen, indem Sie Berechtigungen mithilfe des Parameters **–e** entfernen. (Informationen hierzu finden Sie unten im Abschnitt „Verwenden des Parameters ‚–e‘ zum Entfernen von Berechtigungen aus einer App“).|

### Suchen der vorhandenen Berechtigungen einer signierten App
So überprüfen Sie die vorhandenen Berechtigungen einer signierten App und eines Bereitstellungsprofils:

1.  Suchen Sie die IPA-Datei, und ändern Sie ihre Erweiterung in ZIP.

2.  Erweitern Sie die ZIP-Datei. Dies erzeugt einen Nutzlastordner, der Ihr .app-Paket enthält.

3.  Verwenden Sie das Codesignaturtool, um die Berechtigungen des .app-Pakets wie folgt zu überprüfen:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    wobei `YourApp.app` den tatsächlichen Namen Ihres APP-Pakets darstellt.

4.  Verwenden Sie das Sicherheitstool, um die Berechtigungen des in die App eingebetteten Bereitstellungsprofils zu überprüfen:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    wobei `YourApp.app` den tatsächlichen Namen Ihres APP-Pakets darstellt.

### Verwenden des Parameters „–e“ zum Entfernen von Berechtigungen aus einer App
Dieser Befehl entfernt alle aktivierten Funktionen in der App, die nicht in der Berechtigungsdatei enthalten sind. Wenn Sie Funktionen entfernen, die von der App verwendet werden, kann dies zu einer Beschädigung der App führen. Fehlende Funktionen können beispielsweise dann entfernt werden, wenn eine Drittanbieter-App standardmäßig über alle Funktionen verfügt.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Sicherheit und Datenschutz für das App Wrapping Tool
Verwenden Sie die folgenden bewährten Methoden zu Sicherheit und Datenschutz, wenn Sie das App Wrapping Tool verwenden.

-   Signaturzertifikat, Bereitstellungsprofil und Branchen-App, die Sie angeben, müssen sich auf demselben Mac-Computer befinden, den Sie verwenden, um das App Wrapping Tool auszuführen. Wenn sich die Dateien in einem UNC-Pfad befinden, stellen Sie sicher, dass auf diese vom Mac-Computer aus zugegriffen werden kann. Der Pfad muss über IPsec oder SMB-Signaturen geschützt werden.

    Die umschlossene Anwendung, die in die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Konsole importiert wurde, muss sich auf dem Computer befinden, auf dem Sie das Tool ausführen. Wenn sich die Datei in einem UNC-Pfad befindet, stellen Sie sicher, dass der Computer mit der ausgeführten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Konsole darauf zugreifen kann. Der Pfad muss über IPsec oder SMB-Signaturen geschützt werden.

-   Die Umgebung, in der das App Wrapping Tool von der Microsoft Download Center-Website heruntergeladen wird, muss über IPsec oder SMB-Signaturen geschützt sein.

-   Die App, die Sie verarbeiten, muss zum Schutz gegen Angriffe aus einer vertrauenswürdigen Quelle stammen.

-   Stellen Sie sicher, dass der Ausgabeordner, den Sie im App Wrapping Tool angeben, gesichert ist, insbesondere, wenn es sich um einen Remoteordner handelt.

-   iOS-Apps, die ein Dialogfeld zum Dateien hochladen enthalten, können Benutzern erlauben, die Einschränkungen beim Ausschneiden, Kopieren und Einfügen für die App zu umgehen. Z. B. kann ein Benutzer das Dialogfeld zum Dateien hochladen verwenden, um einen Screenshot der App-Daten hochzuladen.

-   Wenn Benutzer den Dokumentordner auf dem Gerät von einer umschlossenen App aus überwachen, sehen sie möglicherweise einen Ordner namens **.msftintuneapplauncher**. Wird dieser Ordner geändert oder gelöscht, beeinträchtigt dies die ordnungsgemäße Funktionsweise der eingeschränkten Apps.

### Weitere Informationen:
- [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Verwenden des SDKs zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


