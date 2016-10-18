---
title: "Umschließen von Android-Apps mit dem App Wrapping Tool | Microsoft Intune"
description: "In diesem Thema lernen Sie, Ihre Android-Apps zu umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c6622624230e3486d2498b1b023f2efcdc2970
ms.openlocfilehash: ea1a6ef60b6a9cdd64559f67276280a4f491e30e


---

# Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Intune App Wrapping Tool
Verwenden Sie das **Microsoft Intune App Wrapping Tool für Android** zur Steuerung des Verhaltens interner Android-Apps, um die Funktionen von Apps zu konfigurieren, ohne den Code der eigentlichen App zu ändern.

Das Tool ist eine Windows-Befehlszeilenanwendung, die in PowerShell ausgeführt wird und einen Wrapper um die App erstellt. Sobald die App verarbeitet wurde, können Sie die App-Funktionalität mit von Ihnen konfigurierten [Verwaltungsrichtlinien für mobile Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ändern.


Lesen Sie vor dem Ausführen des Tools die [Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools](#security-considerations-for-running-the-app-wrapping-tool). Informationen zum Herunterladen des Tools finden Sie unter [Microsoft Intune App Wrapping Tool für Android](https://www.microsoft.com/download/details.aspx?id=47267).

>[!IMPORTANT]
>Die Version des App Wrapping-Tools, die nicht in Intune registrierte Geräte unterstützt, ist als öffentliche Vorschau verfügbar. Wenn Sie an der öffentlichen Vorschau teilnehmen möchten, können Sie das Tool von [dieser GitHub-Seite](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) für Android herunterladen.

Dieses Szenario ist im Thema [Schützen von Branchenanwendungen auf Geräten, die nicht bei Intune registriert sind](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) beschrieben.


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

3.  Führen Sie das Tool mithilfe des Befehls **invoke-AppWrappingTool** zusammen mit den folgenden Parametern aus.

|Parameter|Weitere Informationen|Beispiele|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Pfad der Android-Quelle-App (.apk).| |
|**-OutputPath**&lt;String&gt;|Pfad zur Android-"Ausgabe"-App. Ist dies der gleiche Verzeichnispfad wie InputPath, schlägt das Verpacken fehl.| |
|**-KeyStorePath**&lt;String&gt;|Pfad zur KeyStore-Datei, die das Öffentlich/Privat-Schlüsselpaar für die Signierung enthält.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des KeyStore. Android erfordert, dass alle Anwendungspakete (APK) signiert sind. Verwenden Sie das Java-Keytool, um das KeyStorePassword wie im Beispiel dargestellt zu generieren. Weitere Informationen zum KeyStore finden Sie [hier](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Der Name des Schlüssels, der zum Signieren verwendet werden soll.| |
|**-KeyPassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des privaten Schlüssels, der zum Signieren verwendet wird.| |
|**-SigAlg**&lt;SecureString&gt;|Der Name des Signaturalgorithmus, der zum Signieren verwendet werden soll. Der Algorithmus muss mit dem privaten Schlüssel kompatibel sein.|Beispiele: SHA256withRSA, SHA1withRSA, MD5withRSA|


**&lt;CommonParameters&gt;**
    (optional – unterstützt allgemeine PowerShell-Parameter wie „verbose“, „debug“ usw.)

- Eine Liste der allgemeinen Parameter finden Sie im [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Um die Hilfe für das Tool anzuzeigen, geben Sie folgenden Befehl ein:

    ```
    Help Invoke-AppWrappingTool
    ```

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

-   Stellen Sie sicher, dass die Anwendung von einer vertrauenswürdigen Quelle stammt, was möglicherweise erlaubt, dass die Anwendung während der Laufzeit auf das AAD-Token zugreift.

-   Sichern Sie das Ausgabeverzeichnis, das die umschlossene Anwendung enthält. Erwägen Sie für die Ausgabe ein Verzeichnis auf Benutzerebene zu verwenden.



### Weitere Informationen:
- [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Verwenden des SDKs zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO2-->


