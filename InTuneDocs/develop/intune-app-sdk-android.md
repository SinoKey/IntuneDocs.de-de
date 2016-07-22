---
title: "Entwicklerhandbuch zum Microsoft Intune App SDK für Android | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2915cca314b489bbcb590d01b03a0b38134fa619
ms.openlocfilehash: d2e4b6903d86b79edd9c758b2ce51733831e785a


---

# Microsoft Intune App SDK für Android – Entwicklerhandbuch

> [!NOTE]
> Lesen Sie am besten zuerst die [Übersicht über das Intune App SDK](intune-app-sdk.md). Dort finden Sie Informationen zu den aktuellen Funktionen des SDK sowie zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen. 

# Inhalt des SDK 

Das Intune App SDK für Android ist eine Android-Standardbibliothek ohne externe Abhängigkeiten. Das SDK besteht aus:  

* **`Microsoft.Intune MAM.SDK.jar`**: Die Schnittstellen, die zum Aktivieren von MAM in einer App sowie zum Aktivieren der Interoperabilität mit der Microsoft Intune-Unternehmensportal-App erforderlich sind. In Apps muss sie als Referenz zu einer Android-Bibliothek angegeben werden.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android, Version 4, nutzen.  Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android, Version 7, nutzen.   Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen.

* **Ressourcenverzeichnis**: Die Ressourcen (etwa Zeichenfolgen), die das SDK benötigt. 

* **`Microsoft.Intune.MAM.SDK.aar`**: Die SDK-Komponenten, mit Ausnahme der Support.V4- und der Support.V7-JAR-Datei. Diese Datei kann anstelle der einzelnen Komponenten verwendet werden, wenn das Buildsystem AAR-Dateien unterstützt.

* **`AndroidManifest.xml`**: Die zusätzlichen Einstiegspunkte und die Bibliotheksanforderungen. 

* **`THIRDPARTYNOTICES.TXT`**: Ein Urheberrechtshinweis für Drittanbieter- und/oder OSS-Code, der in Ihrer App kompiliert wird. 

# Anforderungen 

Das Intune App SDK ist ein kompiliertes Android-Projekt. Daher ist es größtenteils unabhängig von der Version von Android, die die App für ihre API-Mindest- bzw. -Zielversion verwendet. Das SDK unterstützt Android API 14 (Android 4.0 und höher) bis Android 24. 

# Funktionsweise des Intune App SDK 

Das Intune App SDK erfordert Änderungen am Quellcode einer App, damit App-Verwaltungsrichtlinien aktiviert werden können. Zu diesem Zweck werden Android-Basisklassen durch äquivalente verwaltete Klassen ersetzt, auf die im Dokument mit dem Präfix `MAM`. Die SDK-Klassen befinden sich zwischen der Android-Basisklasse und der App-eigenen abgeleiteten Version dieser Klasse.  Wenn Sie beispielsweise "Activity" verwenden, erhalten Sie eine Vererbungshierarchie, die wie folgt aussieht: `Activity ->MAMActivity->AppSpecificActivity`.

Wenn `AppSpecificActivity` mit dem übergeordneten Element interagieren möchte, z. B. `super.onCreate())`, ist `MAMActivity` die übergeordnete Klasse, obwohl sie sich in der Vererbungshierarchie befindet und mehrere Methoden ersetzt. Android-Apps verfügen über einen einzelnen Modus und haben über ihr Context-Objekt Zugriff auf das gesamte System.  Apps mit integriertem Intune App SDK hingegen haben Dualmodi beim Zugriff auf das System über das Context-Objekt. Je nach verwendeter Activity-Basisklasse wird das Context-Objekt jedoch entweder von Android bereitgestellt oder intelligent mithilfe von Multiplex zwischen einer begrenzten Ansicht des Systems und dem von Android bereitgestellten Context-Objekt verarbeitet.

Das Intune App SDK für Android ist darauf angewiesen, dass die Unternehmensportal-App auf dem Gerät vorhanden ist, damit MAM-Richtlinien aktiviert werden können. Wenn die Unternehmensportal-App nicht vorhanden ist, ändert sich das Verhalten der MAM-aktivierten App nicht, vielmehr verhält sie sich wie jede andere mobile App. Wenn die Unternehmensportal-App installiert ist und über eine Richtlinie für den Benutzer verfügt, werden die SDK-Einstiegspunkte asynchron initialisiert. Die Initialisierung ist nur erforderlich, wenn der Prozess ursprünglich von Android erstellt wurde. Während der Initialisierung wird eine Verbindung mit der Unternehmensportal-App hergestellt, und die App-Einschränkungsrichtlinie wird heruntergeladen.  

# Integration mit dem Intune App SDK
 
Wie bereits kurz erwähnt, erfordert das Intune App SDK Änderungen am Quellcode der App, damit App-Verwaltungsrichtlinien aktiviert werden können. Führen Sie folgende Schritte aus, um MAM in Ihrer App zu aktivieren: 

## Ersetzen von Klassen, Methoden und Aktivitäten durch das MAM-Äquivalent (erforderlich) 

* Android-Basisklassen müssen durch ihre MAM-Äquivalente ersetzt werden. Suchen Sie dazu nach allen Instanzen der in der folgenden Tabelle aufgeführten Klassen, und ersetzen Sie sie durch das Intune App SDK-Äquivalent.  

    | Android-Klasse | Intune App SDK-Äquivalent |
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
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *"Binder" muss nur durch "MAMBinder" ersetzt werden, wenn "Binder" nicht von einer AIDL-Schnittstelle generiert wird.

    **Microsoft.Intune.MAM.SDK.Suppbzw.t.v4.jar**:

    | Android-Klasse – Intune MAM | SDK-Äquivalent |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppbzw.t.v7.jar**:

    |Android-Klasse | Intune MAM SDK-Äquivalent |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* Bei Verwendung eines Android-Einstiegspunkts, der von dem MAM-Äquivalent überschrieben wurde, muss eine alternative Version des Lebenszyklus des Einstiegspunkt verwendet werden (mit Ausnahme der Klasse `MAMApplication`).

    Beispiel: Wenn von `MAMActivity`abgeleitet wird, statt `onCreate` zu überschreiben und `super.onCreate`aufzurufen, muss die Activity-Klasse `onMAMCreate` überschreiben und`uper.onMAMCreate`. So kann der Activity-Start (neben anderen) in bestimmten Fällen begrenzt werden. 

# Aktivieren von Funktionen, die App-Beteiligung erfordern 

Es gibt einige Richtlinien, die das SDK nicht selbst implementieren kann. Damit die App ihr Verhalten für diese Funktionen steuern kann, sind mehrere APIs verfügbar. Diese finden Sie in der folgenden `AppPolicy` -Schnittstelle.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

## Aktivieren der Steuerung des App-Speicherverhaltens durch IT-Administratoren

Viele Apps implementieren Funktionen, die es dem Endbenutzer ermöglichen, Dateien lokal oder bei einem anderen Dienst zu speichern. Mit dem Intune App SDK können IT-Administratoren dafür sorgen, dass keine Datenpreisgabe erfolgt, indem sie Richtlinieneinschränkungen entsprechend den Anforderungen ihrer Organisation anwenden.  Eine der durch Administratoren steuerbaren Richtlinien betrifft das Speichern in einem persönlichen Datenspeicher durch den Endbenutzer. Darunter fällt das Speichern an einem lokalen Speicherort, auf einer SD-Karte und bei Sicherungsdiensten. Damit die Funktion aktiviert werden kann, ist App-Beteiligung erforderlich. Wenn Ihre App das direkte Speichern aus der App an einem persönlichen oder Cloudspeicherort ermöglicht, müssen Sie diese Funktion implementieren, damit IT-Administratoren steuern können, ob das Speichern an einem Speicherort erlaubt ist. Die folgende API informiert die App darüber, ob das Speichern in einem persönlichen Speicher gemäß der aktuellen Adminrichtlinie zulässig ist. Die App kann dann die Richtlinie erzwingen, da sie über den persönlichen Datenspeicher informiert ist, der dem Endbenutzer über die App zur Verfügung steht.  

Um festzustellen, ob die Richtlinie erzwungen wird, kann die App folgenden Aufruf ausführen: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Hinweis**: "MAMComponents.get(AppPolicy.class)" gibt stets eine App-Richtlinie ungleich NULL zurück, und zwar auch dann, wenn das Gerät oder die App nicht verwaltet wird. 

## Zulassen, dass die App erkennt, ob die PIN-Richtlinie erforderlich ist
 
 Es gibt zusätzliche Richtlinien, bei denen die App ihre Funktionen möglicherweise zum Teil deaktivieren möchte, um Funktionen im Intune App SDK nicht zu duplizieren. Verfügt die App z. B. über eine eigene PIN-Benutzererfahrung, kann diese deaktiviert werden, wenn das SDK so konfiguriert ist, dass der Endbenutzer eine PIN eingeben muss. 

Um festzustellen, ob die PIN-Richtlinie so konfiguriert ist, dass regelmäßig die PIN-Eingabe erfordert wird, kann die App folgenden Aufruf ausführen: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## Registrieren für Benachrichtigungen vom SDK  

Das Intune App SDK erlaubt Ihrer App die Steuerung des Verhaltens, wenn bestimmte Richtlinien, z. B. eine Richtlinie zur Remotezurücksetzung, vom IT-Administrator verwendet werden. Dazu müssen Sie sich für Benachrichtigungen vom SDK registrieren, indem Sie eine `MAMNotificationReceiver` -Klasse erstellen und diese bei `MAMNotificationReceiverRegistry`. Zu diesem Zweck werden der Empfänger und der Typ der Benachrichtigung, die dieser erhalten möchte, in  `App.onCreate`angegeben, wie das folgende Beispiel veranschaulicht:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` empfängt lediglich Benachrichtigungen. Einige Benachrichtigungen werden direkt vom SDK verarbeitet, andere erfordern die Beteiligung der App. Eine App muss "true" oder "false" von einer Benachrichtigung zurückgeben. Sie muss immer "true" zurückgeben, es sei denn, eine von ihr aufgrund der Benachrichtigung ausgeführte Aktion schlägt fehl. Der Fehler kann dem Intune-Dienst gemeldet werden, etwa wenn die App angibt, dass Benutzerdaten nicht zurückgesetzt werden konnten. Ein Blockieren in `MAMNotificationReceiver.onReceive`ist sicher; der zugehörige Rückruf wird nicht im UI-Thread ausgeführt. 

Die MAMNotificationReceiver-Schnittstelle ist nachfolgend laut Definition im SDK enthalten: 

    /**
     * The SDK is signaling that a MAM event has occurred. 
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

Folgende Benachrichtigungen werden an die App gesendet; für manche ist ggf. App-Beteiligung erforderlich: 

* **`WIPE_USER_DATA`-Benachrichtigung**: Diese Benachrichtigung wird in einer `MAMUserNotification`-Klasse gesendet. Beim Empfang dieser Benachrichtigung sollte die App alle Daten im Zusammenhang mit der mit `MAMUserNotification`. Diese Benachrichtigung wird derzeit bei der Aufhebung der Registrierung beim Intune-Dienst gesendet. Der primäre Name des Benutzers wird in der Regel während der Registrierung angegeben. Wenn Sie sich für diese Benachrichtigung registrieren, muss Ihre App sicherstellen, dass alle Benutzerdaten gelöscht wurden. Wenn Sie sich nicht für sie registrieren, wird das Standardverhalten für die selektive Zurücksetzung ausgeführt. 

* **`WIPE_USER_AUXILIARY_DATA`-Benachrichtigung**: Apps können sich für diese Benachrichtigung registrieren, wenn das Intune App SDK die Standardzurücksetzung ausführen soll, aber bei der Zurücksetzung weitere Daten entfernt werden sollen.  

* **`REFRESH_POLICY`-Benachrichtigung**: Diese Benachrichtigung wird in einer MAMNotification ohne weitere Informationen gesendet. Bei Empfang dieser Benachrichtigung ist keine zwischengespeicherte Richtlinie mehr als ungültig zu erachten, und aus diesem Grund ist eine Überprüfung der Art der Richtlinie durchzuführen. In der Regel wird diese Aufgabe vom SDK ausgeführt, sollte aber von der App ausgeführt werden, wenn die Richtlinie beständig verwendet wird. 

## Ausstehende Intents und Methoden 

Nach der Ableitung von einem der MAM-Einstiegspunkte können Sie "Context" ganz normal für Activity-Starts mithilfe von `PackageManager`usw. verwenden.  `PendingIntents` sind eine Ausnahme von dieser Regel. Beim Aufrufen dieser Klassen müssen Sie den Klassennamen ändern. Anstelle von `PendingIntent.get*` muss z. B. `MAMPendingIntents.get*` verwendet werden. 

In einigen Fällen wurde eine in der Android-Klasse verfügbare Methode in der äquivalenten MAM-Klasse als abgeschlossen gekennzeichnet. In diesem Fall enthält die äquivalente MAM-Klasse eine Methode mit ähnlichem Namen (normalerweise mit dem Suffix "MAM"), die stattdessen überschrieben werden sollte. Beispiel: Anstelle von `ContentProvider.query`würden Sie `MAMContentProvider.queryMAM`. Der Java-Compiler sollte die abgeschlossenen Einschränkungen erzwingen, um zu verhindern, dass die ursprüngliche Methode anstelle des MAM-Äquivalents überschrieben wird. 

# Schutz von Sicherungsdaten 

Seit Android Marshmallow (API 23) bietet Android einer App zwei Möglichkeiten zum Sichern ihrer Daten. Diese Optionen stehen in Ihrer App zur Verwendung zur Verfügung; sie erfordern verschiedene Schritte, um sicherzustellen, dass der MAM-Datenschutz ordnungsgemäß angewendet wird. In der folgenden Tabelle können Sie sich schnell einen Überblick über die entsprechenden Aktionen verschaffen, die für ein korrektes Verhalten beim Datenschutz erforderlich sind.  Weitere Informationen zur Android-Sicherung finden Sie im [Android Developer-Handbuch zur Datensicherung](http://developer.android.com/guide/topics/data/backup.html.). 

## Automatische vollständige Sicherung

Seit Android M bietet Android automatische vollständige Sicherungen für Apps unabhängig von der Ziel-API bei Ausführung auf einem Android M-Gerät. Sofern das Attribut `android:allowBackup` nicht "false" ist, erhält eine App vollständige, nicht gefilterte Sicherungen. Dadurch entsteht das Risiko einer Datenpreisgabe. Daher erfordert das SDK die in der folgenden Tabelle aufgeführten Änderungen, um sicherzustellen, dass Datenschutz angewendet wird.  Die nachfolgend beschriebenen Richtlinien sollten für einen ordnungsgemäßen Schutz von Kundendaten eingehalten werden.  Wenn Sie `android:allowBackup=false` festlegen, wird Ihre App niemals vom Betriebssystem für Sicherungen in eine Warteschlange gestellt, und es liegen keine weiteren Aktionen für MAM an, da keine Sicherung stattfindet.
 
 ## „key/value“-Sicherungen

Diese Option ist für alle APIs verfügbar; sie verwendet `BackupAgent` und `BackupAgentHelper`. 

### Verwenden von BackupAgentHelper

`BackupAgentHelper` ist viel einfacher zu implementieren als `BackupAgent`, was systemeigene Android-Funktionalität und MAM-Integration anbelangt. `BackupAgentHelper` ermöglicht dem Entwickler, ganze Dateien und gemeinsam genutzte Einstellungen bei `FileBackupHelper` bzw. `SharedPreferencesBackupHelper` zu registrieren, die bei Erstellung dann `BackupAgentHelper` hinzugefügt werden. 

### Verwenden von BackupAgent

`BackupAgent` ermöglicht Ihnen eine explizitere Angabe der zu sichernden Daten. Bei Verwendung dieser Option können Sie jedoch nicht das Sicherungsframework von Android verwenden.  Da Sie in vollem Umfang für die Implementierung verantwortlich sind, müssen mehr Schritte ausgeführt werden, um den ordnungsgemäßen Datenschutz von MAM sicherzustellen. Da die Arbeit größtenteils von Ihnen als Entwickler zu leisten ist, ist die MAM-Integration etwas komplizierter. 

#### App hat keinen Sicherungs-Agent
  
Dies sind die Entwickleroptionen, wenn `Android:allowbBackup =true`:

##### Vollständige Sicherung gemäß einer Konfigurationsdatei: 

Geben Sie unter dem `com.microsoft.intune.mam.FullBackupContent` -Metadatentag in Ihrem Manifest eine Ressource an. Beispiel:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Fügen Sie folgendes Attribut im `<application>` -Tag hinzu: `android:fullBackupContent="@xml/my_scheme"`, wobei `my_scheme` eine XML-Ressource in Ihrer App ist. 

##### Vollständige Sicherung ohne Ausnahmen 

Geben Sie ein Tag im Manifest an, z. B. `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Fügen Sie im `<application>`-Tag folgendes Attribut hinzu: `android:fullBackupContent="true"`.

#### App hat einen Sicherungs-Agent

Befolgen Sie die Empfehlungen in den oben stehenden Abschnitten `BackupAgent` und `BackupAgentHelper` . 

Wechseln Sie ggf. zu unserem `MAMDefaultFullBackupAgent`, der eine einfache Sicherung für Android M bietet. 

### Vor der Sicherung

Überprüfen Sie vor dem Sichern, dass die zu sichernden Dateien oder Datenpuffer wirklich gesichert werden dürfen. Wir haben eine `isBackupAllowed` -Funktion in `MAMFileProtectionManager` und `MAMDataProtectionManager` eingefügt, um diese Überprüfung durchzuführen. Wenn die Sicherung der Datei oder des Datenpuffers nicht zulässig ist, sollten Sie von einer Verwendung in Ihrer Sicherung absehen.

Wenn während der Sicherung die Identitäten der in Schritt 1 überprüften Dateien gesichert werden sollen, müssen Sie `backupMAMFileIdentity(BackupDataOutput data, File … files)` mit den Dateien aufrufen, aus denen Sie Daten extrahieren möchten. So werden automatisch neue Sicherungsentitäten für Sie erstellt und in `BackupDataOutput` geschrieben. Diese Entitäten werden bei der Wiederherstellung automatisch genutzt. 

## Konfigurieren der Authentifizierungsbibliothek des Azure-Verzeichnisses (ADAL)  

Das SDK basiert für seine Szenarien für Authentifizierung und bedingten Start auf ADAL. Dazu benötigen Apps bestimmte Werte in der Azure Active Directory-Konfiguration. Die Konfigurationswerte werden dem SDK über `AndroidManifest` -Metadaten übermittelt. Zum Konfigurieren der App und zum Aktivieren der geeigneten Authentifizierung fügen Sie dem App-Knoten in `AndroidManifest`. Einige dieser Konfigurationen sind nur erforderlich, wenn Ihre App für die Authentifizierung im Allgemeinen ADAL verwendet; in diesem Fall benötigen Sie die speziellen Werte, die die App verwendet, um sich selbst bei AAD zu registrieren. Damit wird sichergestellt, dass der Endbenutzer nicht zweimal zur Authentifizierung aufgefordert wird, weil AAD zwei separate Registrierungswerte erkennt: einen von der App und einen vom SDK. 

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

### Häufig verwendete ADAL-Konfigurationen 

Nachfolgend finden Sie häufig verwendete Konfigurationen für die oben erläuterten Werte. 

#### App kann ADAL nicht integrieren

* "Authority" muss auf die gewünschte Umgebung festgelegt werden, in der AAD-Konten konfiguriert wurden.

* "SkipBroker" muss auf "true" festgelegt werden.

#### App kann ADAL integrieren

* "Authority" muss auf die gewünschte Umgebung festgelegt werden, in der AAD-Konten konfiguriert wurden.

* "ClientID" muss auf die Client-ID der App festgelegt werden.

* `NonBrokerRedirectURI` sollte auf einen gültigen Umleitungs-URI für die App festgelegt werden.
    * Or `urn:ietf:wg:oauth:2.0:oob` muss als gültiger Umleitungs-URI für AAD konfiguriert werden.

* "SkipBroker" muss auf "false" festgelegt werden (oder darf nicht vorhanden sein).

* AAD muss so konfiguriert sein, dass der Umleitungs-URI des Brokers akzeptiert wird.

#### App kann ADAL integrieren, unterstützt aber nicht die AAD Authenticator-App

* "Authority" muss auf die gewünschte Umgebung festgelegt werden, in der AAD-Konten konfiguriert wurden.

* "ClientID" muss auf die Client-ID der App festgelegt werden.

* `NonBrokerRedirectURI` muss auf einen gültigen Umleitungs-URI für die App festgelegt werden.

    * Or `urn:ietf:wg:oauth:2.0:oob` sollte als gültiger Umleitungs-URI für AAD konfiguriert werden.

## Aktivieren der Protokollierung im SDK 

Die Protokollierung erfolgt über das `java.util.logging` -Framework. Richten Sie zum Empfangen von Protokollen die globale Protokollierung ein, wie im [Technischen Handbuch zu Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Je nach App ist `App.onCreate` normalerweise die beste Stelle, um die Protokollierung zu initiieren. Protokollmeldungen werden mit dem Klassennamen verschlüsselt, der möglicherweise verborgen ist.

# Bekannte Plattformeinschränkungen 

## Einschränkungen bei der Dateigröße 

Unter Android können die Einschränkungen des Formats der ausführbaren Dalvik-Datei bei großen Codebasen, die ohne ProGuard ausgeführt werden, zu einem Problem werden. Insbesondere können die folgenden Einschränkungen auftreten: 

* Einschränkung auf 65 KB bei Feldern.

* Einschränkung auf 65 KB bei Methoden.

Wenn Sie viele Projekte einschließen, erhält jedes "android:package" eine Kopie von R. Dadurch erhöht sich beim Hinzufügen von Bibliotheken die Anzahl der Felder erheblich. Die folgenden Empfehlungen können hilfreich sein, um diese Einschränkung zu minimieren:
 
* Alle Bibliotheksprojekte sollten dasselbe "android:package" gemeinsam verwenden, wenn dies möglich ist. Dabei kommt es in der Praxis nicht sporadisch zu Fehlern, da es sich um ein reines Problem zur Buildzeit handelt.   Darüber hinaus verarbeiten neuere Versionen des SDK für Android DEX-Dateien vorab, um Redundanzen zu entfernen. Dies verringert den Abstand zwischen den Feldern noch weiter.

* Verwenden Sie die neuesten verfügbaren Android SDK-Buildtools.

* Entfernen Sie alle nicht benötigten und nicht verwendeten Bibliotheken (z. B. `android.support.v4`)

## Einschränkungen der Richtlinienerzwingung

**Bildschirmaufnahme**: Das SDK kann keinen neuen Wert für die Bildschirmaufnahmeeinstellung in "Activities" erzwingen, die bereits "Activity.onCreate" durchlaufen haben. Dies kann dazu führen, dass für eine gewisse Zeit nach dem Konfigurieren der App zur Deaktivierung von Bildschirmaufnahmen weiterhin Bildschirmaufnahmen erstellt werden können.

**Verwenden von Inhaltsresolvers*: Durch die Übertragungs- oder Empfangsrichtlinien kann die Verwendung eines Inhaltsresolvers für den Zugriff auf den Inhaltsanbieter in einer anderen App ganz oder teilweise blockiert werden. Dadurch geben ContentResolver-Methoden NULL oder einen Fehlerwert zurück (z. B. gibt `openOutputStream` bei Blockierung `FileNotFoundException` zurück). Die App kann feststellen, ob ein Fehler beim Schreiben von Daten durch einen Inhaltsresolver durch die Richtlinie verursacht wurde (oder würde), indem folgender Aufruf ausgeführt wird:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exportierte Dienste**: Die im Intune App SDK enthaltene Datei `AndroidManifest.xml` enthält `MAMNotificationReceiverService`; dies muss ein exportierter Dienst sein, damit das Unternehmensportal Benachrichtigungen an eine App mit aktiviertem Intune App SDK senden kann. Der Dienst prüft den Aufrufer, um sicherzustellen, dass nur das Unternehmensportal Benachrichtigungen senden kann. 

# Empfohlene und bewährte Methoden für Android 

Das Intune SDK verwaltet des von der Android-API bereitgestellten Vertrag; jedoch ist es möglich, dass aufgrund der Richtlinienerzwingung häufiger Fehlerbedingungen ausgelöst werden. Durch diese bewährten Methoden für Android wird die Wahrscheinlichkeit, dass Fehler auftreten, gemindert: 

* Es besteht die höhere Wahrscheinlichkeit, dass Android SDK-Funktionen, die möglicherweise NULL zurückgeben, jetzt NULL sind.  Um Probleme zu minimieren, stellen Sie sicher, dass NULL-Überprüfungen an den richtigen Stellen stattfinden.

* Funktionen, die überprüft werden können, müssen über die zugehörigen SDK-APIs überprüft werden.

* Alle abgeleiteten Funktionen müssen an ihre übergeordneten Klassenversionen einen durchgehenden Aufruf ausführen.

* Vermeiden Sie eine nicht eindeutige Verwendung von APIs. So führt beispielsweise `Activity.startActivityForResult/onActivityResult` ohne Überprüfung von "requestCode" zu unerwartetem Verhalten.



<!--HONumber=Jun16_HO4-->


