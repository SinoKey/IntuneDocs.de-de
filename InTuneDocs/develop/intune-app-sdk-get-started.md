---
title: Erste Schritte mit dem Microsoft Intune App SDK | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8bc2f6e8dcf9d0ac3e7fccec792c86ff1fd4131c
ms.openlocfilehash: 15be877edbdeb827a4318af226ea8cde8c8e46f4


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Erste Schritte mit dem Microsoft Intune App SDK

Dieser Leitfaden unterstützt Sie dabei, Ihre mobile App schnell für die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) mit Microsoft Intune einzurichten. Unter Umständen ist es ratsam, sich zuerst in der [Übersicht über das Intune App SDK](intune-app-sdk.md) mit den Vorteilen des Intune App SDK vertraut machen.

In diesem Leitfaden werden die wichtigsten Schritte zum Einrichten der Verwaltung mobiler Anwendungen in Ihrer App mit Microsoft Intune vorgestellt. Das Intune App SDK unterstützt ähnliche Szenarien auf allen Plattformen und bietet dem IT-Administrator eine plattformübergreifend konsistente Umgebung. Bei der Unterstützung bestimmter Funktionen gibt es jedoch geringfügige Unterschiede, die auf Einschränkungen der jeweiligen Plattform zurückzuführen sind.

## <a name="register-your-store-app-with-microsoft"></a>Registrieren Ihrer Store-App bei Microsoft

**Wenn Ihre App für die firmeninterne Verwendung bestimmt ist und nicht in einem öffentlichen App Store zur Verfügung gestellt wird**:

Dann muss die App *nicht* registriert werden. Interne branchenspezifische Apps werden vom IT-Administrator intern bereitgestellt. Intune erkennt, dass die App mit dem SDK erstellt wurde, und ermöglicht dem IT-Administrator die Anwendung von MAM-Richtlinieneinstellungen auf die App. Sie können zu Abschnitt [Aktivieren von mobilen iOS- oder Android-Apps für die Verwaltung mobiler Anwendungen (MAM) mit dem SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) wechseln.

**Wenn Ihre App in einem öffentlichen App Store (z.B. im Apple App Store oder Google Play Store) freigegeben wird, gilt Folgendes**:

Sie *müssen* Ihre App zuerst bei Microsoft Intune registrieren und den Registrierungsbedingungen zustimmen. Danach können IT-Administratoren Intune-MAM-Richtlinieneinstellungen auf die entsprechend aktivierte App anwenden, die als Intune-Partner-App aufgelistet wird. Solange die Registrierung nicht abgeschlossen ist und vom Microsoft Intune-Team bestätigt wurde, können Intune-Administratoren dem Deep-Link der App keine MAM-Richtlinie zuweisen. Microsoft fügt Ihre App auch zur Seite der [Microsoft Intune-Partner](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) hinzu. Dort wird das Symbol der App angezeigt, um anzugeben, dass sie die Microsoft Intune-MAM-Richtlinie unterstützt.

Zu Beginn des Registrierungsvorgangs müssen Sie den [Fragebogen für Microsoft Intune-App-Partner](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u) ausfüllen.

Die auf dem ausgefüllten Fragebogen angegebenen E-Mail-Adressen werden verwendet, um sich mit Ihnen in Verbindung zu setzen und damit den Registrierungsprozess fortzusetzen. Über diese E-Mail-Adresse nehmen wir bei Fragen oder Problemen auch Kontakt mit Ihnen auf.

> [!NOTE]
> Alle Daten, die in diesem Fragebogen oder in der E-Mail-Korrespondenz mit dem Microsoft Intune-Team erfasst werden, unterliegen der [Microsoft-Datenschutzrichtlinie](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Informationen zum Registrierungsvorgang**:

1. Nachdem Sie den Fragebogen gesendet haben, setzen wir uns über die dort angegebene E-Mail-Adresse mit Ihnen in Verbindung, um den erfolgreichen Eingang zu bestätigen oder zusätzliche Informationen anzufordern, damit die Registrierung abgeschlossen werden kann.
2. Nachdem wir alle erforderlichen Informationen von Ihnen erhalten haben, senden wir Ihnen die Vereinbarung für Microsoft Intune-App-Partner zum Unterschreiben zu. Diese Vereinbarung enthält die Bedingungen, denen Ihr Unternehmen zustimmen muss, bevor es Microsoft Intune-App-Partner werden kann.
3. Sie werden ebenso benachrichtigt, wenn Ihre App erfolgreich beim Microsoft Intune-Dienst registriert wurde und auf der [Microsoft Intune-Partnerwebsite](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) empfohlen wird.
4. Schließlich wird der Deep-Link Ihrer App zum nächsten monatlichen Intune-Dienstupdate hinzugefügt. Wenn die Registrierung mit allen Informationen beispielsweise im Juli abgeschlossen ist, wird der Deep-Link ab Mitte August unterstützt.

Wenn sich der Deep-Link Ihrer App zu einem späteren Zeitpunkt ändert, müssen Sie Ihre App neu registrieren. Informieren Sie uns bitte zusätzlich, wenn Sie Ihre App mit einer neuen Intune App SDK-Version aktualisieren.



## <a name="download-the-sdk-files"></a>Herunterladen der SDK-Dateien

Die Intune App SDKs für natives iOS und Android werden auf einem Microsoft-GitHub-Konto gehostet. Die folgenden öffentlichen Repositorys enthalten die SDK-Dateien für iOS bzw. Android:

* [Intune App SDK für iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK für Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Wenn Ihre App eine Xamarin- oder Cordova-App ist, verwenden Sie die folgenden Entwicklertools:

* [Intune App SDK-Xamarin-Komponente](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK-Cordova-Plug-In](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Es wird empfohlen, sich für ein GitHub-Konto zu registrieren, mit dem Sie Fork- und Pullfunktionen für unsere Repositorys verwenden können. GitHub bietet Entwicklern die Möglichkeit, mit unserem Produktteam zu kommunizieren, Probleme zu melden und schnelle Antworten zu erhalten, Versionshinweise anzuzeigen und Feedback an Microsoft zu senden. Wenn Sie Fragen zum GitHub-Konto und zu GitHub-Repositorys haben, senden Sie eine E-Mail an „msintuneappsdk@microsoft.com“.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Aktivieren von mobilen iOS- oder Android-Apps für die Verwaltung mobiler Anwendungen (MAM) mit dem SDK

Damit Sie das Intune App SDK in Ihre native iOS-App integrieren können, benötigen Sie Folgendes:

* **[Entwicklerleitfaden zum Intune App SDK für iOS](intune-app-sdk-ios.md)**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre mobile iOS-App für das Intune App SDK einrichten.


Damit Sie das Intune App SDK in Ihre Android-App integrieren können, benötigen Sie Folgendes:

* **[Entwicklerleitfaden zum Intune App SDK für Android](intune-app-sdk-android.md)**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre mobile Android-App für das Intune App SDK einrichten.

Die Dokumentation für die Intune App SDK-Xamarin-Komponente und das Intune App SDK-Cordova-Plug-In finden Sie in den jeweiligen GitHub-Repositorys.


## <a name="set-up-telemetry-for-your-app"></a>Einrichten der Telemetrie für Ihre App

Microsoft Intune sammelt Daten zu Nutzungsstatistiken für Ihre App.

* **Intune App SDK für iOS**: Das SDK protokolliert standardmäßig SDK-Telemetriedaten zu Verwendungsereignissen. Diese Daten werden an Microsoft Intune gesendet.

    * Wenn von Ihrer App keine SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, müssen Sie die Telemetrieübertragung deaktivieren, indem Sie im Wörterbuch „IntuneMAMSettings“ die Eigenschaft `MAMTelemetryDisabled` auf„JA“ festlegen.

* **Intune App SDK für Android**: Vom SDK werden keine Telemetriedaten protokolliert.

## <a name="test-your-mamenabled-app-with-microsoft-intune"></a>Testen Ihrer für die Verwaltung mobiler Anwendungen (MAM) eingerichteten App mit Microsoft Intune

Nachdem Sie die notwendigen Schritte zur Integration des Intune App SDK in Ihre iOS- oder Android-App abgeschlossen haben, müssen Sie sicherstellen, dass alle App-Verwaltungsrichtlinien für den Benutzer und den IT-Administrator aktiviert und funktionsfähig sind. Zum Testen Ihrer integrierten App benötigen Sie Folgendes:

<!--TODO-->

* **Testen MAM-fähiger Apps mit Microsoft Intune**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre MAM-fähigen iOS- oder Android-Apps mit Microsoft Intune testen. Sie finden dieses Dokument in den GitHub-Repositorys der SDKs.

* **Microsoft Intune-Konto**: Zum Testen MAM-fähiger Apps mit Microsoft Intune benötigen Sie ein Microsoft Intune-Konto.
    * ISVs, die ihre iOS- oder Android-Store-Apps für Intune MAM aktivieren, erhalten nach Abschluss der Registrierung bei Microsoft Intune (wie im Registrierungsschritt beschrieben) einen Angebotscode. Mit diesem Angebotscode können Sie sich für eine Microsoft Intune-Testversion mit einem Jahr erweiterter Nutzung anmelden.
    * Wenn Sie eine branchenspezifische App entwickeln, die nicht in den Store übertragen wird, sollten Sie über Ihre Organisation auf Microsoft Intune zugreifen können. Sie können sich auch bei [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) für eine kostenlose einmonatige Testversion registrieren.



<!--HONumber=Nov16_HO3-->


