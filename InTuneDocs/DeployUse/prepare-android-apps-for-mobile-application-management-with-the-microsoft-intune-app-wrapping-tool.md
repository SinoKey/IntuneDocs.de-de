---
title: "Umschließen von Android-Apps mit dem App Wrapping Tool | Microsoft Intune"
description: "In diesem Thema lernen Sie, Ihre Android-Apps zu umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 061bde9155c30bf8d7063d40478bbdf35fc7b53a


---

# Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Intune App Wrapping Tool
Verwenden Sie das **Microsoft Intune App Wrapping Tool für Android** zur Steuerung des Verhaltens interner Android-Apps, um die Funktionen von Apps zu konfigurieren, ohne den Code der eigentlichen App zu ändern.

Das Tool ist eine Windows-Befehlszeilenanwendung, die in PowerShell ausgeführt wird und einen Wrapper um die App erstellt. Sobald die App verarbeitet wurde, können Sie die App-Funktionalität mit von Ihnen konfigurierten [Verwaltungsrichtlinien für mobile Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ändern.

Wenn die Azure Active Directory Authentication Library (ADAL) von Ihrer App verwendet wird, führen Sie die Schritte unter [Umschließen von Apps, die ADAL (Azure Active Directory Library) verwenden](#how-to-wrap-apps-that-use-the-azure-active-directory-library) aus, bevor Sie Ihre App umschließen. Wenn Sie nicht wissen, ob Ihre Anwendung diese Bibliothek verwendet, wenden Sie sich an den Entwickler der Anwendung.

Lesen Sie vor dem Ausführen des Tools die [Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools](#security-considerations-for-running-the-app-wrapping-tool). Informationen zum Herunterladen des Tools finden Sie unter [Microsoft Intune App Wrapping Tool für Android](https://www.microsoft.com/download/details.aspx?id=47267).

## Schritt 1: Erfüllen der Voraussetzungen für die Verwendung des App Wrapping Tools

-   Sie müssen das App Wrapping Tool auf einem Windows-Computer unter Windows 7 oder höher ausführen.

-   Die Eingabe-App muss ein gültiges Android-Anwendungspaket mit der Dateierweiterung **.apk** sein und folgende Kriterien aufweisen:

    -   Kann nicht verschlüsselt werden

    -   Darf nicht bereits vom App Wrapping Tool umschlossen sein

    -   Muss für Android 4.0 oder höher geschrieben sein

-   Die App muss von Ihrem oder für Ihr Unternehmen entwickelt werden. Mit diesem Tool können Sie keine von Google Play Store heruntergeladenen Apps bearbeiten.

-   Um das App Wrapping Tool auszuführen, müssen Sie die neueste Version der [Java Runtime Environment](http://java.com/download/) installieren und sicherstellen, dass die Java-Pfadvariable in den Windows-Umgebungsvariablen auf **C:\ProgramData\Oracle\Java\javapath** festgelegt wurde. Weitere Informationen finden Sie in der [Java-Dokumentation](http://java.com/download/help/).

    > [!NOTE]
    > In einigen Fällen kann die 32-Bit-Version von Java zu Speicherproblemen führen. Es wird empfohlen, stattdessen die 64-Bit-Version zu installieren.

## Schritt 2: Installieren des App Wrapping Tools

1.  Laden Sie die Installationsdatei für das App Wrapping Tool aus dem Microsoft Download Center herunter, und öffnen Sie sie auf einem Windows-Computer.

2.  Akzeptieren Sie den Lizenzvertrag, und schließen Sie die Installation ab.

Merken Sie sich den Ordner, in dem Sie das Tool installieren. Der Standardspeicherort ist: **C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Schritt 3: Ausführen des App Wrapping Tools

1.  Öffnen Sie auf dem Windows-Computer, auf dem Sie das App Wrapping Tool installiert haben, ein PowerShell-Fenster im Administratormodus.

2.  Importieren Sie aus dem Ordner, in dem Sie das Tool installiert haben, das PowerShell-Modul des App Wrapping Tools:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Führen Sie das Tool mithilfe des Befehls **invoke-AppWrappingTool** zusammen mit den folgenden Parametern aus. Parameter, die als "optional" markiert sind, sind für Apps bestimmt, die Azure Active Directory Library (ADAL) verwenden. Weitere Informationen finden Sie unter [Umschließen von Apps, die ADAL (Azure Active Directory Library) verwenden](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Parameter|Weitere Informationen|Beispiele|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Pfad der Android-Quelle-App (.apk).| |
|**-OutputPath**&lt;String&gt;|Pfad zur Android-"Ausgabe"-App. Ist dies der gleiche Verzeichnispfad wie InputPath, schlägt das Verpacken fehl.| |
|**-KeyStorePath**&lt;String&gt;|Pfad zur KeyStore-Datei, die das Öffentlich/Privat-Schlüsselpaar für die Signierung enthält.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des KeyStore. Android erfordert, dass alle Anwendungspakete (APK) signiert sind. Verwenden Sie das Java-Keytool, um das KeyStorePassword wie im Beispiel dargestellt zu generieren. Weitere Informationen zum KeyStore finden Sie [hier](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Der Name des Schlüssels, der zum Signieren verwendet werden soll.| |
|**-KeyPassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des privaten Schlüssels, der zum Signieren verwendet wird.| |
|**-SigAlg**&lt;SecureString&gt;|Der Name des Signaturalgorithmus, der zum Signieren verwendet werden soll. Der Algorithmus muss mit dem privaten Schlüssel kompatibel sein.|Beispiele: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|Azure Active Directory-Client-ID der Eingabe-App (optional).| |
|**-AuthorityURI**&lt;Uri&gt;|Azure Active Directory-Registrierungsstellen-URI der Eingabe-App (optional).| |
|**-SkipBroker**&lt;Boolean&gt;|Gibt an, ob die Eingabeanwendung geräteweites vermitteltes einmaliges Anmelden (Single Sign-On, SSO) unterstützt (optional). |**True**: Die Eingabeanwendung unterstützt kein geräteweites vermitteltes SSO. Verwenden Sie den Parameter "NonBrokerRedirectURI". **False**: Die Eingabeanwendung unterstützt geräteweites vermitteltes SSO.|
|**-NonBrokerRedirectURI**&lt;URI&gt;|Der Azure Active Directory-Umleitungs-URI, der verwendet werden soll, wenn SkipBroker "true" ist (optional).|  |


**&lt;CommonParameters&gt;**
    (optional – unterstützt allgemeine PowerShell-Parameter wie „verbose“, „debug“ usw.)

- Eine Liste der allgemeinen Parameter finden Sie im [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Um die Hilfe für das Tool anzuzeigen, geben Sie folgenden Befehl ein:

    ```
    Help Invoke-AppWrappingTool
    ```
- Weitere Informationen zur Integration von Azure Active Directory (AAD) finden Sie unter [Umschließen von Apps, die ADAL (Azure Active Directory Library) verwenden](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Beispiel:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

Anschließend werden Sie zur Eingabe des **KeyStorePassword** und **KeyPassword**aufgefordert.

Die umschlossene App wird generiert und zusammen mit einer Protokolldatei in dem von Ihnen angegebenen Ausgabepfad gespeichert.

## Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools
So verhindern Sie ein mögliches Spoofing, das Offenlegen von Informationen und Angriffe durch Rechteerweiterungen:

-   Stellen Sie sicher, dass sich die Branchenanwendung für die Eingabe, die Ausgabeanwendung und Java KeyStore auf demselben Computer befinden, auf dem auch das App Wrapping Tool ausgeführt wird.

-   Importieren Sie die Ausgabeanwendung in die Intune-Konsole auf demselben Computer, auf dem das Tool ausgeführt wird. Unter [Keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) finden Sie weitere Informationen zum Java-Keytool.

-   Wenn sich die Ausgabenanwendung und das Tool in einem Universal Naming Convention (UNC)-Pfad befinden und Sie das Tool und die Eingabedateien nicht auf demselben Computer ausführen, schützen Sie die Umgebung, indem Sie [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) oder [SMB-Signaturen (Server Message Block)](https://support.microsoft.com/en-us/kb/887429)konfigurieren.

-   Stellen Sie sicher, dass die Anwendung von einer vertrauenswürdigen Quelle stammt. Dies gilt insbesondere, wenn Sie Azure Active Directory (AAD) verwenden, da die Anwendung dann möglicherweise während der Laufzeit auf das AAD-Token zugreifen kann.

-   Sichern Sie das Ausgabeverzeichnis, das die umschlossene Anwendung enthält. Erwägen Sie für die Ausgabe ein Verzeichnis auf Benutzerebene zu verwenden.

## Umschließen von Apps, die ADAL (Azure Active Directory Library) verwenden
Wenn Azure Active Directory Authentication Library (ADAL) von Ihrer App verwendet wird, führen Sie diese Schritte aus, bevor Sie Ihre App wrappen.

### Schritt 1: Sicherstellen, dass die Anforderungen für ADAL erfüllt sind
Für Apps, die ADAL verwenden, muss Folgendes zutreffen:

-   In der App muss mindestens ADAL 1.0.2 integriert sein.

-   Der Entwickler muss seiner App Zugriff auf die Intune MAM-Ressource (mobile Anwendungsverwaltung) gewähren, wie unter [Schritt 3: Konfigurieren des Zugriffs auf die mobile Anwendungsverwaltung in AAD](#step-3-configure-access-to-mobile-app-management-in-aad) beschrieben.

### Schritt 2: Überprüfen der Bezeichner, die Sie beim Registrieren der App abrufen müssen
Im nächsten Schritt verwenden Sie das Azure-Verwaltungsportal zum Registrieren Ihrer Apps (die ADAL mit Azure Active Directory (AAD) verwenden), um die in der folgenden Tabelle aufgeführten eindeutigen Bezeichner zu erhalten. Anschließend übergeben Sie die Bezeichner beim Integrieren von ADAL in die App dem Entwickler.

|ID|Weitere Informationen|Standardwert|
|--------------|--------------------|-----------------|
|**Client-ID**|Ein eindeutiger GUID-Bezeichner, der für die App nach der Registrierung mit AAD generiert wird.<br /><br />Wenn Sie die Client-ID der App kennen, geben Sie diesen Wert an. Andernfalls verwenden Sie den Standardwert.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Authority URI**|Der Registrierungsstellen-URI-Wert (Uniform Resource Identifier) für AAD-Objekte (z. B. Benutzer und Gruppen).<br /><br />Der Parameter "AuthorityURI" ist für das App Wrapping Tool optional. Der Standard-URI wird verwendet, wenn Sie den Parameter nicht verwenden.||
|**SkipBroker**|Wert, der angibt, ob das Unternehmensportal als Broker verwendet wird.<br /><br />**True**: Das Unternehmensportal wird nicht für die ADAL-Authentifizierung verwendet.<br /><br />**False**: Das Unternehmensportal wird für die ADAL-Authentifizierung verwendet. Das Unternehmensportal verwendet zu SSO-Zwecken den angemeldeten Benutzer.||
|**Non-Broker Redirect URI**|Anmelde-URI, der verwendet wird, wenn ADAL die Broker-App (Intune-Unternehmensportal) nicht verwendet.|urn:ietf:wg:oauth:2.0:oob|
|**Resource ID**|Zeiger auf die AAD-Ressourcen der App.||

### Schritt 3: Konfigurieren des Zugriffs auf die mobile Anwendungsverwaltung in AAD
Bevor Sie die AAD-Registrierungswerte einer App im App Wrapping Tool verwenden können, muss der App-Entwickler der App den Zugriff auf die Intune MAM-Ressource (mobile Anwendungsverwaltung) mithilfe der folgenden Schritte gewähren:

1.  Melden Sie sich bei einem vorhandenen AAD-Konto im Azure-Verwaltungsportal an.

2.  Wählen Sie die **Registrierung von vorhandenen Branchenanwendungen**.

3.  Wählen Sie im Abschnitt **Konfigurieren** die Option **Zugriff auf Web-APIs in anderen Anwendungen konfigurieren**aus.

4.  Im Abschnitt **Berechtigungen für andere Anwendungen** wählen Sie aus der ersten Dropdownliste den Eintrag **Mobile Anwendungsverwaltung mit Intune** aus.

Jetzt können Sie die Client-ID der App im App Wrapping Tool verwenden. Die Client-ID finden Sie im Azure Active Directory-Verwaltungsportal, wie in der Tabelle unter [Schritt 2: Überprüfen der Bezeichner, die Sie beim Registrieren der App abrufen müssen](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app) beschrieben.

### Schritt 4: Verwenden der AAD-Bezeichnerwerte im App Wrapping Tool
Geben Sie die Werte im App Wrapping Tool unter Verwendung der Bezeichnerwerte aus dem Registrierungsprozess als Befehlszeileneigenschaften ein. Sie müssen alle Werte in der Tabelle angeben, damit Endbenutzer die App erfolgreich authentifizieren können. Wenn Sie einen Wert nicht angeben, wird der entsprechende Standardwert verwendet.

|ID|Parameter|
|--------------|-------------|
|Client-ID|ClientID|
|Authority URI|Authority-URI|
|SkipBroker|SkipBroker|
|Non-Broker Redirect URI|NonBrokerRedirectURI|
|Resource ID|ResourceID|
Beachten Sie beim Wrappen Ihrer App folgende Punkte:

-   Um zu überprüfen, ob die Authentifizierung erfolgreich war, ruft [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] das der MAM-Ressourcen-ID zugeordnete AAD-Token ab. Das Token wird jedoch in keinem Aufruf verwendet, wodurch die Gültigkeit des Tokens verifiziert würde. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] liest nur den Benutzerprinzipalnamen (UPN) des angemeldeten Benutzers, um den Zugriff auf die App zu bestimmen. Das AAD-Token wird nicht für weitere Dienstaufrufe verwendet.

-   Doppelte Anmeldeeingabeaufforderungen werden verhindert, wenn Sie die Client-ID und den Registrierungsstellen-URI der Clientanwendung bereitstellen. Die Client-ID muss für den Zugriff auf die veröffentlichte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM-Ressourcen-ID im AAD-Dashboard registriert werden. Wurde die Client-ID nicht registriert, erhalten Benutzer bei der Anmeldung einen Fehler, wenn die App ausgeführt wird.


### Weitere Informationen:
- [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Verwenden des SDKs zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO5-->


