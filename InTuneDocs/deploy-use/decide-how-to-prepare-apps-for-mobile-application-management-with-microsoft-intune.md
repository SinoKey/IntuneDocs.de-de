---
title: "Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune | Microsoft Docs"
description: "Die Informationen in diesem Thema unterstützen Sie bei der Entscheidung, wann Sie das App Wrapping Tool und das App SDK verwenden sollten, um Ihrer benutzerdefinierten Reihe von Branchen-Apps die Verwendung der Verwaltungsrichtlinien für mobile Apps zu ermöglichen."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/8/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b15f56f6e771faeb924668aa68140ab89a174b8d
ms.openlocfilehash: c9bba34d2252e6b9dff295724f9c935c558aa179


---

# <a name="prepare-line-of-business-apps-for-mam"></a>Vorbereiten von Branchen-Apps für MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sie können Ihre Apps mit dem Intune App Wrapping Tool oder Intune App-SDK für die Verwendung von Verwaltungsrichtlinien für mobile Anwendungen (MAM, Mobile Application Management) aktivieren. Verwenden Sie diese Informationen, um diese beiden Methoden und den Zeitpunkt für ihre Verwendung kennenzulernen.

## <a name="intune-app-wrapping-tool"></a>Intune App Wrapping Tool
Das App Wrapping Tool wird in erster Linie für interne Line-of-Business-Apps (LOB) verwendet. Das Tool ist eine Befehlszeilenanwendung, die einen Wrapper für die App erstellt, der es der App anschließend ermöglicht, von einer Intune-Verwaltungsrichtlinie für mobile Anwendungen verwaltet zu werden.

Der Quellcode ist für die Verwendung des Tools nicht erforderlich, aber Sie benötigen entsprechende Anmeldeinformationen.  Weitere Informationen zu Anmeldeinformationen finden Sie im [Intune-Blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Die Dokumentation zum App Wrapping Tool finden Sie unter [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Das App Wrapping Tool unterstützt **keine** Apps im Apple App Store oder Google Play Store. Es unterstützt auch keine bestimmten Features, die Entwicklerintegration erfordern (siehe die folgende Featurevergleichstabelle).


Weitere Informationen zum App Wrapping Tool für MAM auf Geräten, die nicht bei Intune registriert sind, finden Sie unter [Schützen von branchenspezifischen Apps und Daten auf nicht in Microsoft Intune registrierten Geräten](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Gründe für die Verwendung des App Wrapping Tools:
* Ihre App verfügt nicht über integrierte Datenschutzfunktionen.
* Ihre App ist einfach.
* Ihre App wird intern bereitgestellt.
* Sie haben keinen Zugriff auf den Quellcode der App.
* Sie haben die App nicht entwickeln.
* Ihre App verfügt über eine minimale Benutzeroberfläche für die Authentifizierung.


### <a name="supported-app-development-platforms"></a>Unterstützte App-Entwicklungsplattformen

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Ja|Ja|
|**Android**| Nein |Ja|

## <a name="intune-app-sdk"></a>Intune App SDK
Das App SDK ist in erster Linie für Kunden konzipiert, die über Apps im Apple App Store oder Google Play Store verfügen und diese Apps mit Intune verwalten möchten. Das SDK kann jedoch in jede App integriert werden, auch in branchenspezifische Apps.

Weitere Informationen zum SDK finden Sie unter [Übersicht](/intune/develop/intune-app-sdk). Ein Einführung in das SDK finden Sie unter [Erste Schritte mit dem Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started).

### <a name="reasons-to-use-the-sdk"></a>Gründe für die Verwendung des SDKs
* Ihre App verfügt nicht über integrierte Datenschutzfunktionen.
* Ihre App ist komplex und enthält viele Oberflächen.
* Ihre App wird in einem öffentlichen App Store wie Google Play oder Apple App Store bereitgestellt.
* Sie sind ein App-Entwickler mit dem technischen Hintergrund zur Verwendung des SDKs.
* Ihre App verfügt über andere SDK-Integrationen.
* Ihre App wird regelmäßig aktualisiert.

### <a name="supported-app-development-platforms"></a>Unterstützte App-Entwicklungsplattformen

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ja – [Intune App SDK-Xamarin-Komponente](/../develop/intune-app-sdk-xamarin) verwenden|Ja – [Intune App SDK-Cordova-Plug-In](/../develop/intune-app-sdk-cordova) verwenden|
|**Android**| Ja – [Intune App SDK-Xamarin-Komponente](/../develop/intune-app-sdk-xamarin) verwenden|Ja – [Intune App SDK-Cordova-Plug-In](/../develop/intune-app-sdk-cordova) verwenden|

## <a name="feature-comparison"></a>Funktionsvergleich
In dieser Tabelle sind die Einstellungen aufgeführt, die Sie für das App SDK und App Wrapping Tool verwenden können.

> [!NOTE]
> Das App Wrapping Tool kann mit eigenständigen Intune-Bereitstellungen oder mit Intune mit Configuration Manager verwendet werden.

|Komponente|App SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Einschränken von anzuzeigenden Webinhalten in einem unternehmensverwalteten Browser|X|X|
|Verhindern von Android-, iTunes- oder iCloud-Sicherungen|X|X|
|App Übertragung von Daten an andere Apps erlauben|X|X|
|App Empfang von Daten aus anderen Apps erlauben|X|X|
|Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps|X|X|
|Einfache PIN für Zugriff erforderlich|X|X|
|Ersetzen der integrierten App-PIN durch die Intune-PIN|X||
|Angeben der Anzahl von Versuchen vor dem Zurücksetzen der PIN|X|X|
|Fingerabdruck anstelle von PIN zulassen |X|X|
|Unternehmensanmeldeinformationen für Zugriff erforderlich|X|X|
|Blockieren der Ausführung von verwalteten Apps auf per Jailbreak oder Rooting manipulierten Geräten|X|X|
|App-Daten verschlüsseln|X|X|
|Erneutes Überprüfen der Zugriffsanforderungen nach einer angegebenen Anzahl von Minuten|X|X|
|Angeben der Offlinetoleranzperiode|X|X|
|Blockieren von Bildschirmaufnahmen (nur Android)|X|X|
|Vollständiges Zurücksetzen|X|X|
|Selektives Zurücksetzen <br></br>**Hinweis:** Für iOS wird die App auch entfernt, wenn das Verwaltungsprofil entfernt wird.|X||
|Verhindern von „Speichern unter“ |X||
|Unterstützung von mehreren Identitäten|X||
|Unterstützung von MAM ohne Geräteregistrierung|X|X|
|Anpassbarer Stil |X|||
### <a name="see-also"></a>Weitere Informationen:

[Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Verwenden des SDK zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Feb17_HO2-->


