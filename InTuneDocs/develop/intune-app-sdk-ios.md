---
title: "Entwicklerhandbuch zum Microsoft Intune App SDK für iOS | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: 820ec2da0554f0af383895482241be7d1c0cf305


---

# Microsoft Intune App SDK für iOS –Entwicklerhandbuch

> [!NOTE]
> Lesen Sie am besten zuerst den Leitfaden [Erste Schritte mit dem Microsoft Intune App SDK](intune-app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.* 

Das Microsoft Intune App SDK für iOS ermöglicht die Integration von Intune Mobile App Management (MAM) in Ihre iOS-App. Eine MAM-aktivierte Anwendung ist eine Anwendung, in die das Intune App SDK integriert ist. Damit können IT-Administratoren Richtlinien in Ihrer mobilen App bereitstellen, wenn die App aktiv verwaltet wird.

# Inhalt des SDK

Das Intune App SDK für iOS enthält eine statische Bibliothek, Ressourcendateien, API-Header, eine Liste mit Debug-Einstellungen (PLIST) sowie ein Konfigurationstool. Mobile Apps können einfach nur die Ressourcendateien enthalten und statisch mit den Bibliotheken verknüpft sein, um die meisten Richtlinien durchzusetzen. Erweiterte Intune-MAM-Funktionen werden mithilfe von APIs erzwungen.
Dieses Handbuch befasst sich mit der Nutzung der folgenden Komponenten bei der Integration von des Intune App SDK für iOS:

* **`libIntuneMAM.a`**: Die Intune App-SDK-Bibliothek. Verknüpfen Sie diese Bibliothek mit Ihrem Projekt, um Ihre mobile App für MAM zu aktivieren. Anweisungen finden Sie im Abschnitt "Erstellen Ihrer App mit dem Intune App SDK" in diesem Artikel.

* **`IntuneMAMResources.Bundle`**: Ein Ressourcenpaket, das die Ressourcen für das SDK enthält. 

* **Headers**: Stellt die Intune App SDK-APIs bereit. Wenn Sie eine API verwenden, müssen Sie die Headerdatei einschließen, die die API enthält. 

# Funktionsweise des Intune App SDK

Ziel des Intune App SDK für iOS ist es, iOS-Anwendungen mit minimalen Codeänderungen mit Verwaltungsfunktionen zu versehen. Mit weniger Codeänderungen wird die Markteinführungszeit verkürzt, während gleichzeitig die Konsistenz und Stabilität der mobilen Anwendung erhöht wird. 

Die Anwendung muss mit der statischen Bibliothek verknüpft werden und das Ressourcenpaket enthalten. Die Datei "MAMDebugSettings.plist" ist optional und kann in das Paket eingeschlossen werden, um MAM-Richtlinien zu simulieren, die für die Anwendung aktiviert werden, ohne dass die Anwendung über Microsoft Intune bereitgestellt werden muss. Daneben können in Debugversionen die Richtlinien in der Datei " MAMDebugSettings.plist" angewendet werden, indem die Datei " MAMDebugSettings.plist" mithilfe der iTunes-Dateifreigabe in das Verzeichnis "Dokumente" der Anwendung übertragen wird.

# Erstellen einer App mit dem Intune App SDK 

Führen Sie die nachstehenden Schritte aus, um das Intune App SDK zu aktivieren:

1. Verknüpfen Sie die Bibliothek `libIntuneMAM.a` mit den folgenden Schritten:

    Ziehen Sie die Bibliothek " libIntuneMAM.a" auf die Liste "Verknüpfte Frameworks und Bibliotheken" des Projektziels, und legen Sie sie dort ab.  

    ![Intune App SDK iOS – verknüpfte Frameworks und Bibliotheken](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **Hinweis**: Bei der Veröffentlichung im App Store verwenden Sie bitte die Version von "libIntuneMAM.a", die für die Veröffentlichung erstellt wurde, und nicht die Debugversion. Die Veröffentlichungsversion befindet sich im Ordner "Release". Die Debugversion enthält ausführliche Ausgaben, die sich gut für das Debuggen von Problemen mit dem Intune App SDK eignen.

2. Fügen Sie (sofern noch nicht vorhanden) die folgenden iOS-Frameworks zum Projekt hinzu:
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Hinweis**: Wenn die Anwendung für iOS7 erstellt werden soll, legen Sie das Attribut "Status" von `LocalAuthentication.Framework` auf "Optional" fest. 

    Wenn "Status" nicht festgelegt wurde, kann die Anwendung unter iOS7 nicht gestartet werden.

    **Hinweis**: In Xcode 7 wurden die `.dylib` -Erweiterungen in `.tbd`.

3. Fügen Sie das Ressourcenpaket `IntuneMAMResources.bundle` zum Projekt hinzu, indem Sie es unter "Copy Bundle Resources" in "Build Phases" ziehen. 

    ![Intune App SDK iOS – Paketressourcen kopieren](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Fügen Sie `-force_load {PATH_TO_LIB}/libIntuneMAM.a` einem der folgenden Pfade hinzu, wobei Sie `{PATH_TO_LIB}` durch den Speicherort des Intune App SDK ersetzen:
    * der Buildkonfigurationseinstellung OTHER_LDFLAGS des Projekts 
    * "Other Linker Flags" der Benutzeroberfläche<br>

    **Hinweis**: Um den `PATH_TO_LIB`zu suchen, wählen Sie die Datei `libIntuneMAM.a` aus, und wählen Sie dann "Get Info" im Menü "File" aus. Kopieren Sie die Informationen unter "Where" (den Pfad) aus dem Abschnitt "General" in das Fenster "Info".

5. Wenn in Ihrer mobilen App ein Haupt-NIB oder eine Haupt-Storyboard in der Datei `info.plist`definiert ist, entfernen Sie die Felder für Haupt-Storyboard oder Haupt-NIB. Fügen Sie die zuvor entfernten Werte für die Storyboard oder die NIB in einem neuen Wörterbuch mit Namen `IntuneMAMSettings` mit den folgenden Schlüsselnamen (sofern zutreffend) hinzu:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    Wenn in Ihrer mobilen App keine Haupt-NIB oder Storyboard in der `info.plist`definiert sind, sind diese Einstellungen **nicht erforderlich**. 

    **Hinweis**: Sie können die Datei `info.plist` im Raw-Format anzeigen (um die Schlüsselnamen zu sehen), indem Sie mit der rechten Maustaste an eine beliebige Stelle im Dokument klicken und den Anzeigetyp auf "Show Raw Keys/Values" ändern.

6. Aktivieren Sie die Freigabe der Schlüsselsammlung (sofern noch nicht geschehen), indem Sie in jedem Projektziel auf "Capabilities" klicken und den Schalter "Keychain Sharing" auf "Ein" festlegen. Die Freigabe der Schlüsselsammlung ist für den nächsten Schritt erforderlich.

    **Hinweis**: Ihr Bereitstellungsprofil muss neue Werte für die Freigabe der Schlüsselsammlung unterstützen. Die Schlüsselsammlungs-Zugriffsgruppen sollten ein Platzhalterzeichen unterstützen. Sie können dies überprüfen, indem Sie die Datei `.mobileprovision` in einem Text-Editor öffnen, nach "keychain-access-groups" suchen und sich vergewissern, dass ein Platzhalter vorhanden ist. Beispiel: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. Nachdem Sie die Freigabe der Schlüsselsammlung aktiviert haben, folgen Sie den nachstehenden Schritten, um eine separate Zugriffsgruppe zu erstellen, in der die Intune App SDK-Daten gespeichert werden. Sie können eine Zugriffsgruppe für die Schlüsselsammlung über die Benutzeroberfläche oder mithilfe der Berechtigungsdatei erstellen:

    Verwenden der Benutzeroberfläche zum erstellen einer Zugriffsgruppe für die Schlüsselsammlung: 
    
    * Wenn in Ihrer mobilen App keine Zugriffsgruppen für die Schlüsselsammlung definiert sind, fügen Sie die Paket-ID der App als erste Gruppe hinzu.
    * Fügen Sie die gemeinsam genutzte Schlüsselsammlungsgruppe "com.microsoft.intune.mam" hinzu. Diese Zugriffsgruppe wird vom Intune App SDK zum Speichern von Daten verwendet.  
    * Fügen Sie das Ressourcenpaket `com.microsoft.adalcache` den vorhandenen Zugriffsgruppen hinzu. 
 
    ![Intune App SDK für iOS – Schlüsselsammlung gemeinsam nutzen](../media/intune-app-sdk-ios-keychain-sharing.png)

    Wenn Sie die Berechtigungsdatei und nicht die reguläre Benutzeroberfläche verwenden, um die Zugriffsgruppe für die Schlüsselsammlung zu erstellen, müssen Sie der Zugriffsgruppe für die Schlüsselsammlung in der Berechtigungsdatei `$(AppIdentifierPrefix)` voranstellen. Beispiele: `$(AppIdentifierPrefix)com.microsoft.intune.mam` und `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Hinweis**: Eine Berechtigungsdatei ist eine XML-Datei, die für Ihre mobile Anwendung eindeutig ist und verwendet wird, um in der iOS-App spezielle Berechtigungen und Funktionen anzugeben.

8. Bei mobilen Apps, die für iOS 9+ entwickelt werden, müssen Sie jedes Protokoll, das Ihre mobile App durchläuft, zu `UIApplication canOpenURL` im Array `LSApplicationQueriesSchemes` der Datei `info.plist` Ihrer mobilen App hinzufügen. Darüber hinaus muss für jedes aufgeführte Protokoll ein neues Protokoll hinzugefügt werden, dem `-intunemam`. Sie müssen auch `http-intunemam`, `https-intunemam`und `ms-outlook-intunemam` in das Array einschließen. 

9. Wenn in der Datei `info.plist file`der App URL-Schemas definiert sind, fügen Sie ein weiteres Schema mit dem Suffix `-intunemam` für jedes URL-Schema hinzu.

10. Wenn in den Berechtigungen der App-Gruppen definiert sind, fügen Sie diese Gruppen dem Wörterbuch `IntuneMAMSettings` unter dem Schlüssel `AppGroupIdentitifiers` als Zeichenfolgenarray hinzu.

11. Verknüpfen Sie Ihre mobile Anwendung mit der ADAL-Bibliothek. Die ADAL-Bibliothek für Objective C ist [auf Github verfügbar](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Hinweis**: Das Intune App SDK wurde mit dem ADAL Broker Branch Code vom 19.06.2015 getestet. Stellen Sie sicher, dass die Verknüpfung mit der neuesten/funktionierenden Version der ADAL-Bibliothek erfolgt.

12. Schließen Sie das Ressourcenpaket `ADALiOSBundle.bundle resource` in das Projekt ein, indem Sie es unter "Copy Bundle Resources" in "Build Phases" ziehen.

13. Verwenden Sie die Linkeroption `-force_load PATH_TO_ADAL_LIBRARY` bei der Verknüpfung mit der Bibliothek.

    Fügen Sie `-force_load {PATH_TO_LIB}/libADALiOS.a` zur Buildkonfigurationseinstellung OTHER_LDFLAGS des Projekts oder zu "Other Linker Flags" auf der Benutzeroberfläche hinzu. „PATH_TO_LIB“ sollte durch den Speicherort der ADAL-Binärdateien ersetzt werden. 

Wenn Ihre mobile Anwendung ADAL für die eigene Authentifizierung verwendet, lesen Sie bitte den Abschnitt "Konfigurieren der Einstellungen für die Authentifizierungsbibliothek des Azure-Verzeichnisses" in diesem Handbuch.

## Telemetrie 

Das Intune App SDK für iOS protokolliert standardmäßig Telemetriedaten zu Verwendungsereignissen, die an Microsoft Intune gesendet werden.

Für die folgenden Verwendungsereignisse werden Daten protokolliert: 

1. App-Start, um Microsoft Intune zu helfen, die Verwendung von für MAM aktivierten Apps nach Verwaltungstyp zu erkennen

2. Aufruf der enrollApplication-API, um Microsoft Intune zu helfen, die Erfolgsrate und verschiedene andere Leistungsmetriken des enrollApplication-Aufrufs von der Clientseite zu erkennen

**Hinweis**:Wenn von Ihrer mobilen Anwendung keine Intune App SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, **müssen Sie die Intune App SDK-Telemetrieerfassung deaktivieren** , indem Sie unter `MAMTelemetryDisabled` die Eigenschaft `IntuneMAMSettings`.

## Konfigurieren der Einstellungen für die Authentifizierungsbibliothek des Azure-Verzeichnisses (ADAL) (optional)

Das Intune App SDK verwendet ADAL (Azure Directory Authentication Library) für die Authentifizierung und bedingte Startszenarien. Normalerweise setzt ADAL voraus, dass Apps sich registrieren und eine eindeutige ID, die als `ClientID`bezeichnet wird, sowie weitere Bezeichner abrufen, um die Sicherheit der Token zu gewährleisten, die an die Anwendung übermittelt werden. Das Intune App SDK verwendet standardmäßige Registrierungswerte bei der Kontaktaufnahme zu Azure Active Directory.  Wenn die App selbst ADAL als Authentifizierungsszenario verwendet, muss sie ihre vorhandenen Registrierungswerte verwenden und die Standardwerte des Intune App SDK überschreiben, um sicherzustellen, dass die Endbenutzer nicht zwei Mal zur Authentifizierung aufgefordert werden (einmal vom Intune App SDK und ein weiteres Mal von der App). 

Die nachstehenden Schritte sind erforderlich, wenn die App selbst ADAL für die Authentifizierung verwendet. Wenn Ihre mobile App ADAL nicht verwendet, ist keine weitere Aktion erforderlich. 

1. Geben Sie in der Datei `Info.plist`des Projekts unter dem `IntuneMAMSettings` -Wörterbuch mit dem Schlüsselnamen `ADALClientId`die `ClientID` an, die für ADAL-Aufrufe verwendet werden soll. 

2. Geben Sie in der Datei `Info.plist`des Projekts unter dem `IntuneMAMSettings` -Wörterbuch mit dem Schlüsselnamen `ADALRedirectUri`die Umleitungs-URI an, die für ADAL-Aufrufe verwendet werden soll. Je nach dem Format der Umleitungs-URI Ihrer App müssen Sie auch das `ADALRedirectScheme` angeben.

## Erstellen von Erweiterungen (optional) 

Folgen Sie beim Erstellen von Erweiterungen denselben Anweisungen wie beim Erstellen Ihrer mobilen App, wie im Abschnitt "Erstellen einer App mit dem Intune App SDK" in diesem Handbuch erläutert. Aktualisieren Sie darüber hinaus die Datei "info.plist" jeder Erweiterung, um einen Schlüssel "ContainingAppBundleId" unter dem Wörterbuch"IntuneMAMSettings" mit dem Wert der Paket-ID der Anwendung hinzuzufügen.

## Erstellen Ihrer Frameworks (optional)

Dank den letzten Änderungen am Intune App SDK müssen Sie Ihre mobile App nicht mit speziellen Linker-Flags kompilieren, wenn Ihre mobile App eingebettete Anwendungsframeworks enthält. 

## Abbilddateien beim Start (optional)

Wenn eine für MAM aktivierte App aktiv von Microsoft Intune verwaltet wird, zeigt das Intune App SDK beim App-Start einen Startbildschirm an, um den Benutzer darauf hinzuweisen, dass die App verwaltet wird. Sie können optional Abbilddateien hinzufügen, damit auf der Startseite "Vom Unternehmen verwaltet" angezeigt wird. Verwenden Sie für Abbilddateien folgende Richtlinien:

* Fügen Sie die Dateinamen unter dem Wörterbuch `IntuneMAMSettings` in der Datei "info.plist" der App mit den Schlüsselnamen `SplashIconFile` und `SplashIconFile~ipad`. 

* Größe der Abbilddatei und Anforderungen:

    * 180 x 180 für iPhone 6s Plus und iPhone 6 Plus, 120 x 120 für andere iPhone-Modelle und 152 x 152 für iPad. 
    
    * Entfernen Sie die Erweiterung `.png` aus den Dateinamen. 
    
    * Verwenden Sie die Linkeroption `@2x` für Versionen mit zweifacher Skalierung und das Suffix `@3x` für Versionen mit dreifacher Skalierung der Abbilddateien. Wenn die Abbilddateien nicht die korrekte Größe aufweisen, werden sie entsprechend skaliert. Wenn die Werte von "SplashIconFile" nicht angegeben werden, wählt das Intune App SDK eines der Symbole der App aus (60 x 60 für alle iPhones, 76 x 76 für iPad).

**Hinweis**: Dieser Bildschirm wird beim Start angezeigt, kann vom Benutzer jedoch dauerhaft abgeschaltet werden.

# Konfigurieren der Intune App SDK-Einstellungen

Zum Konfigurieren des Intune App SDK wird das Wörterbuch `IntuneMAMSettings` verwendet, das sich in der Datei `info.plist` der Anwendung befindet. Es folgt eine Liste aller unterstützten Einstellungen: 

Einige dieser Einstellungen wurden ggf. schon in vorherigen Abschnitten erörtert, und einige gelten nicht für alle Anwendungen. 

Einstellung  | Typ  | Definition | Erforderlich?
--|--|--|--
ADALClientId  | Zeichenfolge  | Die AAD-Client-ID der Anwendung. | Erforderlich, wenn die Anwendung ADAL verwendet.
ADALRedirectUri  | Zeichenfolge  | Die AAD-Umleitungs-URI der Anwendung. | Erforderlich, wenn die Anwendung ADAL verwendet. 
AppGroupIdentifier | Ein Zeichenfolgenarray.  | Ein Array mit App-Gruppen aus dem Berechtigungsabschnitt "com.apple.security.application-groups" der App. | Erforderlich, wenn die App Anwendungsgruppen verwendet.
ContainingAppBundleId  | Zeichenfolge | Gibt die Paket-ID der Anwendung an, die die Erweiterung enthält. | Erforderlich für iOS-Erweiterungen.
MainNibFile<br>MainNibFile~ipad  | Zeichenfolge  | Diese Einstellung sollte den Namen der Haupt-NIB-Datei der Anwendung enthalten.  | Erforderlich, wenn in der Datei "info.plist" der Anwendung "MainNibFile" definiert ist.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Zeichenfolge  | Diese Einstellung sollte den Namen der Haupt-Storyboard-Datei der Anwendung enthalten. | Erforderlich, wenn in der Datei "info.plist" der Anwendung "UIMainStoryboardFile" definiert ist.
SplashIconFile <br>SplashIconFile~ipad  | Zeichenfolge  | Gibt die Intune Splash Icon-Datei an. Weitere Informationen hierzu finden Sie im Abschnitt "Abbilddateien beim Start". | (Optional)
SplashDuration | Zahl | Mindestdauer in Sekunden, für die der Intune Splash-Bildschirm beim Anwendungsstart angezeigt wird. Standardwert ist 1,5. | (Optional)
ADALLogOverrideDisabled | Boolesch  | Gibt an, ob das SDK alle ADAL-Protokolle (einschließlich ADAL-Aufrufe von der App, sofern zutreffend) in die eigene Protokolldatei einschließt. Standardwert ist "NO". Legen Sie den Wert auf "YES" fest, wenn die App einen eigenen ADAL-Protokollrückruf festlegen möchte. | Optional.

# Header des Intune App SDK 

Die folgenden Header schließen die API-Funktionsaufrufe ein, die erforderlich sind, um die Funktionalität des Intune App SDK zu aktivieren. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Debuggen des Intune App SDK in Xcode

Bevor Sie Ihre für MAM aktivierte Anwendung mit Microsoft Intune testen, können Sie `Settings.bundle` verwenden, während Sie sich in Xcode befinden. Dies ermöglicht die Festlegung von Testrichtlinien, ohne dass eine Verbindung zu Intune erforderlich wird. Zum Aktivieren:

* Fügen Sie `Settings.bundle` hinzu, indem Sie mit der rechten Maustaste auf den Ordner auf oberster Ebene in Ihrem Projekt klicken. Wählen Sie "Add" > "New File" im Menü aus. Wählen Sie die Vorlage "Settings Bundle" unter "Resources" aus, um sie hinzuzufügen.

* Nur bei Debug-Builds: Kopieren Sie `MAMDebugSettings.plist` in `Settings.bundle`.

* Fügen Sie in `Root.plist` (in "Settings.bundle") die Einstellung "Type" Child Pane, "FileName" `MAMDebugSettings`.

* Schalten Sie unter "Settings -> Name-Ihrer-App" die Option "Enable Test Policies" um.

* Starten Sie die App (entweder innerhalb oder außerhalb von Xcode). 

* Schalten Sie unter "Settings -> Name-Ihrer-App -> Enable Test Policies" eine Richtlinie um, wie beispielsweise "PIN".

* Starten Sie die App (entweder innerhalb oder außerhalb von Xcode). Vergewissern Sie sich, dass PIN wie erwartet funktioniert.

> [!NOTE]
> Sie können nun „Settings (Einstellungen) -> Name-Ihrer-App -> Enable Test Policies (Testrichtlinien aktivieren)“ verwenden, um Einstellungen zu aktivieren und umzuschalten.

# Empfohlene und bewährte Methoden für iOS

Im Folgenden finden Sie einige empfohlene und bewährte Methoden für die Entwicklung für iOS:

Beim iOS-Dateisystem werden Groß-/Kleinschreibung berücksichtigt. Vergewissern Sie sich, dass die Groß-/Kleinschreibung bei Dateinamen wie `libIntuneMAM.a` und `IntuneMAMResources.bundle`.

Wenn Xcode Probleme beim Suchen nach `libIntuneMAM.a`hat, können Sie das Problem beheben, indem Sie den Pfad zu dieser Bibliothek den Linker-Suchpfaden hinzufügen.




<!--HONumber=Jun16_HO4-->


