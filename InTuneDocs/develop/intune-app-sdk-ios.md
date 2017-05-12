---
title: "Entwicklerhandbuch für Microsoft Intune App SDK für iOS| Microsoft-Dokumentation"
description: "Das Microsoft Intune App SDK für iOS ermöglicht die Integration von App-Schutzrichtlinien in Form von Intune Mobile App Management (MAM) in Ihre iOS-App."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df54ac3a62b5ef21e8a32f3a282dd5299974a1b0
ms.openlocfilehash: 1d2cb0d4b9442262c562e559a675f5a4a28ee572
ms.contentlocale: de-de
ms.lasthandoff: 05/03/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Entwicklerhandbuch für Microsoft Intune App SDK für iOS

> [!NOTE]
> Lesen Sie am besten zuerst den Artikel [Erste Schritte mit dem Intune App SDK](intune-app-sdk-get-started.md). Darin finden Sie Informationen, welche Vorbereitungen Sie für die Integration auf jeder unterstützten Plattform treffen müssen.

Das Microsoft Intune App SDK für iOS ermöglicht die Integration von App-Schutzrichtlinien in Ihre native iOS-App. Diese Richtlinien werden auch als **APP**- oder **MAM-Richtlinien** bezeichnet. Als MAM-fähige App wird eine App bezeichnet, die in das Intune App SDK integriert ist. IT-Administratoren können App-Schutzrichtlinien in Ihren mobilen Apps bereitstellen, wenn diese aktiv von Intune verwaltet werden.

## <a name="prerequisites"></a>Voraussetzungen

* Sie benötigen einen macOS-Computer, auf dem OS X 10.8.5 oder höher ausgeführt wird und auf dem Xcode 8 oder höher installiert ist.

* Das Zielbetriebssystem Ihrer App muss iOS 9 oder höher sein.

* Lesen Sie die [Lizenzbedingungen für das Intune App SDK für iOS (in englischer Sprache)](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Drucken Sie sich eine Kopie der Lizenzbedingungen aus und bewahren Sie diese in Ihren Unterlagen auf. Mit dem Download und der Verwendung des Intune App SDK für iOS stimmen Sie diesen Lizenzbedingungen zu.  Wenn Sie den Lizenzbedingungen nicht zustimmen, verwenden Sie die Software nicht.

* Die Dateien für das Intune App SDK für iOS können Sie von [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) herunterladen.

## <a name="whats-in-the-sdk"></a>Inhalt des SDK

Das Intune App SDK für iOS enthält eine statische Bibliothek, Ressourcendateien, API-Header, eine PLIST-Datei mit Debug-Einstellungen sowie ein Konfigurationstool. Mobile Apps können einfach nur die Ressourcendateien enthalten und statisch mit den Bibliotheken verknüpft sein, um die meisten Richtlinien durchzusetzen. Erweiterte Intune-MAM-Funktionen werden mithilfe von APIs erzwungen.

In diesem Handbuch werden folgende Komponenten der Intune App SDK für iOS besprochen:

* **libIntuneMAM.a**: Die statische Intune App SDK-Bibliothek. Wenn keine Erweiterungen in Ihrer App verwendet werden, verknüpfen Sie diese Bibliothek mit Ihrem Projekt, um Ihre App für die mobile App-Verwaltung mit Intune zu aktivieren.

* **IntuneMAM.framework**: Das Intune App SDK-Framework. Verknüpfen Sie dieses Framework mit Ihrem Projekt, um Ihre App für die mobile App-Verwaltung mit Intune zu aktivieren. Verwenden Sie das Framework anstelle der statischen Bibliothek, wenn in Ihrer App Erweiterungen verwendet werden, damit Ihr Projekt nicht mehrere Kopien der statischen Bibliothek erstellt.

* **IntuneMAMResources.Bundle**: Ein Ressourcenpaket, das die Ressourcen für das SDK enthält.

* **Headers**: Stellt die Intune App SDK-APIs bereit. Wenn Sie eine API verwenden, müssen Sie die Headerdatei einschließen, die die API enthält. Die folgenden Headerdateien enthalten die API-Funktionsaufrufe, die erforderlich sind, um die Funktionalität des Intune App SDK zu aktivieren:

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Funktionsweise des Intune App SDK

Ziel des Intune App SDK für iOS ist es, iOS-Anwendungen mit minimalen Codeänderungen mit Verwaltungsfunktionen zu versehen. Je weniger der Code sich ändert, desto schneller die Marktreife, ohne dass dabei die Konsistenz oder Stabilität Ihrer mobilen App beeinträchtigt wird.


## <a name="build-the-sdk-into-your-mobile-app"></a>Integrieren der SDK in Ihre mobile App

Führen Sie die folgenden Schritte aus, um das Intune App SDK zu aktivieren:

1. **Option 1 (empfohlen)**: Verknüpfen Sie `IntuneMAM.framework` mit Ihrem Projekt. Ziehen Sie `IntuneMAM.framework` in die Liste **Verknüpfte Frameworks und Bibliotheken** des Projektziels.

    > [!NOTE]
    > Wenn Sie das Framework verwenden, müssen Sie die Simulatorstrukturen aus dem universellen Framework entfernen, bevor Sie Ihre App im App Store einreichen. Weitere Informationen finden Sie unter [Submit your app to the App Store (Einreichen Ihrer App im App Store)](#Submit-your-app-to-the-App-Store).

2. **Option 2**: Stellen Sie eine Verknüpfung zur `libIntuneMAM.a`-Bibliothek her. Ziehen Sie `libIntuneMAM.a` in die Liste **Verknüpfte Frameworks und Bibliotheken** des Projektziels.

    ![Intune App SDK für iOS: verknüpfte Frameworks und Bibliotheken](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Wenn sie Ihre App im App Store veröffentlichen möchten, verwenden Sie bitte die Version von `libIntuneMAM.a`, die für die Veröffentlichung erstellt wurde, und nicht die Debugversion. Die Veröffentlichungsversion befindet sich im Ordner **Release** (Version). Die Debugversion verfügt über eine ausführliche Ausgabe, die bei der Problembehebung mit dem Intune App SDK nützlich ist.

    Fügen Sie `-force_load {PATH_TO_LIB}/libIntuneMAM.a` an einer der folgenden Stellen ein, und ersetzen Sie `{PATH_TO_LIB}` durch den Speicherort des Intune App SDK:
      * in der Buildkonfigurationseinstellung `OTHER_LDFLAGS` des Projekts
      * in **Other Linker Flags** (Andere Linker-Flags) der Benutzeroberfläche

        > [!NOTE]
        > Wählen Sie die Datei `libIntuneMAM.a` aus, und wählen Sie dann **Get Info** (Informationen abrufen) aus dem Menü **Datei** aus, um `PATH_TO_LIB` zu finden. Kopieren Sie die Informationen aus **Where** (Wo) (der Pfad) aus dem Abschnitt **General** (Allgemein) im Fenster **Info**, und fügen Sie sie ein.

3. Fügen Sie folgende iOS-Frameworks in das Projekt ein:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. Fügen Sie das Ressourcenpaket `IntuneMAMResources.bundle` zum Projekt hinzu, indem Sie es unter **Copy Bundle Resources** (Paketressourcen kopieren) in **Build Phases** (Buildphasen) ziehen.

    ![Intune App SDK iOS: Paketressourcen kopieren](../media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Wenn Ihre mobile App in ihrer info.plist-Datei eine Haupt-NIB- oder Storyboarddatei definiert, entfernen Sie das/die Feld(er) **Hauptstoryboard** oder **Haupt-NIB**. Fügen Sie diese Felder in „info.plist“ in einem neuen Wörterbuch mit dem Namen **IntuneMAMSettings** mit den folgenden Schlüsselnamen (sofern zutreffend) hinzu:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Wenn in Ihrer mobilen App keine Haupt-NIB oder Storyboarddatei in der info.plist-Datei definiert ist, sind diese Einstellungen nicht erforderlich.

    Sie können die info.plist-Datei im RAW-Format anzeigen (um die Schlüsselnamen zu sehen), indem Sie mit der rechten Maustaste an eine beliebige Stelle im Dokument klicken und den Anzeigetyp auf **Show Raw Keys/Values** (RAW-Schlüsselnamen/-Werte anzeigen) ändern.

6. Aktivieren Sie die Freigabe des Schlüsselbunds (sofern noch nicht geschehen), indem Sie in jedem Projektziel auf **Eigenschaften** klicken und den Schalter **Schlüsselbundfreigabe** umlegen. Die Freigabe des Schlüsselbunds ist für den nächsten Schritt erforderlich.

  > [!NOTE]
    > Ihr Bereitstellungsprofil muss neue Werte für die Freigabe des Schlüsselbunds unterstützen. Die Schlüsselsammlungs-Zugriffsgruppen sollten ein Platzhalterzeichen unterstützen. Sie können dies überprüfen, indem Sie die Datei „.mobileprovision“ in einem Text-Editor öffnen, nach **keychain-access-groups** suchen und sich vergewissern, dass ein Platzhalter vorhanden ist. Beispiel:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Nachdem Sie die Freigabe des Schlüsselbunds aktiviert haben, führen Sie folgende Schritte aus, um eine separate Zugriffsgruppe zu erstellen, in der die Daten des Intune App SDK gespeichert werden. Sie können eine Zugriffsgruppe für den Schlüsselbund über die Benutzeroberfläche oder mithilfe der Berechtigungsdatei erstellen. Wenn Sie die Benutzeroberfläche zum Erstellen der Zugriffsgruppe für den Schlüsselbund verwenden, führen Sie die unten stehenden Schritte aus:

    1. Wenn in Ihrer mobilen App keine Zugriffsgruppen für den Schlüsselbund definiert sind, fügen Sie die Paket-ID der App als erste Gruppe hinzu.

    2. Fügen Sie die freigegebene Schlüsselbundgruppe `com.microsoft.intune.mam` in Ihre vorhandene Zugriffsgruppe ein. Diese Zugriffsgruppe wird vom Intune App SDK zum Speichern von Daten verwendet.

    3. Fügen Sie `com.microsoft.adalcache` in Ihre vorhandene Zugriffsgruppe ein.

        4. Fügen Sie `com.microsoft.workplacejoin` in Ihre vorhandene Zugriffsgruppe ein.
            ![Intune App SDK für iOS: Schlüsselbundfreigabe](../media/intune-app-sdk-ios-keychain-sharing.png)

      5. Wenn Sie die Berechtigungsdatei verwenden, um die Zugriffsgruppe für den Schlüsselbund zu erstellen, müssen Sie der Zugriffsgruppe für den Schlüsselbund in der Berechtigungsdatei `$(AppIdentifierPrefix)` voranstellen. Beispiel:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Eine Berechtigungsdatei ist eine XML-Datei, die Ihrer App eindeutig zugeordnet werden kann. Sie wird zum Angeben besonderer Berechtigungen und Eigenschaften in Ihrer iOS-App verwendet.

7. Wenn in der info.plist-Datei der App URL-Schemas definiert sind, fügen Sie ein weiteres Schema mit dem Suffix `-intunemam` für jedes URL-Schema hinzu.

8. Geben Sie für Apps, die unter iOS 9 oder höher entwickelt wurden, jedes Protokoll an, dass Ihre App im `LSApplicationQueriesSchemes`-Array der info.plist-Datei Ihrer App an `UIApplication canOpenURL` übergibt. Fügen Sie zusätzlich für jedes aufgelistete Protokoll ein neues Protokoll hinzu und fügen Sie dieses mit `-intunemam` an. Außerdem müssen Sie `http-intunemam`, `https-intunemam` und `ms-outlook-intunemam` im Array einschließen.

9. Wenn in den Berechtigungen der App App-Gruppen definiert sind, fügen Sie diese Gruppen dem Wörterbuch **IntuneMAMSettings** unter dem Schlüssel `AppGroupIdentifiers` als Zeichenfolgenarray hinzu.



## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurieren der Azure Active Directory Authentication Library (ADAL)

Das Intune App SDK verwendet [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) für die Authentifizierung und Szenarios für einen bedingten Start. Außerdem ist es davon abhängig, dass ADAL die Benutzeridentität im MAM-Dienst für das Verwalten registriert, ohne dafür Geräteregistrierungsszenarios zu benötigen.

Normalerweise setzt ADAL voraus, dass Apps sich in Azure Active Directory (AAD) registrieren und eine eindeutige ID (Client-ID) sowie weitere Bezeichner erhalten, um die Sicherheit der Token zu gewährleisten, die an die Anwendung übermittelt werden. Wenn nicht anders angegeben, verwendet das Intune App SDK Standardregistrierungswerte, wenn es Azure AD kontaktiert.  

Wenn Ihre App bereits ADAL für die Authentifizierung von Benutzern verwendet, muss sie die bereits vorhandenen Registrierungswerte verwenden und die Standardwerte des Intune App SDK überschreiben. So wird sichergestellt, dass Benutzer nicht zweimal aufgefordert werden, sich zu authentifizieren (jeweils einmal vom Intune App SDK und einmal von der App).

### <a name="recommendations"></a>Empfehlungen

Es wird empfohlen, dass Ihre App eine Verknüpfung mit der [aktuellsten Version von ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) in ihrem Masterbranch herstellt. Das Intune App SDK verwendet im Moment den Brokerbranch von ADAL zur Unterstützung von Apps, die einen bedingten Zugriff erfordern. (Deshalb hängen diese Apps von der Microsoft Authenticator-App ab.) Das SDK ist allerdings immer noch mit dem Masterbranch von ADAL kompatibel. Verwenden Sie den Branch, der am besten zu Ihrer App passt.

### <a name="link-to-adal-binaries"></a>Verknüpfen mit ADAL-Binärdateien

Führen Sie die unten stehenden Schritte durch, um Ihre App mit ADAL-Binärdateien zu verknüpfen:

1. Laden Sie [Azure Active Directory Authentication Library (ADAL) für Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) von GitHub herunter, und folgen Sie dann den [Anweisungen](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) zum Herunterladen von ADAL mit Git-Submodulen oder CocoaPods.

2. Schließen Sie das Ressourcenpaket `ADALiOSBundle.bundle` in das Projekt ein, indem Sie es unter **Copy Bundle Resources** (Paketressourcen kopieren) in **Build Phases** (Buildphasen) ziehen.

3. Fügen Sie `-force_load {PATH_TO_LIB}/libADALiOS.a` in die `OTHER_LDFLAGS`-Konfigurationseinstellung des Projekts oder in **Other Linker Flags** (Andere Linker-Flags) der Benutzeroberfläche ein. `PATH_TO_LIB` sollte durch den Speicherort der ADAL-Binärdateien ersetzt werden.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Freigabe des Tokencaches von ADAL für andere Apps, die mit demselben Bereitstellungsprofil signiert wurden.**

Führen Sie die unten stehenden Schritte aus, wenn Sie ADAL-Token zwischen Apps freigeben möchten, die mit demselben Bereitstellungsprofil signiert wurden:

1. Wenn in Ihrer App keine Zugriffsgruppen für den Schlüsselbund definiert sind, fügen Sie die Paket-ID der App als erste Gruppe hinzu.

2. Aktivieren Sie das einmalige Anmelden (Single Sign-On, SSO) in ADAL, indem Sie die Zugriffsgruppen `com.microsoft.adalcache` und `com.microsoft.workplacejoin` in den Schlüsselbundberechtigungen einfügen.

3. Wenn Sie die Schlüsselbundgruppe für die Cachefreigabe in ADAL explizit angeben, achten Sie darauf, dass sie auf `<app_id_prefix>.com.microsoft.adalcache` festgelegt ist. Dies wird für Sie von ADAL festgelegt, wenn Sie es nicht überschreiben. Wenn Sie eine benutzerdefinierte Schlüsselbundgruppe als Ersatz für `com.microsoft.adalcache` festlegen möchten, können Sie dies in der info.plist-Datei unter IntuneMAMSettings mit dem Schlüssel `ADALCacheKeychainGroupOverride` tun.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Konfigurieren der ADAL-Einstellungen für das Intune App SDK

Wenn Ihre App bereits ADAL für die Authentifizierung verwendet und über eigene ADAL-Einstellungen verfügt, können Sie das Intune SDK dazu zwingen, während der Authentifizierung von Azure AD die gleichen Einstellungen zu verwenden. So wird sichergestellt, dass die App den Benutzer nicht zweimal auffordert, sich zu authentifizieren. Weitere Informationen zum Ausfüllen folgender Einstellungen finden Sie unter [Configure settings for the Intune App SDK (Konfigurieren der Einstellungen des Intune App SDK)](#configure-settings-for-the-intune-app-sdk):  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Wenn Ihre App bereits ADAL verwendet, sind folgende Konfigurationen erforderlich:

1. Geben Sie in der info.plist-Datei des Projekts unter dem Wörterbuch **IntuneMAMSettings** mit dem Schlüsselnamen `ADALClientId` die Client-ID an, die für ADAL-Aufrufe verwendet werden soll.

2. Geben Sie außerdem unter dem Wörterbuch **IntuneMAMSettings** mit dem Schlüsselnamen `ADALAuthority` die Azure AD-Autorität an.

3. Geben Sie außerdem unter dem Wörterbuch **IntuneMAMSettings** mit dem Schlüsselnamen `ADALRedirectUri` den Umleitungs-URI an, der für ADAL-Aufrufe verwendet werden soll. Je nach Format des Umleitungs-URIs Ihrer App müssen Sie auch `ADALRedirectScheme` angeben.


Zusätzlich können Sie die Autoritäts-URL von Azure AD zur Laufzeit mit einer mandantenspezifischen URL überschreiben. Legen Sie dazu einfach die `aadAuthorityUriOverride`-Eigenschaft auf der `IntuneMAMPolicyManager`-Instanz fest.

> [!NOTE]
> Für [APP without device enrollment (App-Schutzrichtlinien (APP) ohne Geräteregistrierung)](#App-protection-policy-without-device-enrollment) ist das Festlegen der Autoritäts-URL von Azure AD erforderlich, damit das SDK das von der App abgerufene Aktualisierungstoken wiederverwenden kann.

Das SDK verwendet diese Autoritäts-URL weiterhin für die Richtlinienaktualisierung und alle weiteren Registrierungsanfragen, wenn der Wert nicht gelöscht oder verändert wird.  Deshalb ist es wichtig, dass Sie den Wert löschen, wenn sich ein verwalteter Benutzer aus der App abmeldet, und dass Sie den Wert zurücksetzen, wenn sich ein neuer verwalteter Benutzer anmeldet.

### <a name="if-your-app-does-not-use-adal"></a>Wenn Ihre App ADAL nicht verwendet

Wenn Ihre App ADAL nicht verwendet, stellt das Intune App SDK Standardwerte für ADAL-Parameter und behandelt die Authentifizierung in Azure AD. Für die oben aufgeführten ADAL-Einstellungen müssen Sie keine Werte festlegen.

## <a name="app-protection-policy-without-device-enrollment"></a>App-Schutzrichtlinie ohne Geräteregistrierung

### <a name="overview"></a>Übersicht
Mit App-Schutzrichtlinien ohne Geräteregistrierung (auch als **APP-WE** oder MAM-WE bezeichnet) können Apps von Intune verwaltet werden, ohne dass das Gerät für die Verwaltung mobiler Geräte mit Intune (Mobile Device Management, MDM) registriert werden muss. Für diese neue Funktion muss die App an der Registrierung von Benutzerkonten für die Verwaltung teilnehmen. Führen Sie folgende Schritte aus, um die neuen APIs zu nutzen:

1. Verwenden Sie die aktuellste Version des Intune App SDK, das das Verwalten von Apps mit und ohne Geräteregistrierung unterstützt.

2. Fügen Sie „intuneMAMEnrollment.h“ in jede Datei ein, die die APIs aufruft.

### <a name="register-user-accounts"></a>Registrieren von Benutzerkonten

Eine App kann eine App-Schutzrichtlinie vom Intune-Dienst erhalten, wenn die App in APP-WE im Namen eines bestimmten Benutzers registriert ist. Die App ist dafür zuständig, jeden neu angemeldeten Benutzer im SDK zu registrieren. Nachdem das neue Benutzerkonto authentifiziert wurde, sollte die App die `registerAndEnrollAccount`-Methode unter Header/IntuneMAMEnrollment.h aufrufen:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Wenn die `registerAndEnrollAccount`-Methode aufgerufen wird, registriert das SDK das Benutzerkonto und versucht, die App im Namen dieses Kontos zu registrieren. Wenn die Registrierung fehlschlägt, führt das SDK den Registrierungsprozess automatisch 24 Stunden später erneut durch. Die App kann zum Debuggen Benachrichtigungen über einen Delegaten empfangen, die Auskünfte über die Ergebnisse einer Registrierungsanfrage geben.

Nachdem diese API aufgerufen wurde, kann die App wie gewohnt ausgeführt werden. Wenn die Registrierung erfolgreich abgeschlossen werden kann, benachrichtigt die App den Benutzer, dass ein Neustart der App erforderlich ist. Nun kann der Benutzer die App sofort neu starten.

### <a name="deregister-user-accounts"></a>Registrierung von Benutzerkonten aufheben

Bevor ein Benutzer aus einer App abgemeldet wird, ist es am besten, wenn die App die Registrierung des Benutzers im SDK aufhebt. So wird sichergestellt:

1. dass der Registrierungsprozess für dieses Benutzerkonto nicht wiederholt durchgeführt wird

2. dass die App-Schutzrichtlinie entfernt wird

3. dass Unternehmensdaten gelöscht werden, wenn die App selektiv zurückgesetzt wird (optional)

Bevor der Benutzer abgemeldet wird, sollte die App die folgende API in `Headers/IntuneMAMEnrollment.h` aufrufen:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Diese Methode muss aufgerufen werden, bevor die Azure AD-Token des Benutzerkontos gelöscht werden. Für das SDK müssen das/die Azure AD-Token des Benutzerkontos spezifische Anfragen an den APP-WE-Dienst im Namen des Benutzers durchführen.

Wenn die App die Unternehmensdaten des Benutzers von alleine löscht, kann das `doWipe`-Flag auf „FALSE“ festgelegt werden. Andernfalls kann die App das SDK dazu veranlassen, einen Prozess zum selektiven Zurücksetzen zu initiieren. Dies führt zu einem Aufruf des Delegaten für das selektive Zurücksetzen der App.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>Apps, die ADAL nicht verwenden

Apps, die den Benutzer nicht mithilfe von ADAL registrieren, können immer noch App-Schutzrichtlinien des Intune-Diensts erhalten, indem sie die API aufrufen, sodass das SDK die Authentifizierung übernimmt. Apps verwenden diese Vorgehensweise am besten, wenn sie keinen Benutzer in Azure AD authentifiziert haben, aber trotzdem App-Schutzrichtlinien zum Schutz von Daten abrufen müssen. Ein derartiger Fall tritt z.B. ein, wenn ein anderer Authentifizierungsdienst für die Anmeldung in der App eingesetzt wird, oder wenn die App keine Anmeldung unterstützt. Dazu sollte die App die `loginAndEnrollAccount`-Methode unter Header/IntuneMAMEnrollment.h aufrufen:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Wenn diese Methode aufgerufen wird, fordert das SDK den Benutzer auf, Anmeldeinformationen einzugeben, wenn kein vorhandenes Token gefunden werden kann. Anschließend versucht das SDK, die App im APP-WE-Dienst im Namen des angegebenen Benutzerkontos zu registrieren. Die Methode kann mit „nil“ als Identität aufgerufen werden. In diesem Fall registriert das SDK beim vorhandenen verwalteten Benutzer auf dem Gerät oder fordert den Benutzer auf, einen Benutzernamen einzugeben, wenn kein vorhandener Benutzer gefunden werden konnte.

Wenn die Registrierung fehlschlägt, sollte die App die API am besten zu einem späteren Zeitpunkt erneut aufrufen, je nach den Gründen für die nicht erfolgreiche Registrierung. Die App kann [Benachrichtigungen](#Status-result-and-debug-notifications) über einen Delegaten empfangen, die Auskunft über die Ergebnisse einer Registrierungsanfrage geben.

Nachdem diese API aufgerufen wurde, kann die App wie gewohnt ausgeführt werden. Wenn die Registrierung erfolgreich abgeschlossen werden kann, benachrichtigt die App den Benutzer, dass ein Neustart der App erforderlich ist.

## <a name="status-result-and-debug-notifications"></a>Status-, Ergebnis- und Debugbenachrichtigungen

Die App kann Benachrichtigungen zum Status, Ergebnis und Debuggen bezüglich folgender Anfragen an den Intune MAM-Dienst empfangen:

 - Registrierungsanfragen
 - Anfragen zur Richtlinienaktualisierung
 - Anfragen zur Aufhebung der Registrierung

Die Benachrichtigungen werden als Delegatmethoden in `Headers/IntuneMAMEnrollmentDelegate.h` dargestellt:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Diese Delegatmethoden geben ein `IntuneMAMEnrollmentStatus`-Objekt zurück, das folgende Informationen enthält:

- die Identität des Kontos, von dem die Anfrage stammt
- einen Statuscode, der das Ergebnis der Anfrage angibt
- eine Fehlerzeichenfolge mit einer Beschreibung des Statuscodes
- ein `NSError`-Objekt

Dieses Objekt ist in `IntuneMAMEnrollmentStatus.h` gemeinsam mit dem spezifischen Statuscode definiert, der zurückgegeben werden kann.


### <a name="sample-code"></a>Beispielcode

Dies sind Beispielimplementierungen der Delegatmethoden:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>App-Neustart

Wenn eine App App-Schutzrichtlinien zum ersten Mal erhält, muss sie neu gestartet werden, um die erforderlichen Hooks zu übernehmen. Das SDK stellt eine Delegatmethode unter Header/IntuneMAMEnrollment.h bereit, um die App zu informieren, dass sie neu gestartet werden muss.

```objc
 - (BOOL) restartApplication
```
Der Rückgabewert dieser Methode zeigt dem SDK an, ob die App den erforderlichen Neustart behandeln muss:   

 - Wenn „TRUE“ zurückgegeben wird, muss die App den Neustart behandeln.   

 - Wenn „FALSE“ zurückgegeben wird, startet das SDK die App neu, nachdem die Methode zurückkehrt. Das SDK zeigt sofort im Anschluss ein Dialogfeld an, dass den Benutzer informiert, dass er die App neu starten muss.

## <a name="customize-your-apps-behavior"></a>Anpassen des Verhaltens Ihrer App

Das Intune App SDK verfügt über mehrere APIs, die Sie aufrufen können, um Informationen zu bereitgestellten App-Schutzrichtlinien von Intune abzurufen. Diese Daten können Sie zum Anpassen des Verhaltens Ihrer App verwenden. Die meisten Einstellungen für App-Schutzrichtlinien werden automatisch vom SDK und nicht von der App erzwungen. Die einzige Einstellung, die die App implementieren sollte, ist das Steuerelement „Speichern unter“.

### <a name="get-app-protection-policy"></a>Abrufen einer App-Schutzrichtlinie

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
Die Klasse „IntuneMAMPolicyManager“ macht an die App bereitgestellte App-Schutzrichtlinien von Intune verfügbar. Im Besonderen macht sie APIs verfügbar, die zum [Aktivieren mehrerer Identitäten](#-enable-multi-identity-optional) dienen.

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
Die Klasse „IntuneMAMPolicy“ macht an die App bereitgestellte App-Schutzrichtlinien von Intune verfügbar. Die meisten der von dieser Klasse verfügbar gemachten Richtlinieneinstellungen werden vom SDK erzwungen; allerdings können Sie das Verhalten Ihrer App jederzeit anpassen, je nachdem, wie Richtlinieneinstellungen erzwungen werden.

Diese Klasse macht einige APIs verfügbar, die für die Implementierung von „Speichern unter“-Steuerelementen benötigt werden, wie im nächsten Abschnitt beschrieben.

### <a name="implement-save-as-controls"></a>Implementieren von „Speichern unter“-Steuerelementen

In Intune können IT-Administratoren bestimmen, an welchen Speicherorten verwaltete Apps Daten speichern können. Apps können dass Intune App SDK mithilfe der API **isSaveToAllowedForLocation** nach möglichen Speicherorten befragen; diese API ist unter **IntuneMAMPolicy.h** definiert.

Bevor Apps verwaltete Daten in einem Cloud-Speicher oder einem lokalen Speicher speichern können, müssen sie die API **isSaveToAllowedForLocation** überprüfen, um zu erfahren, ob der IT-Administrator diesen Ort zum Speichern freigegeben hat.

Wenn Apps die API **isSaveToAllowedForLocation** verwenden, müssen sie den UPN des Speicherorts übergeben, falls dieser verfügbar ist.

#### <a name="supported-save-locations"></a>Unterstützte Speicherorte

Die API **isSaveToAllowedForLocation** stellt Konstanten bereit, mit denen überprüft werden kann, ob der IT-Administrator folgende Speicherorte, die in IntuneMAMPolicy.h definiert sind, zum Speichern freigegeben hat:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Apps verwenden am besten die Konstanten in der API **isSaveToAllowedForLocation**, um zu überprüfen, ob Daten an einem als „verwaltet“ (z.B. OneDrive for Business) oder als „persönlich“ angesehenen Speicherort gespeichert werden können. Zusätzlich sollte die API verwendet werden, wenn die App nicht überprüfen kann, ob ein Speicherort „verwaltet“ oder „persönlich“ ist.

Als „persönlich“ angesehene Speicherorte werden von der `IntuneMAMSaveLocationOther`-Konstante dargestellt.

Die `IntuneMAMSaveLocationLocalDrive`-Konstante sollte verwendet werden, wenn die App Daten an einem Speicherort auf dem lokalen Gerät speichert.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurieren der Einstellungen für das Intune App SDK

Zum Konfigurieren des Intune App SDK können Sie das Wörterbuch **IntuneMAMSettings** verwenden, das sich in der info.plist-Datei der Anwendung befindet. Wenn sich das Wörterbuch „IntuneMAMSettings“ nicht in der info.plist-Datei befindet, erstellen Sie ein Wörterbuch mit dem Namen „IntuneMAMSettings“ in der info.plist-Datei Ihrer App.

Sie können im Wörterbuch „IntuneMAMSettings“ Schlüssel-/Wertzeilen von Konfigurationseinstellungen hinzufügen, um das SDK zu konfigurieren. In der unten stehenden Tabelle werden alle unterstützten Einstellungen aufgelistet.

Einige dieser Einstellungen wurden möglicherweise schon in vorherigen Abschnitten erörtert, und einige gelten nicht für alle Anwendungen.

Einstellung  | Typ  | Definition | Erforderlich?
--       |  --   |   --       |  --
ADALClientId  | String  | Die Azure AD-Client-ID der App | Erforderlich, wenn die App ADAL verwendet |
ADALAuthority | String | Die verwendete Azure AD-Autorität der App. Bei konfigurierten AAD-Konten sollten Sie Ihre eigene Umgebung verwenden. | Erforderlich, wenn die App ADAL verwendet. Wenn dieser Wert nicht vorhanden ist, wird der Intune-Standardwert verwendet.|
ADALRedirectUri  | String  | Der Azure AD-Umleitungs-URI der App | ADALRedirectUri oder ADALRedirectScheme ist erforderlich, wenn die App ADAL verwendet.  |
ADALRedirectScheme  | String  | Das Azure AD-Umleitungsschema der App. Dieses kann anstelle von ADALRedirectUri verwendet werden, wenn der Umleitungs-URI der App im `scheme://bundle_id`-Format ist. | ADALRedirectUri oder ADALRedirectScheme ist erforderlich, wenn die App ADAL verwendet. |
ADALLogOverrideDisabled | Boolesch  | Gibt an, ob das SDK alle ADAL-Protokolle (einschließlich ADAL-Aufrufe von der App, sofern zutreffend) in die eigene Protokolldatei einschließt. Standardwert ist "NO". Legen Sie den Wert auf „YES“ fest, wenn die App einen eigenen ADAL-Protokollrückruf festlegt. | (Optional) |
ADALCacheKeychainGroupOverride | String  | Gibt die anstatt „com.microsoft.adalcache“ für den ADAL-Cache zu verwendende Schlüsselbundgruppe an. Beachten Sie, dass das Präfix der App-ID fehlt. Dieses wird der gegebenen Zeichenfolge zur Laufzeit vorangestellt. | (Optional) |
AppGroupIdentifiers | Zeichenfolgenarray  | Ein Array mit App-Gruppen aus dem Berechtigungsabschnitt "com.apple.security.application-groups" der App. | Erforderlich, wenn die App Anwendungsgruppen verwendet. |
ContainingAppBundleId | String | Gibt die Paket-ID der Anwendung an, die die Erweiterung enthält | Erforderlich für iOS-Erweiterungen. |
DebugSettingsEnabled| Boolesch | Wenn dieser Wert auf „YES“ festgelegt ist, können Testrichtlinien innerhalb des Pakets „Einstellungen“ übernommen werden. Apps sollten *nicht* ausgeliefert werden, wenn diese Einstellung aktiviert ist. | (Optional) |
MainNibFile<br>MainNibFile~ipad  | String  | Diese Einstellung sollte den Namen der Haupt-NIB-Datei der Anwendung haben.  | Erforderlich, wenn in der info.plist-Datei der Anwendung „MainNibFile“ definiert ist |
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | Diese Einstellung sollte den Namen der Haupt-Storyboard-Datei der Anwendung haben. | Erforderlich, wenn in der info.plist-Datei der Anwendung „UIMainStoryboardFile“ definiert ist |
MAMPolicyRequired| Boolesch| Gibt an, ob der Start der App blockiert wird, wenn die App über keine App-Schutzrichtlinie von Intune verfügt. Standardwert ist "NO". <br><br> Hinweis: Apps können nicht im App Store eingereicht werden, wenn „MAMPolicyRequired“ auf „YES“ festgelegt ist. | (Optional) |
MAMPolicyWarnAbsent | Boolesch| Gibt an, ob der Benutzer beim Starten der App gewarnt wird, wenn die App über keine App-Schutzrichtlinie von Intune verfügt. Beachten Sie, dass Apps nicht im App Store eingereicht werden können, wenn diese Einstellung auf „YES“ festgelegt ist. | (Optional) |
MultiIdentity | Boolesch| Gibt an, ob die App mit mehreren Identitäten kompatibel ist | (Optional) |
SplashIconFile <br>SplashIconFile~ipad | String  | Gibt die Intune Splash Icon-Datei (Start) an | (Optional) |
SplashDuration | Zahl | Mindestdauer in Sekunden, für die der Intune-Startbildschirm beim Anwendungsstart angezeigt wird Standardwert ist 1,5. | (Optional) |
BackgroundColor| String| Gibt die Hintergrundfarbe für den Start- und PIN-Bildschirm an. Nimmt eine hexadezimale RGB-Zeichenfolge der Form #XXXXXX an, wobei X zwischen 0 und 9 oder A und F liegen kann. Das Rautezeichen kann weggelassen werden.   | (Optional) Die Standardfarbe ist hellgrün. |
ForegroundColor| String| Gibt die Vordergrundfarbe für den Start- und PIN-Bildschirm an wie etwa die Textfarbe. Nimmt eine hexadezimale RGB-Zeichenfolge der Form #XXXXXX an, wobei X zwischen 0 und 9 oder A und F liegen kann. Das Rautezeichen kann weggelassen werden.  | (Optional) Die Standardfarbe ist schwarz. |
AccentColor | String| Gibt die Akzentfarbe des PIN-Bildschirms an, wie etwa die Textfarbe der Schaltflächen und die Markierungsfarbe der Felder. Nimmt eine hexadezimale RGB-Zeichenfolge der Form #XXXXXX an, wobei X zwischen 0 und 9 oder A und F liegen kann. Das Rautezeichen kann weggelassen werden.| (Optional) Die Standardfarbe ist das Blau des Betriebssystems. |
MAMTelemetryDisabled| Boolesch| Gibt an, ob das SDK keine Telemetriedaten an sein Back-End sendet| (Optional) |

> [!NOTE]
> Wenn Ihre App im App Store veröffentlicht wird, muss `MAMPolicyRequired` gemäß den Vorgaben für den App Store auf „NO“ festgelegt sein.

## <a name="telemetry"></a>Telemetrie

Das Intune App SDK für iOS protokolliert standardmäßig Telemetriedaten zu den folgenden Verwendungsereignissen. Diese Daten werden an Microsoft Intune gesendet.

* **App-Start**: damit Microsoft Intune die Verwendung von für MAM aktivierten Apps nach Verwaltungstyp erkennen kann (MAM mit MDM, MAM ohne MDM-Registrierung usw.)

* **Registrierungsaufrufe**: damit Microsoft Intune die Erfolgsrate und andere Leistungsmetriken des von Clientseite initiierten Registrierungsaufrufs erkennen kann

> [!NOTE]
> Wenn von Ihrer mobilen Anwendung keine Intune App SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, müssen Sie die Intune App SDK-Telemetrieerfassung deaktivieren. Legen Sie die `MAMTelemetryDisabled`-Eigenschaft im Wörterbuch „IntuneMAMSettings“ auf „YES“ fest.

## <a name="enable-multi-identity-optional"></a>Aktivieren von Multi-Identity (optional)

Das SDK wendet eine Richtlinie standardmäßig auf die gesamte App an. Multi-Identity ist eine MAM-Funktion, die Sie, wenn aktiviert, verwenden können, um eine Richtlinie pro Identität anzuwenden. Dazu ist eine höhere App-Beteiligung als bei anderen MAM-Funktionen erforderlich.

Die App muss das App SDK darüber informieren, wann die aktive Identität geändert wird. Das SDK benachrichtigt die App auch, wenn eine Änderung der Identität erforderlich ist. Aktuell wird nur eine verwaltete Identität unterstützt. Nachdem der Benutzer das Gerät oder die App registriert hat, verwendet das SDK die Identität und behandelt sie als primäre verwaltete Identität. Alle anderen Benutzer in der App werden als nicht verwaltet mit uneingeschränkten Richtlinieneinstellungen behandelt.

Beachten Sie, dass eine Identität einfach nur als Zeichenfolge definiert ist. Identitäten beachten Groß- und Kleinschreibung. Identitätsanfragen an das SDK geben möglicherweise nicht die gleiche Schreibweise zurück, die beim Festlegen der Identität verwendet wurde.

### <a name="identity-overview"></a>Überblick: Identität

Eine Identität ist ganz einfach der Benutzername eines Kontos (z.B. user@contoso.com). Entwickler können die Identität der App auf folgenden Ebenen festlegen:

* **Prozessidentität**: Legt die Identität für alle Prozesse fest und wird überwiegend für Apps mit einer Identität verwendet. Diese Identität wirkt sich auf alle Aufgaben, Dateien und Benutzeroberflächen aus.

* **Benutzeroberflächenidentität**: Bestimmt, welche Richtlinien auf Aufgaben der Benutzeroberfläche im Hauptthread angewendet werden, wie z.B. Ausschneiden/Kopieren/Einfügen, PIN, die Authentifizierung und die Datenfreigabe. Die Benutzeroberflächenidentität wirkt sich nicht auf Dateiaufgaben wie die Verschlüsselung oder Sicherung aus.

* **Threadidentität**: Wirkt sich darauf aus, welche Richtlinien auf den aktuellen Thread angewendet werden. Diese Identität wirkt sich auf alle Aufgaben, Dateien und Benutzeroberflächen aus.

Die App ist dafür zuständig, die Identitäten entsprechend festzulegen, unabhängig davon, ob der Benutzer verwaltet ist.

Jeder Thread verfügt immer über eine gültige Identität für Aufgaben von Benutzeroberfläche und Dateien. Dies ist die Identität, die verwendet wird, um zu prüfen, welche Richtlinien gegebenenfalls angewendet werden sollen. Wenn die Identität „No Identity“ (keine Identität) ist, oder der Benutzer nicht verwaltet ist, werden keine Richtlinien angewendet. Die unten stehenden Diagramme veranschaulichen, wie gültige Identitäten bestimmt werden.

  ![Intune App SDK für iOS: verknüpfte Frameworks und Bibliotheken](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>Threadwarteschlangen

Apps senden oft asynchrone und synchrone Aufgaben an Threadwarteschlangen. Das SDK fängt Aufrufe von Grand Central Dispatch (GCD) ab und verknüpft die aktuelle Threadidentität mit den gesendeten Aufgaben. Wenn die Aufgaben abgeschlossen sind, ändert das SDK die Threadidentität vorübergehend in eine mit der Aufgabe verknüpfte Identität, schließt die Aufgaben ab, und stellt anschließend die ursprüngliche Threadidentität wieder her.


Weil `NSOperationQueue` auf GCD aufbaut, kann `NSOperations` auf der Threadidentität ausgeführt werden, wenn die Aufgaben `NSOperationQueue` hinzugefügt werden. `NSOperations` oder direkt mit GCD gesendete Funktionen können auch die aktuelle Threadidentität ändern, während sie ausgeführt werden. Diese Identität überschreibt die vom sendenden Thread geerbte Identität.

### <a name="file-owner"></a>Dateibesitzer

Das SDK verfolgt die Identität von Besitzern von lokalen Dateien nach und wendet Richtlinien entsprechend an. Ein Dateibesitzer wird festgelegt, wenn eine Datei erstellt wird, oder wenn eine Datei im Modus „Abschneiden“ geöffnet wird. Der Besitzer wird auf die gültige Dateiaufgabenidentität des Threads festgelegt, der die Aufgabe ausführt.

Alternativ können Apps die Dateibesitzeridentität explizit mit `IntuneMAMFilePolicyManager` festlegen. Mit `IntuneMAMFilePolicyManager` können Apps den Dateibesitzer abrufen und die Benutzeroberflächenidentität festlegen, bevor der Dateiinhalt angezeigt wird.

### <a name="shared-data"></a>Freigegebene Daten

Wenn die App Dateien erstellt, die sowohl Daten von verwalteten als auch von nicht verwalteten Benutzern enthalten, ist die App dafür zuständig, die Daten des verwalteten Benutzers zu verschlüsseln. Sie können Daten mit den APIs `protect` und `unprotect` in `IntuneMAMDataProtectionManager` verschlüsseln.

Die `protect`-Methode kann sowohl eine Identität von einem verwalteten als auch von einem nicht verwalteten Benutzer annehmen. Wenn der Benutzer verwaltet ist, werden die Daten verschlüsselt. Wenn der Benutzer nicht verwaltet ist, wird den Daten ein Header hinzugefügt, der die Identität verschlüsselt; die Daten werden allerdings nicht verschlüsselt. Mit der `protectionInfo`-Methode können Sie den Datenbesitzer abrufen.

### <a name="share-extensions"></a>Teilen-Erweiterung

Wenn die App über eine Teilen-Erweiterung verfügt, kann der Besitzer des freigegebenen Elements durch die `protectionInfoForItemProvider`-Methode in `IntuneMAMDataProtectionManager` abgerufen werden. Wenn es sich bei dem freigegebenen Element um eine Datei handelt, legt das SDK den Dateibesitzer fest. Wenn es sich bei dem freigegebenen Element um Daten handelt, legt die App den Dateibesitzer fest, wenn die Daten in eine Datei übernommen werden, und ruft die API `setUIPolicyIdentity` auf, bevor die Daten auf der Benutzeroberfläche angezeigt werden.

### <a name="turning-on-multi-identity"></a>Aktivieren von Multi-Identity

Standardmäßig wird bei Apps davon ausgegangen, dass sie eine Identität besitzen. Das SDK legt die Prozessidentität auf den registrierten Benutzer fest. Fügen Sie eine boolesche Einstellung mit dem Namen `MultiIdentity` und dem Wert „YES“ in das Wörterbuch „IntuneMAMSettings“ in der info.plist-Datei der App hinzu, um die Unterstützung für mehrere Identitäten zu aktivieren.

> [!NOTE]
> Wenn Multi-Identity aktiviert ist, werden die Prozess-, Benutzeroberflächen- und Threadidentitäten auf „nil“ festgelegt. Die App ist dafür zuständig, diese entsprechend festzulegen.

### <a name="switching-identities"></a>Wechseln von Identitäten

* **Von der App initiierter Wechsel der Identität**

    Beim Start werden Apps mit mehreren Identitäten als Apps behandelt, die unter einem unbekannten, nicht verwalteten Konto ausgeführt werden. Die Benutzeroberfläche für einen bedingten Start wird nicht ausgeführt, und es werden keine Richtlinien auf die App angewendet. Die App ist dafür zuständig, das SDK zu informieren, wenn die Identität gewechselt werden sollte. Dies geschieht für gewöhnlich immer dann, wenn die App kurz davor ist, Daten für ein spezifisches Benutzerkonto anzuzeigen.

    Ein derartiger Fall tritt z.B. ein, wenn ein Benutzer versucht, ein Dokument, ein Postfach oder eine Registerkarte auf einem Notebook zu öffnen. Die App muss das SDK informieren, bevor diese Datei, dieses Postfach oder diese Registerkarte tatsächlich geöffnet wird. Dies geschieht über die `setUIPolicyIdentity`-API in `IntuneMAMPolicyManager`. Diese API sollte aufgerufen werden, unabhängig davon, ob der Benutzer verwaltet ist. Wenn der Benutzer verwaltet ist, führt das SDK Prüfungen zum bedingten Start durch, wie etwa die Erkennung von Jailbreaks, PIN und die Authentifizierung.

    Das Ergebnis des Identitätswechsels wird anhand eines Fertigstellungshandlers asynchron an die App zurückgegeben. Die App sollte das Öffnen des Dokuments, des Postfachs oder der Registerkarte solange aussetzen, bis ein Erfolgsergebniscode zurückgegeben wird. Wenn das Wechseln der Identität fehlgeschlagen ist, sollte die App die Aufgabe abbrechen.

* **Vom SDK initiierter Wechsel der Identität**:

    Manchmal muss das SDK die App dazu auffordern, zu einer spezifischen Identität zu wechseln. Apps mit mehreren Identitäten müssen die `identitySwitchRequired`-Methode in `IntuneMAMPolicyDelegate` implementieren, um dieser Aufforderung zu folgen.

    Wenn diese Methode aufgerufen wird, wenn die App der Aufforderung, zu einer spezifischen Identität zu wechseln, folgen kann, sollte sie `IntuneMAMAddIdentityResultSuccess` an den Fertigstellungshandler übergeben. Wenn Sie den Identitätswechsel nicht durchführen kann, sollte die App `IntuneMAMAddIdentityResultFailed` an den Fertigstellungshandler übergeben.

    Als Reaktion auf diesen Aufruf muss die App nicht `setUIPolicyIdentity` aufrufen. Wenn das SDK es erfordert, dass die App zu einem nicht verwalteten Benutzerkonto wechselt, wird die leere Zeichenfolge an den `identitySwitchRequired`-Aufruf übergeben.

* **Selektives Zurücksetzen**:

    Wenn die App selektiv zurückgesetzt wird, ruft das SDK die `wipeDataForAccount`-Methode in `IntuneMAMPolicyDelegate` auf. Die App ist dafür zuständig, das angegebene Benutzerkonto und alle damit verknüpften Daten zu entfernen. Das SDK kann alle Dateien, die der Benutzer besitzt, entfernen; dies geschieht, wenn die App nach dem `wipeDataForAccount`-Aufruf „FALSE“ zurückgibt.

    Beachten Sie, dass diese Methode durch einen Hintergrundthread aufgerufen wird. Die App sollte keinen Wert zurückgeben, bis nicht alle Daten des Benutzers entfernt wurden (ausgenommen sind Dateien, wenn die App „FALSE“ zurückgibt).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Testen von Einstellungen für App-Schutzrichtlinien in Xcode

Bevor Sie Ihre sich in der Produktion befindliche Intune-fähige App manuell testen, können Sie die Datei „settings.bundle“ in Xcode verwenden. Damit können Sie App-Schutzrichtlinien für das Testen festlegen, ohne mit Intune verbunden zu sein.

### <a name="enable-policy-testing"></a>Aktivieren des Testens von Richtlinien

Führen Sie die unten stehenden Schritte aus, um das Testen von Richtlinien in Xcode zu aktivieren:

1. Achten Sie darauf, dass Sie sich in einem Debugbuild befinden. Fügen Sie die Datei „settings.bundle“ hinzu, indem Sie mit der rechten Maustaste auf den Ordner oberster Ebene in Ihrem Projekt klicken. Wählen Sie im Menü **Add** > **New File** (Hinzufügen > Neue Datei). Wählen Sie unter **Resources** (Ressourcen) die Vorlage **Settings Bundle** (Einstellungspaket) aus.

2.  Kopieren Sie folgenden Block in die Datei „settings.bundle/**root.plist**“ für den Debugbuild:
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. Fügen Sie im Wörterbuch **IntuneMAMSettings** in der info.plist-Datei der App einen booleschen Wert mit dem Namen „DebugSettingsEnabled“ hinzu. Legen Sie den Wert von „DebugSettingsEnabled“ auf „YES“ fest.



### <a name="app-protection-policy-settings"></a>Einstellungen für App-Schutzrichtlinien

In der unten stehenden Tabelle werden die Einstellungen für App-Schutzrichtlinien beschrieben, die Sie mit „MAMDebugSettings.plist“ testen können. Fügen Sie eine Eigenschaft in die Datei „MAMDebugSettings.plist“ ein, um diese zu aktivieren.

| Name der Richtlinieneinstellung | Beschreibung | Mögliche Werte |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | Der Zeitraum (in Minuten), den die App offline sein kann, bevor Intune den Start oder das Fortsetzen der App blockiert, wenn die Authentifizierung aktiviert ist. | Jede ganze Zahl größer als 0 |
|    AccessRecheckOnlineTimeout | Der Zeitraum (in Minuten), für den die App ausgeführt werden kann, bevor der Benutzer aufgefordert wird, einen PIN oder eine Authentifizierung beim Start oder beim Fortsetzen einzugeben (wenn die Authentifizierung oder der PIN für den Zugriff aktiviert ist). | Jede ganze Zahl größer als 0 |
| AppSharingFromLevel | Gibt an, von welchen Apps diese App Daten annehmen kann. | 0 = |
## <a name="ios-best-practices"></a>Empfohlene Methoden für iOS

Im Folgenden finden Sie einige empfohlene und bewährte Methoden für die Entwicklung für iOS:

* Beim iOS-Dateisystem wird Groß-/Kleinschreibung berücksichtigt. Achten Sie darauf, dass die Groß-/Kleinschreibung für Dateinamen wie `libIntuneMAM.a` oder `IntuneMAMResources.bundle` korrekt ist.

* Wenn Xcode Probleme beim Suchen nach `libIntuneMAM.a` hat, können Sie das Problem beheben, indem Sie den Pfad zu dieser Bibliothek den Linker-Suchpfaden hinzufügen.

## <a name="faqs"></a>Häufig gestellte Fragen


**Sind alle APIs über natives Swift oder über gleichzeitiges Objective-C und Swift zu erreichen?**

Die APIs des Intune App SDK sind nur für Objective-C geeignet und unterstützen **natives** Swift nicht. Die Interoperabilität zwischen Swift und Objective-C ist erforderlich.


**Müssen alle Benutzer meiner App in APP-WE registriert sein?**

Nein. Es müssen nur Geschäfts- und Schulkonten im Intune App SDK registriert werden. Apps sind dafür zuständig, zu bestimmen, ob ein Konto in einem Geschäfts- oder Schulkontext verwendet wird.   

**Was ist mit Benutzern, die sich bereits in der App registriert haben? Müssen sie sich registrieren?**

Die App ist dafür zuständig, Benutzer zu registrieren, nachdem diese erfolgreich authentifiziert wurden. Außerdem ist die App dafür zuständig, alle vorhandenen Konten zu registrieren, die möglicherweise schon existiert haben, bevor in der App MDM-loses MAM möglich war.   

Dies kann die App mit der `registeredAccounts:`-Methode machen. Diese Methode gibt ein „NSDictionary“-Objekt zurück, das alle im Intune MAM-Dienst registrierten Konten enthält. Wenn sich in der App vorhandene Konten nicht auf der Liste befinden, sollte die App diese Konten über `registerAndEnrollAccount:` registrieren und anmelden.

**Wie oft kommt es vor, dass das SDK Registrierungen erneut vornimmt?**

Das SDK versucht automatisch im 24-Stunden-Abstand alle fehlgeschlagenen Registrierungen erneut vorzunehmen. Dies macht das SDK, um sicherzustellen, dass der Benutzer erfolgreich registriert wird und Richtlinien erhält, auch wenn dessen Organisation MAM erst dann aktiviert, nachdem der Benutzer sich in der App bereits angemeldet hatte.

Das SDK versucht die erneute Registrierung erst dann nicht mehr, wenn es erkennt, dass der Benutzer erfolgreich in der App angemeldet wurde. Dies liegt daran, dass nur ein Benutzer eine App zu einem Zeitpunkt registrieren kann. Wenn die Registrierung des Benutzers aufgehoben wird, werden die Versuche im 24-Stunden-Abstand wieder aufgenommen.

**Warum muss die Registrierung des Benutzers aufgehoben werden?**

Das SDK führt folgende Aktionen regelmäßig im Hintergrund aus:

 - Wenn die App noch nicht registriert wurde, versucht es, alle registrierten Konten in einem Abstand von 24 Stunden zu registrieren.
 - Wenn die App bereits registriert wurde, prüft das SDK in einem Abstand von acht Stunden auf Aktualisierung der App-Schutzrichtlinien.

Bei der Aufhebung der Registrierung eines Benutzers wird das SDK darüber informiert, dass der Benutzer die App nicht mehr verwendet, und dass alle regelmäßigen Aktionen für dieses Benutzerkonto beendet werden können. Falls notwendig werden dadurch eine Aufhebung der Registrierung der App und das selektive Zurücksetzen ausgelöst.

**Soll das doWipe-Flag in der deregister-Methode auf „YES“ festgelegt werden?**

Diese Methode sollte aufgerufen werden, bevor der Benutzer aus der App abgemeldet wird.  Wenn die Benutzerdaten im Rahmen der Abmeldung aus der App gelöscht werden, kann `doWipe` auf „FALSE“ festgelegt werden. Wenn die App die Benutzerdaten nicht entfernt, sollte `doWipe` auf „TRUE“ festgelegt werden, damit das SDK die Daten löschen kann.

**Gibt es andere Möglichkeiten zur Aufhebung der Registrierung von Apps?**

Ja, der IT-Administrator kann den Befehl für das selektive Zurücksetzen an die App senden. Dadurch wird die Registrierung des Benutzers aufgehoben und die Benutzerdaten werden gelöscht. Das SDK behandelt dieses Szenario automatisch und sendet eine Benachrichtigung über die unenroll-Delegatmethode.



## <a name="submit-your-app-to-the-app-store"></a>Einreichen Ihrer App im App Store

Sowohl die statische Bibliothek als auch die Frameworkbuilds des Intune App SDK sind universelle Binärdateien. Dies bedeutet, dass sie über Code für alle Geräte- und Simulatorstrukturen verfügen. Im App Store eingereichte Apps mit Simulatorcode werden von Apple abgelehnt. Wenn mit der statischen Bibliothek für Builds nur für Geräte kompiliert wird, entfernt der Linker automatisch den Simulatorcode. Führen Sie die unten stehenden Schritte aus, um sicherzustellen, dass der gesamte Simulatorcode entfernt wird, bevor Sie die App in den App Store hochladen.

1. Achten Sie darauf, dass sich `IntuneMAM.framework` auf Ihrem Desktop befindet.

2. Führen Sie diese Befehle aus:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    Der erste Befehl entfernt die Simulatorstrukturen aus der DYLIB-Datei des Frameworks. Der zweite Befehl kopiert die DYLIB-Datei, die nur für Geräte gedacht ist, zurück in das Frameworkverzeichnis.

