---
title: "Vorbereiten von Apps für die Verwaltung von mobilen Anwendungen | Microsoft Intune"
description: "Die Informationen in diesem Thema unterstützen Sie bei der Entscheidung, wann Sie das App Wrapping-Tool und die App-SDK verwenden sollten, um Ihrer benutzerdefinierten Reihe von Branchen-Apps die Verwendung der Verwaltungsrichtlinien für mobile Apps zu ermöglichen."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 70f9fb5580b114fe1ba14a1bd05de58467d5cd00
ms.openlocfilehash: b5dd5bec0910a8ce3a940b5ed288907aba0f7ee4


---

# Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune
Sie können Ihre Apps mit dem Intune App Wrapping Tool oder Intune App-SDK für die Verwendung von Verwaltungsrichtlinien für mobile Anwendungen (MAM, Mobile Application Management) aktivieren. Verwenden Sie diese Informationen, um diese beiden Methoden und den Zeitpunkt für ihre Verwendung kennenzulernen.

## Intune App Wrapping Tool
Das App Wrapping Tool wird in erster Linie für interne Line-of-Business-Apps (LOB) verwendet. Das Tool ist eine Befehlszeilenanwendung, die einen Wrapper für die App erstellt, der es der App dann ermöglicht, von der Intune-Verwaltungsrichtlinie für mobile Anwendungen verwaltet zu werden. Der Quellcode ist für die Verwendung des Tools nicht erforderlich, aber Sie benötigen entsprechende Anmeldeinformationen.  Weitere Informationen zu Anmeldeinformationen finden Sie im [Intune-Blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Die Dokumentation zum App Wrapping Tool finden Sie unter [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Das App Wrapping Tool unterstützt keine Apps im App Store oder Play Store oder Features, die eine Integration zur Entwicklungszeit erfordern (weitere Informationen finden Sie in der folgenden Tabelle zum Funktionsvergleich).

Sie sollten das App Wrapping Tool anstelle des SDKs verwenden, wenn die App bereits erstellt wurde oder der Quellcode nicht verfügbar ist.

**Das App Wrapping Tool für MAM auf Geräten, die nicht bei Intune registriert sind, wird aktuell als öffentliche Vorschau unterstützt. Weitere Informationen finden Sie im Thema [Schützen von Branchenanwendungen auf Geräten, die nicht bei Intune registriert sind](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)**.

### Unterstützte Plattformen

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Ja|Ja|
|**Android**| Nein |Ja|
## Intune App SDK
Das App-SDK ist in erster Linie für Kunden konzipiert, die im App Store oder Play Store über Apps verfügen und diese Apps mit Intune verwalten möchten. Allerdings kann jede App die Integration des SDKs nutzen, selbst wenn es sich um eine LOB-Anwendung handelt.

Weitere Informationen zum SDK finden Sie unter [Übersicht](/intune/develop/intune-app-sdk). Ein Einführung in das SDK finden Sie unter [Erste Schritte mit dem Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started).

### Unterstützte Plattformen
|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ja – Intune App SDK-Xamarin-Komponente verwenden|Ja – Intune App SDK-Cordova-Plug-In verwenden|
|**Android**| Ja – Intune App SDK-Xamarin-Komponente verwenden|Ja – Intune App SDK-Cordova-Plug-In verwenden|

## Funktionsvergleich
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
|Erfordern des Fingerabdrucks anstelle der PIN (nur iOS)<br></br>**Hinweis:** Nur in reinen MAM-Umgebungen verfügbar.|X||
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
### Weitere Informationen:

[Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Verwenden des SDKs zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO2-->


