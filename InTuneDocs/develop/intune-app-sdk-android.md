---
title: "Entwicklerhandbuch zum Microsoft Intune App SDK für Android | Microsoft Docs"
description: "Das Microsoft Intune App SDK für Android ermöglicht die Integration von Intune Mobile App Management (MAM) in Ihre Android-App."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: ddfd4e8a23f1a7e20230c188ac8203a11e48c4a6


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Entwicklerhandbuch zum Microsoft Intune App SDK für Android

> [!NOTE]
> Lesen Sie am besten zuerst die [Übersicht über das Intune App SDK](intune-app-sdk.md). Dort finden Sie Informationen zu den aktuellen Features des SDK sowie zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.

Das Microsoft Intune App SDK für Android ermöglicht die Integration von Intune Mobile App Management (MAM) in Ihre Android-App. MAM-fähige Anwendungen sind in das Intune App SDK integrierte Anwendungen. Sie ermöglichen IT-Administratoren, Richtlinien für ihre mobile App bereitzustellen, wenn diese aktiv von Intune verwaltet wird.

## <a name="whats-in-the-sdk"></a>Inhalt des SDK

Das Intune App SDK für Android ist eine Android-Standardbibliothek ohne externe Abhängigkeiten. Das SDK besteht aus den folgenden Komponenten:  

* **Microsoft.Intune.MAM.SDK.jar**: Die Schnittstellen, die zum Aktivieren von MAM und Interoperabilität mit der Intune-Unternehmensportal-App erforderlich sind. In Apps muss sie als Referenz zu einer Android-Bibliothek angegeben werden.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android v4 verwenden. Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android v7 verwenden. Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen.

* **Ressourcenverzeichnis**: Die Ressourcen (etwa Zeichenfolgen), die das SDK benötigt.

* **Microsoft.Intune.MAM.SDK.aar**: Die SDK-Komponenten, mit Ausnahme der Support.V4- und der Support.V7-JAR-Datei. Diese Datei kann anstelle der einzelnen Komponenten verwendet werden, wenn das Buildsystem AAR-Dateien unterstützt.

* **AndroidManifest.xml**: Die zusätzlichen Einstiegspunkte und die Bibliotheksanforderungen.

* **THIRDPARTYNOTICES.TXT**: Ein Urheberrechtshinweis für Drittanbieter- und/oder OSS-Code, der in Ihrer App kompiliert wird.

## <a name="requirements"></a>Anforderungen

Das Intune App SDK ist ein kompiliertes Android-Projekt. Daher ist es größtenteils unabhängig von der Version von Android, die die App für ihre API-Mindest- bzw. -Zielversion verwendet. Das SDK unterstützt Android API 14 (Android 4.0 und höher) bis Android API 24.

Das Intune App SDK für Android ist darauf angewiesen, dass die [Unternehmensportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-App auf dem Gerät vorhanden ist, damit MAM-Richtlinien aktiviert werden können. Für MAM ohne Registrierung des Geräts muss der Benutzer das Gerät *nicht* mithilfe der Unternehmensportal-App registrieren.


## <a name="how-the-intune-app-sdk-works"></a>Funktionsweise des Intune App SDK

###<a name="entry-points"></a>Einstiegspunkte

Das Intune App SDK erfordert Änderungen am Quellcode einer App, damit Intune-App-Verwaltungsrichtlinien aktiviert werden können. Zu diesem Zweck werden die Android-Basisklassen durch äquivalente Intune-Basisklassen ersetzt, deren Namen das Präfix `MAM` haben. Die SDK-Klassen befinden sich zwischen der Android-Basisklasse und der App-eigenen abgeleiteten Version dieser Klasse. Wenn Sie beispielsweise eine Aktivität verwenden, erhalten Sie eine Vererbungshierarchie, die wie folgt aussieht: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Wenn `AppSpecificActivity` z. B. mit dem übergeordneten Element (z. B. durch Aufrufen von `super.onCreate()`) interagiert, ist `MAMActivity` die übergeordnete Klasse.

Typische Android-Apps verfügen über einen einzelnen Modus und können über ihr [Context](https://developer.android.com/reference/android/content/Context.html)-Objekt auf das gesamte System zugreifen. Andererseits verfügen Apps, in die das Intune App SDK integriert ist, über zwei Modi. Diese Apps greifen auch weiterhin über das `Context`-Objekt auf das System zu. Abhängig von der verwendeten Basis-`Activity` wird das `Context`-Objekt von Android bereitgestellt oder auf intelligente Weise zwischen einer eingeschränkten Ansicht des Systems und dem von Android bereitgestellten `Context` im Multiplexmodus gesendet.

Wenn ein Android-[Einstiegspunkt](https://developer.android.com/guide/components/fundamentals.html) durch sein MAM-Äquivalent überschrieben wurde, muss die MAM-Version des Lebenszyklus des Einstiegspunkts verwendet werden (mit Ausnahme der Klasse `MAMApplication`).

Wenn z. B. von `MAMActivity` abgeleitet wird, anstatt `onCreate` zu überschreiben und `super.onCreate` aufzurufen, muss `Activity` `onMAMCreate` überschreiben und `super.onMAMCreate` aufrufen. Auf diese Weise kann Intune den Start von `Activity` (unter anderem ) unter bestimmten Umständen einschränken.


###<a name="sdk-permissions"></a>SDK-Berechtigungen

Das Intune App SDK erfordert drei [Android-Systemberechtigungen](https://developer.android.com/guide/topics/security/permissions.html) für Apps, die es integrieren:

* `android.permission.GET_ACCOUNTS` (zur Laufzeit angefordert, wenn erforderlich)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Die Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) verlangt, dass diese Berechtigungen Brokerauthentifizierung ausführen. Wenn diese Berechtigungen der App nicht gewährt oder vom Benutzer widerrufen werden, werden Authentifizierungsflüsse deaktiviert, die den Broker (die Unternehmensportal-App) erfordern.


###<a name="company-portal-app"></a>Unternehmensportal-App

Warum ist die Unternehmensportal-App erforderlich? Wenn die Unternehmensportal-App auf dem Gerät installiert ist und eine Anwendungseinschränkungsrichtlinie für den Benutzer aus dem Intune-Dienst abgerufen hat, werden die SDK-Einstiegspunkte asynchron initialisiert. Initialisierung ist nur erforderlich, wenn Android den Prozess anfänglich erstellt. Während der Initialisierung wird eine Verbindung mit der Unternehmensportal-App hergestellt, und die Richtlinie wird von der App abgerufen.  

> [!NOTE]
> Wenn die Unternehmensportal-App nicht auf dem Gerät vorhanden ist, ändert sich das Verhalten der für Intune aktivierten App nicht. Vielmehr verhält sie sich wie eine normale App.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Integration mit dem Intune App SDK

Wie bereits kurz erwähnt, erfordert das SDK Änderungen am Quellcode der App, damit App-Verwaltungsrichtlinien aktiviert werden können. Führen Sie folgende Schritte aus, um MAM in Ihrer App zu aktivieren.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Ersetzen von Klassen, Methoden und Aktivitäten durch das MAM-Äquivalent (erforderlich)

Android-Basisklassen müssen durch ihre jeweiligen MAM-Äquivalente ersetzt werden. Suchen Sie dazu nach allen Instanzen der in der folgenden Tabelle aufgeführten Klassen, und ersetzen Sie sie durch das Intune App SDK-Äquivalent.

| Android-Basisklasse | Intune App SDK-Äquivalent |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (nur erforderlich, wenn der Binder nicht von einer AIDL-Schnittstelle (Android Interface Definition Language) generiert wird) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppbzw.t.v4.jar**:

| Android-Klasse: Intune MAM | Intune App SDK-Äquivalent |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Suppbzw.t.v7.jar**:

|Android-Klasse | Intune App SDK-Äquivalent |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Denken Sie daran: Wenn ein Android-[Einstiegspunkt](https://developer.android.com/guide/components/fundamentals.html) durch sein MAM-Äquivalent überschrieben wurde, muss die MAM-Version des Lebenszyklus des Einstiegspunkts verwendet werden (mit Ausnahme der Klasse `MAMApplication`).
>
>Wenn z. B. von `MAMActivity` abgeleitet wird, anstatt `onCreate` zu überschreiben und `super.onCreate` aufzurufen, muss `Activity` `onMAMCreate` überschreiben und `super.onMAMCreate` aufrufen. Auf diese Weise kann Intune den Start von `Activity` (unter anderem ) unter bestimmten Umständen einschränken.

#### <a name="pendingintent-classes-and-renamed-methods"></a>PendingIntent-Klassen und umbenannte Methoden

Nachdem Sie die Ableitung von einem der MAM-Einstiegspunkte vorgenommen haben, kann `Context` wie gewohnt gefahrlos verwendet werden, z. B. zum Starten von `Activity`-Klassen und Verwenden von `PackageManager`.  

`PendingIntent`-Klassen stellen eine Ausnahme von dieser Regel dar. Wenn Sie diese Klassen aufrufen, müssen Sie den Klassennamen ändern. Anstelle von `PendingIntent.get*` müssen Sie z. B. die `MAMPendingIntent.get*`-Methode verwenden. Anschließend können Sie den sich ergebenden `PendingIntent` wie gewohnt verwenden.

In einigen Fällen wurde eine in der Android-Klasse verfügbare Methode in der äquivalenten MAM-Klasse als abgeschlossen gekennzeichnet. In diesem Fall stellt die äquivalente MAM-Klasse eine Methode mit ähnlichem Namen (normalerweise mit dem Suffix `MAM`) bereit, die stattdessen überschrieben werden sollte. Beispiel: Anstelle von `ContentProvider.query`würden Sie `MAMContentProvider.queryMAM`. Der Java-Compiler sollte die abgeschlossenen Einschränkungen erzwingen, um zu verhindern, dass die ursprüngliche Methode anstelle des MAM-Äquivalents überschrieben wird.

###<a name="enable-features-that-require-app-participation"></a>Aktivieren von Funktionen, die App-Beteiligung erfordern

Einige Richtlinien kann das SDK nicht selbst implementieren. Die App kann ihr Verhalten zum Bereitstellen dieser Features mit mehreren APIs steuern, die Sie in der folgenden `AppPolicy`-Schnittstelle finden.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

### <a name="enable-it-control-over-app-saving-behavior"></a>Aktivieren der IT-Steuerung des App-Speicherverhaltens

Viele Apps implementieren Features, die dem Benutzer ermöglichen, Dateien lokal oder bei einem Cloudspeicherdienst zu speichern. Mit dem Intune App SDK können IT-Administratoren dafür sorgen, dass keine Datenpreisgabe erfolgt, indem sie Richtlinieneinschränkungen entsprechend den Anforderungen ihrer Organisation anwenden.  Eine der durch die IT steuerbaren Richtlinien betrifft das Speichern in einem „persönlichen“, nicht verwalteten Datenspeicher durch den Benutzer. Darunter fällt das Speichern an einem lokalen Speicherort, auf einer SD-Karte und bei Sicherungsdiensten von Drittanbietern.

Damit die Funktion aktiviert werden kann, ist App-Beteiligung erforderlich. Wenn Ihre App das direkte Speichern aus der App an einem persönlichen oder Cloudspeicherort ermöglicht, müssen Sie dieses Feature implementieren, damit IT-Administratoren steuern können, ob das Speichern an einem Speicherort zulässig ist.   

Die App kann den folgenden Aufruf ausführen, um festzustellen, ob die Richtlinie erzwungen wird. Durch diesen Aufruf kann die App ermitteln, ob die aktuelle Richtlinie des Intune-Administrators das Speichern in einem persönlichen Speicher zulässt. Die App kann dann die Richtlinie erzwingen, weil sie über den persönlichen Datenspeicher informiert ist, der dem Benutzer über die App zur Verfügung steht.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` gibt stets eine App-Richtlinie ungleich NULL zurück. Dies gilt selbst dann, wenn das Gerät oder die App keiner Intune-Verwaltungsrichtlinie unterliegt.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Die App erkennen lassen, ob eine PIN-Richtlinie erforderlich ist

Bei manchen Intune-App-Einschränkungen möchten Sie vielleicht, dass die App ihre Funktionen zum Teil deaktiviert, um Funktionen im Intune App SDK nicht zu duplizieren. Verfügt die App z.B. über eine eigene PIN-Benutzererfahrung, kann diese deaktiviert werden, wenn das SDK so eingerichtet ist, dass der Endbenutzer eine PIN eingeben muss.

Um festzustellen, ob eine Intune-PIN-Richtlinie so eingerichtet ist, dass die Eingabe einer App-PIN beim Start erforderlich ist, kann die App den folgenden Aufruf ausführen:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Registrieren für Benachrichtigungen vom SDK  

Das Intune App SDK erlaubt Ihrer App die Steuerung des Verhaltens bestimmter Richtlinien (z. B. zur selektiven Zurücksetzung), wenn sie vom IT-Administrator bereitgestellt werden. Wenn ein IT-Administrator eine solche Richtlinie bereitstellt, sendet der Intune-Dienst eine Benachrichtigung an das SDK.

Ihre App muss sich für Benachrichtigungen vom SDK registrieren, indem eine `MAMNotificationReceiver`-Klasse erstellt und diese bei `MAMNotificationReceiverRegistry` registriert wird. Zu diesem Zweck werden der Empfänger und der Typ der Benachrichtigung in `App.onCreate` angegeben, wie das folgende Beispiel veranschaulicht:

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

`MAMNotificationReceiver` empfängt lediglich Benachrichtigungen vom Intune-Dienst. Das SDK verarbeitet einige Benachrichtigungen direkt. Andere Benachrichtigungen erfordern die Teilnahme der App.

Eine App *muss* TRUE oder FALSE von einer Benachrichtigung zurückgeben. Sie muss immer TRUE zurückgeben, es sei denn, bei einer von ihr aufgrund der Benachrichtigung ausgeführten Aktion tritt ein Fehler auf. Dieser Fehler kann beim Intune-Dienst gemeldet werden. Ein Beispiel für ein zu berichtendes Szenario ist, wenn die Anwendung Benutzerdaten nicht zurücksetzt, nachdem der IT-Administrator eine Zurücksetzung initiiert hat.

Ein Blockieren in `MAMNotificationReceiver.onReceive` ist sicher, weil der zugehörige Rückruf nicht im Benutzeroberflächenthread ausgeführt wird.

Die folgende `MAMNotificationReceiver`-Schnittstelle ist im SDK definiert:

```
/**
 * The SDK is signaling that a WG event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

###<a name="types-of-notifications"></a>Arten von Benachrichtigungen

Die folgenden Benachrichtigungen werden an die App gesendet. Einige dieser Benachrichtigungen erfordern ggf. eine Teilnahme der App.

* **`WIPE_USER_DATA`**: Diese Benachrichtigung wird in einer `MAMUserNotification`-Klasse gesendet. Beim Empfang dieser Benachrichtigung sollte die App alle Daten im Zusammenhang mit der mit `MAMUserNotification` übergebenen „Unternehmensidentität“ löschen. Diese Benachrichtigung wird zurzeit bei der Aufhebung der Registrierung beim Intune-Dienst gesendet. Der primäre Name des Benutzers wird in der Regel während der Registrierung angegeben. Wenn Sie sich für diese Benachrichtigung registrieren, muss Ihre App sicherstellen, dass alle Benutzerdaten gelöscht wurden. Wenn Sie sich nicht für sie registrieren, führt die App das Standardverhalten für die selektive Zurücksetzung aus.

* **`WIPE_USER_AUXILIARY_DATA`**: Apps können sich für diese Benachrichtigung registrieren, wenn das Intune App SDK die standardmäßige selektive Zurücksetzung ausführen soll, bei der Zurücksetzung aber weitere Daten entfernt werden sollen.  

* **`REFRESH_POLICY`**: Diese Benachrichtigung wird in `MAMUserNotification` gesendet. Bei Empfang dieser Benachrichtigung muss jegliche zwischengespeicherte Intune-Richtlinie für ungültig erklärt und aktualisiert werden. Das SDK übernimmt in der Regel diese Aufgabe. Die App sollte diese Aufgabe jedoch übernehmen, wenn die Richtlinie permanent verwendet wird.



### <a name="protection-of-backup-data"></a>Schutz der Sicherungsdaten

Seit Android Marshmallow (API 23) bietet Android einer App zwei Möglichkeiten zum Sichern ihrer Daten. Jede Option ist für Ihre App verfügbar und erfordert andere Schritte, um sicherzustellen, dass Intune-Datenschutz ordnungsgemäß implementiert wird. Mehr über die Sicherungsmethoden erfahren Sie im [Android-API-Handbuch](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Automatische Sicherung für Apps

Android hat begonnen, [automatische vollständige Sicherungen](https://developer.android.com/guide/topics/data/autobackup.html) für Apps auf Android Marshmallow-Geräten unabhängig von der Ziel-API der App anzubieten. Wenn Sie `android:allowBackup` in der Datei „AndroidManifest.xml“ explizit auf FALSE festlegen, wird Ihre App niemals für Sicherungen von Android in die Warteschlange eingereiht, und „Unternehmensdaten“ verbleiben in der App. In diesem Fall ist keine weitere Aktion erforderlich.

Allerdings ist das `android:allowBackup`-Attribut standardmäßig auf TRUE festgelegt. Dies gilt auch dann, wenn `android:allowBackup` nicht in der Manifestdatei angegeben wird. Dies bedeutet, dass alle App-Daten automatisch im Google Drive-Konto des Benutzers gesichert werden – ein Standardverhalten, das ein *Datenverlustrisiko* darstellt. Das SDK erfordert die folgenden Änderungen, um sicherzustellen, dass Datenschutz angewendet wird. Es ist wichtig, die folgenden Richtlinien zu befolgen, um Kundendaten angemessen zu schützen, wenn Ihre App auf Android Marshmallow-Geräten ausgeführt werden soll.  

Wenn Sie keinen Sicherungs-Agent zum Sichern Ihrer App mit `MAMBackupAgent` oder `MAMBackupAgentHelper` geschrieben haben, müssen Sie bedenken und steuern, wie die automatische Sicherung Ihre App-Daten hochlädt. Mit Intune können Sie alle [Features für automatische Sicherung](https://developer.android.com/guide/topics/data/autobackup.html) nutzen, die in Android verfügbar sind, z. B. auch Möglichkeit zum Definieren von benutzerdefinierten Regeln in XML. Sie müssen aber die folgenden Schritte zum Sichern Ihrer Daten ausführen:

1. Verwenden Sie die Standardeinstellung `MAMBackupAgent`, um automatische vollständige Sicherungen zu ermöglichen, die mit Intune-Richtlinien kompatibel sind. Fügen Sie `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` in Ihr App-Manifest ein.

2. Wenn Sie festlegen, welche Art von vollständiger Sicherung Ihre App erhalten soll (ungefiltert, gefiltert oder keine), legen Sie das Attribut `android:fullBackupContent` auf TRUE, FALSE oder eine XML-Ressource in Ihrer App fest. Kopieren Sie den Inhalt, den Sie in `android:fullBackupContent` eingefügt haben, in ein Metadatentag mit dem Namen `com.microsoft.intune.mam.FullBackupContent`.

    Wenn Ihre App z. B. vollständige Sicherungen gemäß der in einer XML-Datei vorliegenden benutzerdefinierten Regeln ausführen soll, geben Sie wie folgt eine Ressource unter dem `com.microsoft.intune.mam.FullBackupContent`-Metadatentag in Ihr Manifest ein:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Schlüssel-Wert-Sicherung

Die Schlüssel-Wert-Sicherungsoption ist für alle APIs verfügbar. Sie verwendet `BackupAgentHelper` und `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` ist hinsichtlich nativer Android-Funktionalität und MAM-Integration viel einfacher zu implementieren als `BackupAgent`. Mit `BackupAgentHelper` können Sie ganze Dateien und freigegebene Einstellungen in `FileBackupHelper` bzw. `SharedPreferencesBackupHelper` registrieren. Diese werden dann `BackupAgentHelper` bei der Erstellung hinzugefügt.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent` ermöglicht explizitere Angaben zu den zu sichernden Daten. Diese Option bedeutet aber auch, dass das Sicherungsframework von Android nicht genutzt werden kann. Da Sie für die Implementierung verantwortlich sind, sind mehr Schritte erforderlich, um den ordnungsgemäßen Datenschutz von MAM sicherzustellen. Da die Arbeit größtenteils von Ihnen als Entwickler zu leisten ist, ist die MAM-Integration etwas komplizierter.

###### <a name="app-does-not-have-a-backup-agent"></a>App hat keinen Sicherungs-Agent

Dies sind die Entwickleroptionen, wenn `android:allowBackup =true` verwendet wird.

####### <a name="full-backup-according-to-a-configuration-file"></a>Vollständige Sicherung anhand einer Konfigurationsdatei

Geben Sie unter dem `com.microsoft.intune.mam.FullBackupContent` -Metadatentag in Ihrem Manifest eine Ressource an. Beispiel:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Fügen Sie folgendes Attribut im `<application>` -Tag hinzu: `android:fullBackupContent="@xml/my_scheme"`, wobei `my_scheme` eine XML-Ressource in Ihrer App ist.

####### <a name="full-backup-without-exclusions"></a>Vollständige Sicherung ohne Ausnahmen

Geben Sie ein Tag im Manifest an, z. B. `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`

Fügen Sie im `<application>`-Tag folgendes Attribut hinzu: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>App hat einen Sicherungs-Agent

Befolgen Sie die Empfehlungen weiter oben in diesem Handbuch für `BackupAgent` und `BackupAgentHelper`.

Verwenden Sie ggf. `MAMDefaultFullBackupAgent`, um eine einfache Sicherung für Android Marshmallow zu erzielen.

##### <a name="before-your-backup"></a>Vor der Sicherung

Überprüfen Sie vor dem Sichern, dass die zu sichernden Dateien oder Datenpuffer wirklich gesichert werden dürfen. Es ist eine `isBackupAllowed`-Funktion in `MAMFileProtectionManager` und `MAMDataProtectionManager` verfügbar, um dies zu überprüfen. Wenn die Sicherung der Datei oder des Datenpuffers nicht zulässig ist, sollten Sie von einer weiteren Verwendung in Ihrer Sicherung absehen.

Wenn während der Sicherung die Identitäten der in Schritt 1 überprüften Dateien gesichert werden sollen, müssen Sie `backupMAMFileIdentity(BackupDataOutput data, File … files)` mit den Dateien aufrufen, aus denen Sie Daten extrahieren möchten. Auf diese Weise werden automatisch neue Sicherungsentitäten für Sie erstellt und in `BackupDataOutput` geschrieben. Diese Entitäten werden bei der Wiederherstellung automatisch genutzt.

#### <a name="azure-directory-authentication-library-setup"></a>Einrichten von ADAL (Azure Directory Authentication Library)  

Das SDK verwendet ADAL für die Authentifizierung und bedingte Startszenarien. Diese Szenarien erfordern, dass Apps über eine gewisse Azure Active Directory-Konfiguration (Azure AD) verfügen. Die Konfigurationswerte werden dem SDK über `AndroidManifest` -Metadaten übermittelt.

Zum Konfigurieren der App und zum Aktivieren ordnungsgemäßer Authentifizierung fügen Sie dem App-Knoten in `AndroidManifest` Folgendes hinzu. Einige dieser Konfigurationen sind nur erforderlich, wenn Ihre App ADAL im Allgemeinen für die Authentifizierung verwendet. In diesem Fall benötigen Sie die spezifischen Werte, die Ihre App verwendet, um sich bei Azure AD zu registrieren. Auf diese Weise wird sichergestellt, dass der Benutzer nicht zwei Mal zur Authentifizierung aufgefordert wird, weil Azure AD zwei separate Registrierungswerte erkennt: einen Wert aus der App und einen Wert aus dem SDK.

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

Die GUIDs müssen nicht die voran- oder nachgestellte geschweifte Klammer aufweisen.

##### <a name="common-adal-configurations"></a>Häufig verwendete ADAL-Konfigurationen

Nachfolgend finden Sie häufig verwendete Konfigurationen für die zuvor erläuterten Werte.

###### <a name="app-does-not-integrate-adal"></a>App kann ADAL nicht integrieren

* „Authority“ muss auf die gewünschte Umgebung festgelegt werden, in der Azure AD-Konten konfiguriert wurden.

* "SkipBroker" muss auf "true" festgelegt werden.

###### <a name="app-integrates-adal"></a>App kann ADAL integrieren

* „Authority“ muss auf die gewünschte Umgebung festgelegt werden, in der Azure AD-Konten konfiguriert wurden.

* "ClientID" muss auf die Client-ID der App festgelegt werden.

* `NonBrokerRedirectURI` sollte auf einen gültigen Umleitungs-URI für die App festgelegt werden. Alternativ muss `urn:ietf:wg:oauth:2.0:oob` als ein gültiger Azure AD-Umleitungs-URI eingerichtet werden.

* „SkipBroker“ muss auf FALSE festgelegt werden (oder darf nicht vorhanden sein).

* Azure AD muss so konfiguriert sein, dass der Umleitungs-URI des Brokers akzeptiert wird.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>Die App kann ADAL integrieren, unterstützt aber nicht die AAD Authenticator-App

* „Authority“ muss auf die gewünschte Umgebung festgelegt werden, in der Azure AD-Konten konfiguriert wurden.

* "ClientID" muss auf die Client-ID der App festgelegt werden.

* `NonBrokerRedirectURI` muss auf einen gültigen Umleitungs-URI für die App festgelegt werden. Alternativ kann `urn:ietf:wg:oauth:2.0:oob` als ein gültiger Azure AD-Umleitungs-URI eingerichtet werden.

#### <a name="logging-in-the-sdk"></a>Protokollierung im SDK

Die Protokollierung erfolgt über das `java.util.logging` -Framework. Richten Sie zum Empfangen von Protokollen die globale Protokollierung ein, wie im [Technischen Handbuch zu Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Abhängig von der App ist `App.onCreate` normalerweise die beste Stelle, um die Protokollierung zu initiieren. Beachten Sie, dass Protokollmeldungen mit dem Klassennamen verschlüsselt werden, der ggf. verborgen ist.

###<a name="multi-identity"></a>Mehrere Identitäten

Standardmäßig wird vom Intune App SDK eine Richtlinie auf die gesamte App angewendet. Die Unterstützung für mehrere Identitäten ist ein MAM-Feature, das Sie aktivieren können, um eine Richtlinie auf der Ebene einzelner Identitäten anzuwenden. Dies erfordert eine deutlich stärkere Beteiligung der App als andere MAM-Features. Die App muss das App-SDK informieren, wenn sie die Änderung der aktiven Identität beabsichtigt. Das SDK muss die App außerdem benachrichtigen, wenn eine Änderung der Identität erforderlich ist.

Aktuell wird nur eine verwaltete Identität unterstützt. Nachdem der Benutzer das Gerät oder die App registriert hat, verwendet das SDK die dabei verwendete Identität und betrachtet sie als die primäre verwaltete Identität. Andere Benutzer der App werden als nicht verwaltet mit uneingeschränkten Richtlinieneinstellungen behandelt.

Beachten Sie, dass eine Identität einfach in Form einer Zeichenfolge definiert wird. Bei Identitäten werden Groß- und Kleinschreibung nicht unterschieden. Anforderungen einer Identität beim SDK werden möglicherweise nicht mit der gleichen Groß-/Kleinschreibung zurückgegeben, die ursprünglich beim Festlegen der Identität verwendet wurde.

####<a name="enabling-multi-identity"></a>Aktivieren mehrerer Identitäten

Standardmäßig werden alle Apps als Einzelidentitäts-Apps betrachtet. Eine App deklariert durch Einfügen der folgenden Metadaten in das Android-Manifest, dass sie mit mehreren Identitäten kompatibel ist.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Festlegen der Identität

Sie können die Identität der App auf den folgenden Ebenen festlegen:

1. Prozessebene

2. Kontextebene (allgemein `Activity`)

3. Threadebene

Eine auf Threadebene festgelegte Identität hat Vorrang vor einer auf `Context`-Ebene festgelegten Identität, die wiederum Vorrang vor einer auf Prozessebene festgelegten Identität besitzt. Eine für `Context` festgelegte Identität wird nur bei Bedarf verwendet. Datei-E/A-Vorgängen ist z. B. kein `Context` zugeordnet. Die folgenden Methoden für `MAMPolicyManager` können verwendet werden, um die Identität festzulegen bzw. die zuvor festgelegten Identitätswerte abzurufen.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Sie können die Identität der App auch durch Festlegung auf NULL löschen. Die leere Zeichenfolge kann als Identität verwendet werden, die niemals Einschränkungen unterliegt. Alle Methoden zum Festlegen der Identität geben über ``` MAMIdentitySwitchResult``` Ergebniswerte zurück. Vier Werte können zurückgegeben werden:

* **SUCCEEDED**: Die Identitätsänderung war erfolgreich.

* **NOT_ALLOWED**: Die Identitätsänderung ist unzulässig. Dies geschieht bei einem Versuch, zu einem anderen Unternehmensbenutzer zu wechseln, der zu dem gleichen Unternehmen wie der registrierte Benutzer gehört. Dies geschieht auch bei einem Versuch, die Benutzeroberflächenidentität (`Context`) festzulegen, wenn für den aktuellen Thread eine andere Identität festgelegt ist.

* **CANCELLED**: Der Benutzer hat die Identitätsänderung abgebrochen, in der Regel mithilfe der Schaltfläche „Zurück“ einer PIN-/Authentifizierungseingabeaufforderung.

* **FAILED**: Bei der Identitätsänderung ist aus unbekannten Gründen ein Fehler aufgetreten.

Bei Festlegung einer `Context`-Identität wird das Ergebnis asynchron gemeldet. Wenn `Context` eine `Activity`-Klasse ist, ist erst nach dem bedingten Start bekannt, ob die Identitätsänderung erfolgreich war. Ein bedingter Start erfordert ggf., dass der Benutzer eine PIN oder seine vollständigen Unternehmensanmeldeinformationen eingibt. Es wird vorausgesetzt, dass die App einen ```MAMSetUIIdentityCallback``` für den Empfang dieses Ergebnisses implementiert, obwohl es zulässig ist, NULL für diesen Parameter zu übergeben.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Sie können die Identität einer Aktivität auch direkt über eine Methode für `MAMActivity` festlegen, anstatt ```MAMPolicyManager.setUIPolicyIdentity``` aufzurufen. Hierzu können Sie folgende Methode verwenden:

 ```public final void switchMAMIdentity(final String newIdentity);```

Apps können auch eine Methode für `MAMActivity` überschreiben, um über das Ergebnis von Versuchen, die Identität dieser Aktivität zu ändern, benachrichtigt zu werden.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Das Wechseln der Identität kann das erneute Erstellen der Aktivität erfordern. In diesem Fall wird der ```onSwitchMAMIdentityComplete```-Rückruf an die neue Instanz der Activity übermittelt.


####<a name="implicit-identity-changes"></a>Implizite Identitätsänderungen

Zusätzlich zu der Möglichkeit der App, die Identität festzulegen, kann die Identität eines Threads oder Kontexts sich basierend auf dem Dateneingang von einer anderen MAM-aktivierten App ändern. Wenn eine Aktivität z. B. durch eine `Intent`-Klasse gestartet wird, die von einer anderen MAM-App gesendet wird, wird die Identität der Aktivität basierend auf der effektiven Identität in der anderen App zu dem Zeitpunkt festgelegt, zu dem die `Intent`-Klasse gesendet wurde.

Für Dienste wird die Identität des Threads ähnlich für die Dauer eines `onStart`- oder `onBind`-Aufrufs festgelegt. Aufrufe von `Binder`, die von `onBind` zurückgegeben werden, legen ebenfalls vorübergehend die Threadidentität fest. An einen ```ContentProvider``` gerichtete Aufrufe legen auf ähnliche Weise die Threadidentität für ihre Dauer fest.

Darüber hinaus kann Benutzerinteraktion mit einer Aktivität ggf. einen impliziten Identitätswechsel hervorrufen. Wenn ein Benutzer z.B. während ```Resume``` eine Autorisierungsanforderung abbricht, führt dies zu einem impliziten Wechsel zu einer leeren Identität.
Die App kann auf diese Änderungen aufmerksam gemacht werden und kann sie ggf. in einigen Fällen verbieten. ```MAMService``` und ```MAMContentProvider``` stellen die folgende Methode bereit, die Unterklassen überschreiben können:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
Im Fall von ```MAMActivity``` ist ein zusätzlicher Parameter in der Methode vorhanden:
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
Der ```AppIdentitySwitchReason```-Teil erfasst die Quelle des impliziten Wechsels. Er kann die Werte ```CREATE```, ```RESUME_CANCELLED``` und ```NEW_INTENT``` annehmen.  Die Ursache ```RESUME_CANCELLED``` wird verwendet, wenn das Fortsetzen einer Aktivität bewirkt, dass eine PIN-, Authentifizierungs- oder andere Kompatibilitätsbenutzeroberfläche angezeigt wird, und der Benutzer versucht, die Benutzeroberfläche abzubrechen (in der Regel mithilfe der Schaltfläche „Zurück“).
```AppIdentitySwitchResultCallback``` ist wie folgt:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult``` ist ```SUCCESS``` oder ```FAILURE```.

Die Methode ```onMAMIdentitySwitchRequired``` wird für alle impliziten Identitätsänderungen mit Ausnahme der Änderungen aufgerufen, die über eine von ```MAMService.onMAMBind``` zurückgegebene `Binder`-Klasse erfolgen. Die Standardimplementierung von ```onMAMIdentitySwitchRequired``` ruft sofort ```reportIdentitySwitchResult(FAILURE)``` auf, wenn die Ursache ```RESUME_CANCELLED``` ist. In allen anderen Fällen wird ```reportIdentitySwitchResult(SUCCESS)``` aufgerufen.

Die meisten Apps müssen einen Identitätswechsel nicht auf andere Weise blockieren oder verzögern. Sollte dies dennoch der Fall sein, berücksichtigen Sie die folgenden Aspekte:

* Wenn ein Identitätswechsel blockiert wird, ist das Ergebnis identisch mit dem Verbot des Dateneingangs durch die ```Receive```-Freigabeeinstellungen.

* Wenn ein Dienst im Hauptthread ausgeführt wird, *muss* ```reportIdentitySwitchResult``` synchron aufgerufen werden. Andernfalls reagiert der UI-Thread nicht mehr.

* Für die ```Activity```-Erstellung wird ```onMAMIdentitySwitchRequired``` vor ```onMAMCreate``` aufgerufen. Wenn die App eine Benutzeroberfläche anzeigen muss, um zu überprüfen, ob das Wechseln der Identität zugelassen wird, muss diese Benutzeroberfläche mit einer anderen Aktivität angezeigt werden.

* Wenn in ```Activity``` ein Wechsel zu der leeren Identität mit einer Ursache angefordert wird, die ```RESUME_CANCELLED``` entspricht, muss die App die fortgesetzte Aktivität ändern, um Daten anzuzeigen, die mit diesem Identitätswechsel konsistent sind. Wenn dies nicht möglich ist, sollte die App den Wechsel verweigern. Der Benutzer wird dann erneut zur Einhaltung der Richtlinie für die Fortsetzung der Identität aufgefordert (z. B. durch Anzeige des Bildschirms für die PIN-Eingabe).

> [!NOTE]
> Eine App mit mehreren Identitäten empfängt eingehende Daten immer von verwalteten und nicht verwalteten Apps. Es liegt in der Verantwortung der App, Daten von verwalteten Identitäten in einer verwalteten Weise zu behandeln. Wenn eine angeforderte Identität verwaltet wird ```(MAMPolicyManager.getIsIdentityManaged)```, die App das Konto aber nicht verwenden kann (weil z. B. Konten wie E-Mail-Konten zunächst in der App eingerichtet werden müssen), sollte der Identitätswechsel verweigert werden.

###<a name="file-protection"></a>Dateischutz

Jeder Datei wird zum Zeitpunkt der Erstellung basierend auf der Thread- und Prozessidentität eine Identität zugewiesen. Diese Identität wird für die Dateiverschlüsselung und die selektive Zurücksetzung verwendet. Nur Dateien, deren Identität eine Richtlinie aufweist, die Verschlüsselung erfordert, werden verschlüsselt. Die standardmäßige selektive Zurücksetzung des SDK setzt nur Dateien zurück, denen die Identität zugeordnet ist, für die eine Zurücksetzung angefordert wurde. Die App kann die Identität einer Datei mithilfe von ```MAMFileProtectionManager``` abfragen oder ändern.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     *
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> Die Markierung der Dateiidentität reagiert empfindlich auf den Offlinemodus. Die folgenden Aspekte sollten berücksichtigt werden:
> * Wenn die Unternehmensportal-App nicht installiert ist, kann die Identität von Dateien nicht markiert werden.
>
> * Wenn die Unternehmensportal-App installiert ist, die App aber nicht über die Richtlinie verfügt, kann die Identität von Dateien nicht zuverlässig markiert werden.
>
> * Wenn das Markieren der Dateiidentität verfügbar wird, werden alle zuvor erstellte Dateien als persönlich (zur Identität der leeren Zeichenfolge gehörend) behandelt, wenn die App nicht zuvor als verwaltete App mit einzelner Identität installiert wurde. In diesem Fall werden sie als zu dem registrierten Benutzer gehörend behandelt.

####<a name="data-protection"></a>Datenschutz

Es ist nicht möglich, eine Datei als zu mehreren Identitäten gehörend zu kennzeichnen. Apps, die zu einem anderen Benutzer gehörende Daten in der gleichen Datei speichern müssen, können dies manuell mit den von ```MAMDataProtectionManager``` bereitgestellten Features ausführen. Auf diese Weise kann die App Daten verschlüsseln und an einen bestimmten Benutzer binden. Die verschlüsselten Daten eignen sich für die Speicherung in einer Datei auf dem Datenträger. Sie können die Daten abfragen, die der Identität zugeordnet sind, und die Daten können später entschlüsselt werden.

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
 * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
 * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
 *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
 *            Otherwise it will be impossible to get protection info
 *            without advancing the stream position. The stream must be
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
 *            returned by a previous call to protect() or a copy of
 *            such bytes.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
###<a name="content-providers"></a>Inhaltsanbieter

Wenn die App Unternehmensdaten potenziell anders als ein ```ParcelFileDescriptor``` über einen ```ContentProvider``` bereitstellt, muss die App die ```MAMContentProvider```-Methode ```isProvideContentAllowed(String)``` aufrufen und den Besitzer-```UPN``` für den Inhalt übergeben. Wenn diese Funktion FALSE zurückgibt, kann der Inhalt nicht an den Aufrufer zurückgegeben werden. Durch einen Inhaltsanbieter zurückgegebene Dateideskriptoren werden automatisch auf Grundlage der Dateiidentität behandelt.

###<a name="selective-wipe"></a>Selektives Zurücksetzen

Wenn eine App für die ```WIPE_USER_DATA```-Benachrichtigung registriert wird, genießt sie nicht den Vorteil des SDK-Standardverhaltens bei der selektiven Zurücksetzung. Für Apps, die mehrere Identitäten verwenden können, kann dies wichtiger sein, weil die selektive Zurücksetzung nach MAM-Standard nur Dateien zurücksetzt, die der zurückzusetzenden Identität entsprechen.

Wenn Sie eine App erstellen, die mehrere Identitäten verwenden kann, können Sie diese für ```WIPE_USER_AUXILIARY_DATA``` registrieren. Durch diese Benachrichtigung können Sie das Standardverhalten des SDK zum Zurücksetzen nutzen. Diese Benachrichtigung wird unmittelbar vor der Ausführung der selektiven Zurücksetzung nach SDK-Standard gesendet. Beachten Sie, dass eine App niemals gleichzeitig für ```WIPE_USER_DATA``` und für ```WIPE_USER_AUXILIARY_DATA``` registriert sein darf.

### <a name="known-platform-limitations"></a>Bekannte Plattformeinschränkungen

#### <a name="file-size-limitations"></a>Einschränkungen der Dateigröße

Unter Android können die Einschränkungen des Formats der ausführbaren Dalvik-Datei bei großen Codebasen, die ohne ProGuard ausgeführt werden, zu einem Problem werden. Insbesondere können die folgenden Einschränkungen auftreten:

* Einschränkung auf 65 KB bei Feldern

* Einschränkung auf 65 KB bei Methoden

Wenn Sie viele Projekte einschließen, erhält jedes `android:package` eine Kopie von R. Dadurch erhöht sich beim Hinzufügen von Bibliotheken die Anzahl der Felder erheblich. Die folgenden Empfehlungen können hilfreich sein, um diese Einschränkung ggf. zu minimieren:

* Alle Bibliotheksprojekte sollten dasselbe `android:package` gemeinsam verwenden, wenn dies möglich ist. Dabei kommt es in der Praxis nicht sporadisch zu Fehlern, weil es sich um ein reines Problem zur Buildzeit handelt. Darüber hinaus verarbeiten neuere Versionen des SDK für Android DEX-Dateien vorab, um Redundanzen zu entfernen. Dies verringert den Abstand zwischen den Feldern noch weiter.

* Verwenden Sie die neuesten verfügbaren Android SDK-Buildtools.

* Entfernen Sie alle nicht benötigten und nicht verwendeten Bibliotheken (z. B. `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Einschränkungen der Richtlinienerzwingung

**Bildschirmaufnahme**: Das SDK kann keinen neuen Wert für die Bildschirmaufnahmeeinstellung in `Activity`-Klassen erzwingen, die bereits `Activity.onCreate` durchlaufen haben. Dies kann dazu führen, dass für eine gewisse Zeit nach dem Konfigurieren der App zur Deaktivierung von Bildschirmaufnahmen weiterhin Bildschirmaufnahmen erstellt werden können.

**Inhaltskonfliktlöser**: Durch die Übertragungs- oder Empfangsrichtlinien kann die Verwendung eines Inhaltskonfliktlösers für den Zugriff auf den Inhaltsanbieter in einer anderen App ganz oder teilweise blockiert werden. Dies bewirkt, dass `ContentResolver`-Methoden NULL zurückgeben oder einen Fehlerwert auslösen. (`openOutputStream` löst z. B. bei einer Blockierung `FileNotFoundException` aus.) Die App kann diesen Aufruf zum Überprüfen ausführen, ob eine Richtlinie Fehler beim Schreiben von Daten über einen Inhaltskonfliktlöser verursacht hat (oder möglicherweise verursacht):

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exportierte Dienste**: Die im Intune App SDK enthaltene Datei `AndroidManifest.xml` weist einen `MAMNotificationReceiverService` auf. Dabei muss es sich um einen exportierten Dienst handeln, damit die Unternehmensportal-App Benachrichtigungen an eine RMS-aktivierte App senden kann. Der Dienst überprüft den Aufrufer, um sicherzustellen, dass nur die Unternehmensportal-App Benachrichtigungen senden darf.

### <a name="android-best-practices"></a>Bewährte Methoden für Android

Das Intune SDK verwaltet den von der Android-API bereitgestellten Vertrag. Es ist jedoch möglich, dass aufgrund der Richtlinienerzwingung häufiger Fehlerbedingungen ausgelöst werden. Durch diese bewährten Methoden für Android wird die Wahrscheinlichkeit, dass Fehler auftreten, gemindert:

* Es besteht eine höhere Wahrscheinlichkeit, dass Android SDK-Funktionen, die möglicherweise NULL zurückgeben, jetzt NULL sind. Um Probleme zu minimieren, stellen Sie sicher, dass Überprüfungen auf NULL an den richtigen Stellen stattfinden.

* Verwenden Sie für Features, die überprüft werden können, deren SDK-APIs für die Überprüfung.

* Alle abgeleiteten Funktionen müssen einen Aufruf ihrer übergeordneten Klassenversionen ausführen.

* Vermeiden Sie eine nicht eindeutige Verwendung von APIs. So führt beispielsweise `Activity.startActivityForResult/onActivityResult` ohne Überprüfung von `requestCode` zu unerwartetem Verhalten.



<!--HONumber=Dec16_HO3-->


