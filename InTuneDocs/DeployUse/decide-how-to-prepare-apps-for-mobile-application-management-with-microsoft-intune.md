---
title: Entscheiden Sie, wie Sie apps für die Verwaltung der mobilen Anwendung mit Microsoft Intune vorbereiten
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
author: Staciebarker
---
# Entscheiden Sie, wie Sie apps für die Verwaltung der mobilen Anwendung mit Microsoft Intune vorbereiten
Sie können Ihre apps mit Verwaltungsrichtlinien für mobile mit dem Intune App Wrapping Tool oder Intune App-SDK. Verwenden Sie diese Informationen über diese beiden Methoden und deren Verwendung.

## Intune App Wrapping Tool
Das App Wrapping Tool ist in erster Linie für internen Line-of-Business (LOB)-apps verwendet. Das Tool ist eine befehlszeilenanwendung, die einen Wrapper für die app erstellt, die dann in der app von einer Intune mobile Application Management-Richtlinie verwaltet werden können. Den Quellcode des Tools ist nicht erforderlich, jedoch benötigen Sie Anmeldeinformationen anmelden.  Weitere Informationen zum Signieren von Anmeldeinformationen finden Sie unter der [Intune-Blog](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx). Die Dokumentation der App Wrapping Tool finden Sie unter [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [iOS-App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Das App Wrapping Tool unterstützt keine Apps in der Anwendung oder Play Store oder Funktionen, die Entwicklung Zeitintegration erforderlich ist (siehe die folgende Funktion Vergleichstabelle).

Sie sollten das SDK, anstatt dem App Wrapping Tool verwenden, wenn die app bereits geschrieben wurde, oder wenn der Quellcode nicht verfügbar ist.

## Intune-App-SDK
Das App-SDK ist in erster Linie für Kunden entwickelt, die apps in der App oder Wiedergabe speichern und Sie möchten die apps mit Intune verwalten können. Allerdings kann jede app integrieren des SDK nutzen, selbst wenn es sich um eine LOB-Anwendung ist.

Um das SDK zu integrieren, benötigen Sie Zugriff auf den Quellcode der app. Eine Anleitung zur Integration des SDK finden Sie unter [Microsoft Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx).

## Vergleich der Features
Diese Tabelle enthält die Einstellungen, die Sie für die App-SDK und das App Wrapping Tool verwenden können.

> [!NOTE]
> Das App Wrapping Tool kann verwendet werden, nur, wenn Sie Intune Standalone oder Intune mit Configuration Manager verwenden.

|Komponente|App-SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Einschränken von anzuzeigenden Webinhalten in einem unternehmensverwalteten Browser|X|X|
|Verhindern von Android, iTunes oder iCloud-Sicherungen|X|X|
|App Übertragung von Daten an andere Apps erlauben|X|X|
|App Empfang von Daten aus anderen Apps erlauben|X|X|
|Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps|X|X|
|Einfache PIN für Zugriff erforderlich|X|X|
|Ersetzen Sie die integrierte app-PIN mit Intune-PIN|X||
|Geben Sie die Anzahl der Versuche vor dem Zurücksetzen der PIN|X|X|
|Erfordern Sie Fingerabdruck statt PIN (nur iOS)<br></br>**Hinweis:** nur im nur-MAM-Umgebungen verfügbar.|X||
|Unternehmensanmeldeinformationen für Zugriff erforderlich|X|X|
|Blockieren der Ausführung von verwalteten Apps auf per Jailbreak oder Rooting manipulierten Geräten|X|X|
|App-Daten verschlüsseln|X|X|
|Zugriffsanforderungen Sie der nach einer bestimmten Anzahl von Minuten|X|X|
|Geben Sie die offline-Toleranzperiode|X|X|
|Blockieren von Bildschirmaufnahmen (nur Android)|X|X|
|Vollständiges Zurücksetzen|X|X|
|Selektives Zurücksetzen <br></br>**Hinweis:** für iOS, wenn das Management-Profil entfernt wird, die app wird ebenfalls entfernt.|X||
|"Speichern unter" verhindern |X||
|Unterstützung für mehrere Identitäten|X||

### Weitere Informationen:
[Android-app Wrapping tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-toolt.md)</br>
[iOS-app Wrapping tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Verwenden des SDK für apps für die Verwaltung der mobilen Anwendung aktivieren](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=Mar16_HO3-->


