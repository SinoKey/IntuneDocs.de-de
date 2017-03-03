---
title: Microsoft Intune App SDK-Cordova-Plug-In | Microsoft Docs
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 9ef09f43e6c878af689a500457bab578149de499


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune App SDK-Cordova-Plug-In

> [!NOTE]
> Lesen Sie am besten zuerst den Leitfaden [Erste Schritte mit dem Microsoft Intune App SDK](intune-app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.


## <a name="overview"></a>Übersicht

Das [Intune App SDK-Cordova-Plug-In](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) aktiviert [Verwaltungsfunktionen der mobile Apps in Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) für iOS und Android Apps, die mit Cordova erstellt wurden. Das Plug-In ermöglicht es Entwicklern, Funktionen der Intune-App und Datenschutzfunktionen in die Cordova-basierte App zu integrieren.

Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App zu ändern. Sobald Sie das Plug-In auf Ihrer mobilen App auf iOS oder Android erstellt haben, kann der IT-Administrator über die mobile Anwendungsverwaltung in Microsoft Intune (Mobile Application Management, MAM) Richtlinien bereitstellen, die eine Vielzahl von Datenschutzfunktionen unterstützten. Das Plug-In ist so programmiert worden, dass die meisten Schritte automatisch beim Cordova-Buildprozess ausgeführt werden. Dadurch sollte es Ihnen möglich sein, Ihre App-Verwaltung schnell zu aktivieren. Um zu beginnen, befolgen Sie die nachstehenden Anweisungen basierend auf Ihrer Zielplattform.




## <a name="whats-supported"></a>Was wird unterstützt?

### <a name="developer-machines"></a>Entwicklercomputer
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Mobile App-Plattformen
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Intune MAM-Szenarien

* Mit Intune MDM registrierte Geräte
* Mit EMM registrierte Geräte von Drittanbietern
* Nicht verwaltete (bei keiner MDM-Lösung registrierte) Geräte

Cordova-Apps, die mit dem Intune App SDK Cordova Plug-In erstellt wurden, können jetzt sowohl auf Geräten mit Intune Mobilgeräteverwaltung (mobile device management, MDM) als auch auf nicht registrierten Geräten Intune-Richtlinien zur Mobilanwendungsverwaltung (mobile application management, MAM) empfangen.



## <a name="prerequisites"></a>Voraussetzungen

### <a name="technical-prerequisites"></a>Technische Voraussetzungen

* **[Nur Android]** Es muss immer die aktuellste Microsoft Intune-Unternehmensportal-App auf dem Gerät installiert sein.


* Es wird Version 0.8.0+ des [Azure Active Directory Authentifizierungsbibliothek Plug-Ins (ADAL) für Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) benötigt.
  * **Wichtig:** Aufgrund eines Apache Cordova-Bugs führen die [hier](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) aufgelisteten Apps, die schon über die Plug-In-Abhängigkeit verfügen, das Upgrade auf die benötigte Version nicht automatisch aus.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Bevor Sie das Microsoft Intune App SDK Cordova-Plug-In benutzen, **müssen** Sie folgendes tun:

* Lesen Sie die [Intune App SDK-Cordova Plug-In Lizenzbestimmungen (in englischer Sprache)](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Drucken Sie die Lizenzbedingungen aus, und heben Sie eine Kopie für Ihre Unterlagen auf. Indem Sie das Intune App SDK Cordova-Plug-In herunterladen und verwenden, stimmen Sie diesen Lizenzbestimmungen zu.  Wenn Sie sie nicht akzeptieren, dürfen Sie die Software nicht verwenden.


## <a name="quick-start"></a>Schnellstart

1. Updaten Sie Ihre ADAL-Version:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Fügen Sie das Intune App SDK für Cordova-Plug-In hinzu:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>So erstellen Sie das Plug-In in Ihrer iOS-App

Sie müssen einige Schritte abschließen, um Ihre App für Intune MAM zu aktivieren. Der Einfachheit halber werden diese Schritte im Cordova-Buildprozess als Prebuild-Hook automatisch ausgeführt. Dadurch werden die automatisierten Schritte Ihre `*.pbxproj`- , `*-Info.plist`-, und `*.entitlements`-Dateien ändern, die einer Projektkonfiguration zugeordnet sind. Wenn das Projekt keine Berechtigungsdatei enthält, wird das Plug-In automatisch eine erstellen.

Dieses Setup unterstützt nur ein einziges Ziel. Wenn es mehrere Ziele gibt, führt es die Konfiguration auf dem Ziel aus, das als erstes gefunden wird. Wenn der Prozess fehlschlägt, überprüfen Sie, dass:

1. Das Xcode-Projekt Ihrer App `[name].xcodeproj` ist, wobei `[name]` der Wert wie definiert in `config.xml` ist.
2. Ihr Projekt verwendet die [Standardverzeichnisstruktur der Cordova-App](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>So erstellen Sie Plug-Ins in Ihrer Android-App

1. Importieren Sie dieses Plug-In mit den aktuellsten Cordova-Tools. Das Plug-In wird automatisch als ein `after_compile`-Schritt aufgerufen.

2. Das Plug-In erstellt am Ende des Buildprozesses eine MAM-fähige Version einer integrierten APK-Datei (Android API 14+). Das Buildausgabe wird eine `[Project]-intunewrapped-[Build_Configuration].apk` (z.B. `helloWorld-intunewrapped-debug.apk`) enthalten.

Das Plug-In unterstützt nur Gradle-Builds.

Aufgrund eines Cordova-Fehlers, der [hier](https://issues.apache.org/jira/browse/CB-9434) aufgeführt ist, und verursacht, dass bestimmte Cordova-Hooks in `cordova run` ignoriert werden, müssen Sie Folgendes tun, um die umschlossene App aus der Befehlszeile auszuführen:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Signieren Ihrer Android-App
Um Signaturinformationen zur umschlossenen APK-Datei hinzuzufügen, verändern Sie `build.json` so wie Sie gewöhnlich beim Hinzufügen von Signaturinformationen vorgehen würden. Beispiel:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Build nur für Android-Tests

1. Fügen Sie `android:testOnly="true"` zum Anwendungsknoten der `AndroidManifest.xml`-Datei hinzu.


2. **Cordova 6.x.x:** In `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js`, verändern Sie Zeile 60 von

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    auf
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Das Resultat davon ist, `adb install` mit dem „-t“ Flag auszuführen, da `testOnly`-Apps ohne dieses nicht installierbar sind.

### <a name="debugging-from-visual-studio"></a>Debugging aus Visual Studio
Nachdem die App zum ersten Mal gestartet wurde, sollten Sie ein Dialogfeld sehen, das Sie darüber informiert, dass die App von Intune verwaltet wird. Klicken Sie auf „Nicht mehr anzeigen“. Klicken Sie dann in VS noch einmal auf die Schaltfläche Debuggen/Ausführen, damit Haltepunkte erreicht werden.

## <a name="known-limitations"></a>Bekannte Einschränkungen
### <a name="android"></a>Android
* Die MultiDex Unterstützung ist unvollständig.
* Ziel der App muss Android 4.0 (Android API 14) oder höher sein.

### <a name="ios"></a>iOS
* Wenn Sie die Liste der UTIs unter dem Knoten **CFBundleDocumentTypes** der **Info.plist**-Datei verändern, müssen Sie die Intune-UTIs im Bereich „Importierte-UTIs“ derselben PLIST-Datei löschen (Knoten **UTImportedTypeDeclarations**), bevor Sie mit der erneuten Erstellung fortfahren. Alle Intune-UTIs beginnen mit dem Präfix `com.microsoft.intune.mam`.

* Wenn Sie das Intune-Plug-In aus Ihrem Cordova-Projekt entfernen möchten, müssen Sie auch die iOS-Plattform entfernen und sie erneut hinzufügen, um einige der Intune-Konfigurationen in den XCODEPROJ- und PLIST-Dateien rückgängig zu machen.



<!--HONumber=Dec16_HO2-->


