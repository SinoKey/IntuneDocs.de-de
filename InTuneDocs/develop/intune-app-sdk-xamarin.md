---
title: Microsoft Intune App SDK-Xamarin-Komponente | Microsoft Intune
description: 
keywords: sdk, Xamarin, intune
author: oydang
manager: karthikaraman
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4623db80d711f3543b6d688fb1bb1ef228c62c
ms.openlocfilehash: e2d43fff8772046fe7426b267e39d53b278d4e5c


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Intune App SDK-Xamarin-Komponente

## <a name="overview"></a>Übersicht
Mit der [Intune App SDK-Xamarin-Komponente](https://components.xamarin.com/view/microsoft.intune.mam) können Sie die [Intune-Verwaltungsfunktionen für mobile Apps](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in Ihren mit Xamarin erstellten mobilen iOS- und Android-Apps aktivieren. Die Komponente erlaubt Entwicklern die einfache Erstellung von App-Beschränkungen und Datenschutzfunktionen in ihrer Xamarin-basierten App.

Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App zu ändern. Sobald Sie die Komponente auf Ihrer mobilen App für iOS oder Android erstellt haben, kann der IT-Administrator über Microsoft Intune Richtlinien bereitstellen, die eine Vielzahl von Funktionen zur Datenschutzaktivierung unterstützen.

## <a name="supported-scenarios"></a>Unterstützte Szenarien

### <a name="platforms"></a>Plattformen
* Android
* iOS


### <a name="emm-scenarios"></a>EMM-Szenarios

* Intune MAM auf mit Intune MDM registrierten Geräten
* Intune MAM auf mit EMM registrierten Geräten von Drittparteien
* Intune MAM oder unregistrierte, nicht verwaltete Geräte

Xamarin-Apps, die mit Intune App SDK-Xamarin-Komponenten erstellt wurden, können jetzt sowohl auf Geräten mit Intune Mobilgeräteverwaltung (MDM) als auch auf nicht registrierten Geräten Intune-Richtlinien des mobilen Anwendungsmanagements (MAM) empfangen.

## <a name="prerequisites"></a>Voraussetzungen

* **[Nur Android]** Es muss immer die aktuellste Microsoft Intune-Unternehmensportal-App auf dem Gerät installiert sein.

## <a name="get-started"></a>Erste Schritte

1.  Laden Sie [hier](https://components.xamarin.com/submit/xpkg) die **Xamarin-component.exe** herunter, und extrahieren Sie diese.

2. Lesen Sie die [Lizenzbedingungen](https://components.xamarin.com/license/microsoft.intune.mam) für die Microsoft Intune MAM-Xamarin-Komponente.

3.  Laden Sie den Intune App SDK-Xamarin-Komponentenordner aus [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) oder [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) herunter, und extrahieren Sie diesen. Die beiden geladenen Dateien aus Schritt 1 und Schritt 2 sollten sich auf derselben Verzeichnisebene befinden.

4.  Führen Sie `Xamain.Component.exe install <.xam> file` in der Befehlszeile als Administrator aus.

5.  Klicken Sie mit der rechten Maustaste in Ihrem zuvor erstellten Xamarin-Projekt auf **Komponenten**.

6.  Wählen Sie **Komponenten bearbeiten** aus, und fügen Sie die Intune App SDK-Komponente hinzu, die Sie lokal auf Ihren Computer heruntergeladen haben.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Aktivieren von Intune MAM auf Ihrer mobilen iOS-App
1.  Um das Intune-App-SDK zu starten, müssen Sie eine beliebige API der `AppDelegate.cs`-Klasse aufrufen. Beispiel:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Nachdem die Komponente hinzugefügt und gestartet wurde, können die allgemeinen Schritte ausgeführt werden, die zum Einrichten der App-SDK in der mobilen iOS-Anwendung notwendig sind. Die kompletten Unterlagen zur Aktivierung nativer iOS-Apps finden Sie unter [Microsoft Intune App SDK für iOS – Entwicklerhandbuch](intune-app-sdk-ios).
3. **Wichtig**: Es gibt verschiedene Modifikationen, die spezifisch für Xamarin-basierte iOS-Apps sind. Wenn beispielsweise Schlüsselbundgruppen aktiviert werden, muss folgendes hinzugefügt werden, um die Xamarin-Beispiel-App, die von uns in die Komponente integriert wurde, zu integrieren. Nachstehend finden Sie das Beispiel einer Gruppe, die Sie in Ihren Schlüsselbund-Zugriffsgruppen benötigen:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Sie haben die notwendigen Schritte ausgeführt um die Komponente in Ihrer Xamarin-basierten iOS-App einzurichten. Wenn Sie XCode zur Projekterstellung verwenden, können Sie `Intune App SDK Settings.bundle` verwenden. So können Sie die Intune-Richtlinieneinstellungen ein- und ausschalten, während Sie Ihr Projekt zum Testen und Debuggen erstellen. Um das Paket bestmöglich zu nutzen, folgen Sie den Schritten im [Intune App SDK für iOS – Entwicklerhandbuch](intune-app-sdk-ios) und lesen Sie den Abschnitt zu [Debuggen in Xcode](intune-app-sdk-ios#debug-information).

## <a name="enabling-mam-in-your-android-mobile-app"></a>Aktivieren von MAM in Ihrer mobilen Android-App
Für Xamarin-basierte Android-Apps, die kein UI-Framework verwenden, lesen und befolgen Sie das [Intune App SDK für Android – Entwicklerhandbuch]. Für Xamarin-basierte Android-Apps müssen die Klasse, Methoden und Aktivitäten mit dem MAM-Äquivalent ersetzt werden, das auf der [Tabelle](intune-app-sdk-android#replace-classes-methods-and-activities-with-their-mam-equivalent-required) basiert und im Handbuch zu finden ist. Wenn Ihre App keine `android.app.Application`-Klasse definiert, müssen Sie eine erstellen. Es muss sichergestellt werden, dass Sie von `MAMApplication` erben.

Für Xamarin.Forms und andere UI-Frameworks haben wir ein Tool bereit gestellt. Es heißt `MAM.Remapper`. Das Tool wird für Sie den Klassentausch vornehmen. Folgende Schritte müssen dennoch durchgeführt werden:

1.  Fügen Sie der Version 0.1.0.0 oder höher des ` Microsoft.Intune.MAM.Remapper.Tasks`-NuGet-Pakets einen Verweis hinzu.

2.  Fügen Sie Ihrer CSPROJ-Datei von Android die folgende Zeile hinzu:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Legen Sie die Buildaktion der hinzugefügten `remapping-config.json`-Datei mit **RemappingConfigFile** fest. Die integrierte `remapping-config.json`-Datei funktioniert nur mit Xamarin.Forms. Greifen Sie für andere UI-Frameworks auf das Readme im Remapper-NuGet-Paket zurück.

## <a name="test-your-app"></a>Testen Ihrer App

Sie haben die grundlegenden Schritte zum Erstellen der Komponente auf Ihrer App abgeschlossen. Jetzt können die Schritte ausgeführt werden, die in der Xamarin Android-Beispiel-App zu finden sind. Wir haben zwei Beispiele bereit gestellt, eine für Xamarin.Forms und eine weitere für Android.



<!--HONumber=Nov16_HO3-->


