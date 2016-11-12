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
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# Erste Schritte mit dem Microsoft Intune App SDK

Dieser Leitfaden für die ersten Schritte soll Ihnen dabei helfen, Ihre mobile App schnell für die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) mit Microsoft Intune zu aktivieren. Unter Umständen ist es ratsam, sich zuerst in der [Übersicht über das Intune App SDK](intune-app-sdk.md) mit den Vorteilen des Intune App SDK vertraut machen.

In diesem Leitfaden werden die wichtigsten Schritte zum Aktivieren der Verwaltung mobiler Anwendungen in Ihrer App mit Microsoft Intune vorgestellt. Das Intune App SDK unterstützt plattformübergreifend vergleichbare Szenarien und soll für den IT-Administrator eine plattformübergreifende konsistente Umgebung darstellen. Bei der Unterstützung bestimmter Funktionen gibt es jedoch geringfügige Unterschiede, die auf Einschränkungen der jeweiligen Plattform zurückzuführen sind.

# Erste Schritte

## Registrieren Ihrer Store-App bei Microsoft

**Wenn Ihre App für die firmeninterne Verwendung bestimmt ist und nicht in einem öffentlichen App Store zur Verfügung gestellt wird**:

Dann muss die App **nicht** registriert werden. Branchenspezifische Apps werden vom IT-Administrator intern bereitgestellt. Intune erkennt, dass die App mit dem SDK erstellt wurde, und lässt zu, dass der IT-Administrator MAM-Richtlinieneinstellungen darauf anwendet. Sie können zu Abschnitt [Aktivieren von mobilen iOS- oder Android-Apps für die Verwaltung mobiler Anwendungen (MAM) mit dem SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) wechseln.

**Wenn Ihre App in einem öffentlichen App Store (z. B. im Apple App Store oder Google Play Store) freigegeben wird**: 

Dann **müssen** Sie Ihre App zuerst bei Microsoft Intune registrieren und den Registrierungsbedingungen zustimmen. Nach der Registrierung können IT-Administratoren Intune-MAM-Richtlinieneinstellungen auf die entsprechend aktivierte App anwenden, die als Intune-Partner-App aufgelistet wird. Solange die Registrierung nicht abgeschlossen ist und vom Microsoft Intune-Team bestätigt wurde, können Intune-Administratoren dem Deep-Link der App keine MAM-Richtlinie zuweisen. Microsoft fügt Ihre App auch zur Seite der [Microsoft Intune-Partner](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) hinzu, auf der das Symbol der App angezeigt wird, um anzugeben, dass sie Microsoft Intune-MAM-Richtlinien unterstützt.

Zu Beginn des Registrierungsvorgangs müssen Sie den **[Fragebogen für Microsoft Intune-App-Partner (in englischer Sprache)](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)** ausfüllen. 

Microsoft verwendet die auf dem ausgefüllten Fragebogen angegebene(n) E-Mail-Adresse(n), um sich mit Ihnen in Verbindung zu setzen und damit den Registrierungsprozess fortzusetzen. Über diese Registrierungsadresse nehmen wir bei Fragen oder Problemen auch Kontakt mit Ihnen auf.

> [!NOTE]
> Alle Daten, die in obigem Formular oder über die E-Mail-Korrespondenz mit dem Microsoft Intune-Team erfasst werden, unterliegen der [Microsoft-Datenschutzrichtlinie](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Informationen zum Registrierungsvorgang**: 

1. Nachdem Sie den Fragebogen gesendet haben, nimmt Microsoft über die bei der Registrierung angegebene E-Mail-Adresse Kontakt mit Ihnen auf, um den erfolgreichen Eingang zu bestätigen oder zusätzliche Informationen anzufordern, um die Registrierung abschließen zu können. 
2. Nachdem wir alle erforderlichen Informationen von Ihnen erhalten haben, senden wir Ihnen die Vereinbarung für Microsoft Intune-App-Partner zum Unterschreiben zu. Diese Vereinbarung enthält die Bedingungen, denen Ihr Unternehmen zustimmen muss, bevor es ein Microsoft Intune-App-Partner werden kann. 
3. Sie werden ebenso benachrichtigt, wenn Ihre App erfolgreich beim Microsoft Intune-Dienst registriert wurde und auf der [Microsoft Intune-Partnerwebsite](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) empfohlen wird. 
4. Schließlich wird der Deep-Link Ihrer App für das nächste monatliche Intune-Dienstupdate hinzugefügt. Wenn die Registrierung mit allen Informationen beispielsweise im Juli abgeschlossen ist, wird der Deep-Link der App Mitte August unterstützt. 

Wenn sich in Zukunft der Deep-Link Ihrer Store-App ändert, müssen Sie Ihre App neu registrieren. Informieren Sie uns bitte zusätzlich, wenn Sie Ihre App mit einer neuen Intune App SDK-Version aktualisieren.



## Herunterladen der SDK-Dateien

Die Intune App SDKs für natives iOS und Android werden auf einem Microsoft-GitHub-Konto gehostet. Die folgenden öffentlichen Repositorys enthalten die SDK-Dateien für IOS bzw. Android:

* [Intune App SDK für iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK für Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Wenn Ihre App eine Xamarin- oder Cordova-App ist, verwenden Sie bitte die unten stehenden Entwicklertools**:

* [Intune App SDK-Xamarin-Komponente](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK-Cordova-Plug-In](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Wir empfehlen Ihnen, sich für ein GitHub-Konto zu registrieren, mit dem Sie Fork- und Pull-Funktionen für unsere Repositorys verwenden können. GitHub bietet Entwicklern die Möglichkeit, mit unserem Produktteam zu kommunizieren, Probleme zu melden und schnelle Antworten zu erhalten, Versionshinweise anzuzeigen und Feedback an Microsoft zu senden. Wenn Sie Fragen zum GitHub-Konto und zu GitHub-Repositorys haben, senden Sie eine E-Mail an „msintuneappsdk@microsoft.com“.





## Aktivieren von mobilen iOS- oder Android-Apps für die Verwaltung mobiler Anwendungen (MAM) mit dem SDK

Damit Sie das Intune App SDK in Ihre native iOS-App integrieren können, benötigen Sie Folgendes: 

* **[Entwicklerhandbuch zum Intune App SDK für iOS](intune-app-sdk-ios.md)**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre mobile iOS-App mit dem Intune App SDK aktivieren. 


Damit Sie das Intune App SDK in Ihre Android-App integrieren können, benötigen Sie Folgendes:

* **[Entwicklerhandbuch zum Intune App SDK für Android](intune-app-sdk-android.md)**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre mobile Android-App mit dem Intune App SDK aktivieren. 

Die Dokumentation für die Intune App SDK-Xamarin-Komponente und das Intune App SDK-Cordova-Plugin finden Sie in den jeweiligen GitHub-Repositorys. 


## Konfigurieren der Telemetrie für Ihre App

Microsoft Intune sammelt Daten zu Nutzungsstatistiken für Ihre App.

* **Intune App SDK für iOS**: Das SDK protokolliert standardmäßig SDK-Telemetriedaten zu Verwendungsereignissen. Diese Daten werden an Microsoft Intune gesendet.

    * Wenn von Ihrer App keine SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, müssen Sie die Telemetrieübertragung deaktivieren, indem Sie im Wörterbuch „IntuneMAMSettings“ die Eigenschaft `MAMTelemetryDisabled` auf„JA“ festlegen.

* **Intune App SDK für Android**: Vom SDK werden keine Telemetriedaten protokolliert.

## Testen Ihrer für die Verwaltung mobiler Anwendungen (MAM) aktivierten App mit Microsoft Intune

Nachdem Sie die notwendigen Schritte zur Integration des Intune App SDK in Ihre iOS- oder Android-App abgeschlossen haben, müssen Sie sicherstellen, dass alle App-Verwaltungsrichtlinien für den Endbenutzer und IT-Administrator aktiviert und funktionsfähig sind. Zum Testen Ihrer integrierten App benötigen Sie Folgendes:

<!--TODO-->

* **Testen MAM-fähiger Apps mit Microsoft Intune**: In diesem Dokument wird Schritt für Schritt erläutert, wie Sie Ihre MAM-fähigen iOS- oder Android-Apps mit Microsoft Intune testen. Sie finden dieses Dokument in den GitHub-Repositorys der SDKs.

* **Microsoft Intune-Konto**: Zum Testen MAM-fähiger Apps mit Microsoft Intune benötigen Sie ein Microsoft Intune-Konto. 
    * ISVs, die ihre iOS- oder Android-Store-Apps für Intune MAM aktivieren, erhalten nach Abschluss der Registrierung bei Microsoft Intune (wie im Registrierungsschritt beschrieben) einen Promo-Code. Der Promo-Code bietet die Möglichkeit, sich für eine Microsoft Intune-Testversion (1 Jahr erweiterte Verwendung) anzumelden. 
    * Wenn Sie eine spartenspezifische App entwickeln, die nicht in den Store übertragen wird, sollten Sie über Ihre Organisation auf Microsoft Intune zugreifen können. Sie können sich auch bei [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) für eine kostenlose Testversion (1 Monat) registrieren.




<!--HONumber=Nov16_HO1-->


