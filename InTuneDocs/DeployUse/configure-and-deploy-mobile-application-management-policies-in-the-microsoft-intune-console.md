---
# required metadata

title: Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Anwendungen in der Microsoft Intune-Konsole | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Anwendungen in der Microsoft Intune-Konsole
Verwaltungsrichtlinien für mobile Anwendungen in Microsoft Intune ermöglichen Ihnen das Ändern der Funktionalität von Apps, die Sie bereitstellen, um sie auf die Kompatibilitäts- und Sicherheitsrichtlinien Ihres Unternehmens abzustimmen. Sie können z. B. Ausschneide-, Kopier- und Einfügevorgänge innerhalb einer verwalteten App einschränken oder eine App so konfigurieren, dass alle Weblinks innerhalb des Managed Browser geöffnet werden.

Unterstützung der Verwaltungsrichtlinien für mobile Anwendungen:

-   Geräte unter Android 4 und höher.

-   Geräte unter iOS 7 und höher.

> [!TIP] Verwaltungsrichtlinien für mobile Anwendungen unterstützen Geräte, die bei Intune registriert sind.
>
> Informationen zum Erstellen von App-Verwaltungsrichtlinien für Geräte, die nicht von Intune verwaltet werden, finden Sie unter [Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Im Gegensatz zu anderen Intune-Richtlinien wird eine Verwaltungsrichtlinie für mobile Anwendungen nicht direkt bereitgestellt. Stattdessen verknüpfen Sie die Richtlinie mit der App, die Sie einschränken möchten. Wenn die Anwendung bereitgestellt wird und auf Geräten installiert ist, werden die von Ihnen angegebenen Einstellungen wirksam.

Zum Anwenden von Einschränkungen auf eine App muss die App das Microsoft Intune App SDK enthalten. Es gibt drei Möglichkeiten, um diesen App-Typ zu beziehen:

-   **Verwenden einer richtlinienverwalteten App**: Verfügt über die integrierte App-SDK. Um diesen App-Typ hinzuzufügen, geben Sie in einem App Store wie iTunes Store oder Google Play einen Link zur App an. Es ist keine weitere Bearbeitung für diesen App-Typ erforderlich. Hier finden Sie eine Liste von [Apps zur Verwendung mit den Microsoft Intune-Verwaltungsrichtlinien für mobile Anwendungen](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Verwenden einer „umschlossenen“ App**: Apps, die mithilfe des **Microsoft Intune App Wrapping Tool** neu gepackt werden, sodass sie das App-SDK enthalten. Dieses Tool wird normalerweise verwendet, um Unternehmensanwendungen zu verarbeiten, die intern erstellt wurden. Es kann nicht verwendet werden, um Apps zu verarbeiten, die aus dem App Store heruntergeladen wurden. Weitere Informationen finden Sie unter [Vorbereiten von iOS-Apps für die Verwaltung mobiler Anwendungen mit dem Microsoft Intune App Wrapping-Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Microsoft Intune App Wrapping-Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Schreiben einer eigenen App, die das Intune App SDK beinhaltet**: Mit dem Intune App SDK können Sie App-Verwaltungsfeatures integrieren, während Sie die App entwickeln. Weitere Informationen finden Sie unter [Übersicht über das Intune App SDK](/develop/intune-app-sdk).

Hilfe bei der Auswahl der zu verwendenden Methode (App Wrapping-Tool oder Intune App SDK) erhalten Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

Einige verwaltete Apps, wie die Outlook-App für iOS und Android, unterstützen **mehrere Identitäten**. Dies bedeutet, dass Intune Verwaltungseinstellungen nur auf Unternehmenskonten oder Daten in der App anwendet.

Beispiel für die Verwendung der Outlook-App:

-   Wenn der Benutzer eine Unternehmens-App und ein persönliches E-Mail-Konto konfiguriert, wendet Intune nur auf das Unternehmenskonto Verwaltungseinstellungen an. Das persönliche Konto wird nicht verwaltet.

-   Wenn das Gerät abgekoppelt oder abgemeldet wird, werden darauf nur unternehmensbezogene Outlook-Daten entfernt.

-   Das verwendete Unternehmenskonto muss dasselbe Konto sein, mit dem das Gerät bei Intune registriert wurde.

> [!TIP] Wenn Sie Intune mit Configuration Manager verwenden, finden Sie Informationen unter [Steuern von Apps mithilfe von Verwaltungsrichtlinien für mobile Anwendungen in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## Erstellen und Bereitstellen einer App mit einer Verwaltungsrichtlinie für mobile Anwendungen

-   **Schritt 1:** Rufen Sie den Link zu einer richtlinienverwalteten App ab, und erstellen Sie eine umschlossene App, oder verwenden Sie das Intune App SDK, um eine für MAM aktivierte App zu erstellen.

-   **Schritt 2:** Veröffentlichen Sie die App in Ihrem Cloudspeicher.

-   **Schritt 3:** Erstellen Sie eine Verwaltungsrichtlinie für mobile Anwendungen.

-   **Schritt 4:** Stellen Sie die App bereit, und wählen Sie die Option zum Verknüpfen der App mit einer Verwaltungsrichtlinie für mobile Anwendungen aus.

-   **Schritt 5:** Überwachen Sie die App-Bereitstellung.

## **Schritt 1:** Rufen Sie den Link zu einer richtlinienverwalteten App ab, und erstellen Sie eine umschlossene App, oder verwenden Sie das Intune App SDK, um eine für MAM aktivierte App zu erstellen.

-   **So rufen Sie einen Link zu einer richtlinienverwalteten App in einem App Store ab**: Suchen Sie im App Store die URL der richtlinienverwalteten App, die Sie bereitstellen möchten, und notieren Sie sie.

    Die URL der Microsoft Word für iPad-App lautet beispielsweise **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## **Schritt 2:** Veröffentlichen Sie die App in Ihrem Cloudspeicher.
Beim Veröffentlichen einer verwalteten App unterscheiden sich die Verfahren abhängig davon, ob Sie eine richtlinienverwaltete App veröffentlichen oder eine App, die mit dem Microsoft Intune App Wrapping Tool für iOS verarbeitet wurde.

#### So veröffentlichen Sie eine richtlinienverwaltete App

1.  Wenn Sie bereit für den Upload der App in Ihren Cloudspeicher sind, führen Sie die Schritte unter [Hinzufügen von Apps für mobile Geräte in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) aus.

2.  Verwenden Sie für iOS-Apps unter **Wählen Sie aus, wie diese Software für Geräte bereitgestellt werden soll**die Option **Verwaltete iOS-App aus dem App Store**.

    Wählen Sie für Android-Apps **Externer Link**aus.

3.  Geben Sie unter **Geben Sie die URL an**die zuvor notierte URL zur richtlinienverwalteten App ein.

Nach Abschluss des Uploads wird **Ja** für die **App-Verwaltungsrichtlinien** auf der Seite der **Softwareeigenschaften** für die hochgeladene App angezeigt.

Nachdem Sie überprüft haben, dass die Anwendung erfolgreich hochgeladen wurde, fahren Sie mit Schritt 3 fort.

#### So veröffentlichen Sie eine App, die mit dem Microsoft Intune App Wrapping Tool verarbeitet wurde

1.  Wenn Sie bereit für den Upload der App in Ihren Cloudspeicher sind, führen Sie die Schritte unter [Hinzufügen von Apps für mobile Geräte in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) aus.

2.  Geben Sie unter **Wählen Sie aus, wie diese Software für Geräte bereitgestellt werden soll**die Option **Software Installer**an.

3.  Wählen Sie **App-Paket für iOS (&#42;IPA-Datei)** unter **Dateityp des Softwareinstallationsprogramms** aus.

Nach Abschluss des Uploads wird **Ja** für die **App-Verwaltungsrichtlinien** auf der Seite der **Softwareeigenschaften** für die hochgeladene App angezeigt.

Nachdem Sie überprüft haben, dass die Anwendung erfolgreich hochgeladen wurde, fahren Sie mit Schritt 3 fort.

## **Schritt 3:** Erstellen Sie eine Verwaltungsrichtlinie für mobile Anwendungen.

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren und stellen Sie eine der folgenden **Software** -Richtlinien bereit, je nach Gerätetyp, für den Sie Apps konfigurieren möchten:

    -   **Richtlinie zur mobilen Anwendungsverwaltung (Android 4 und höher)**

    -   **Richtlinie zur mobilen Anwendungsverwaltung (iOS 7 und höher)**

    Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Konfigurieren Sie die folgenden Einstellungen nach Bedarf. Die Optionen unterscheiden sich je nach Gerätetyp, für den Sie die Richtlinie konfigurieren.

|Name der Einstellung|Details|
    |---------|--------------------|
    |**Name**|Geben Sie einen Namen für diese Richtlinie ein.|
    |**Beschreibung**|Geben Sie optional eine Beschreibung für diese Richtlinie ein.|
    |**Einschränken von anzuzeigenden Webinhalten in einem unternehmensverwalteten Browser**|Wenn diese Einstellung aktiviert ist, werden alle Links aus der App in Managed Browser geöffnet. Sie müssen diese App auf Geräten bereitstellen, damit diese Option funktioniert.|
    |**Verhindern von Android-Sicherungen** oder **Verhindern von iTunes- und iCloud-Sicherungen**|Deaktiviert die Sicherung von Informationen aus der App.|
    |**App Übertragung von Daten an andere Apps erlauben**|Gibt die Apps an, denen diese App Daten senden kann. Sie können auswählen, die Datenübertragung an eine beliebige App nicht zu erlauben, nur die Übertragung an andere verwaltete Apps zu erlauben oder die Übertragung an beliebige Apps zuzulassen. Diese Einstellung steuert nicht die Verwendung der Funktion **Öffnen In** auf mobilen Geräten.<br /><br />Wenn Sie beispielsweise Datenübertragungen nicht zulassen, schränken Sie die Datenübertragung an Dienste wie SMS-Messaging, das Zuweisen von Bildern zu Kontakten und das Posten von Beiträgen in Facebook oder Twitter ein.<br /><br />Um für iOS-Geräte den Austausch von Dokumenten zwischen verwalteten und nicht verwalteten Apps zu verhindern, müssen Sie eine Sicherheitsrichtlinie für mobile Geräte konfigurieren und bereitstellen, die die Einstellung **Verwaltete Dokumente in anderen nicht verwalteten Apps zulassen** deaktiviert. Bei Zulassung der Übertragung nur auf andere verwaltete Apps werden die Intune PDF- und Image-Viewer (sofern bereitgestellt) verwendet, um den Inhalt der jeweiligen Typen zu öffnen.<br /><br />Wenn Sie diese Option auf **Richtlinienverwaltete Apps** oder **Keine** festlegen, wird zudem das iOS 9-Feature blockiert, das der Spotlight-Suche erlaubt, Daten in Apps zu suchen.|
    |**App Empfang von Daten aus anderen Apps erlauben**|Gibt die Apps an, von denen diese App Daten empfangen kann. Sie können auswählen, die Datenübertragung aus einer beliebigen App nicht zu erlauben, nur die Übertragung aus anderen verwalteten Apps zu erlauben oder die Übertragung aus beliebigen Apps zuzulassen.<br /><br />Für iOS-Apps, die mehrere Identitäten unterstützen (wobei Intune nur Verwaltungseinstellungen auf Unternehmenskonten oder Daten in der App anwendet) gilt: Wenn ein Benutzer mit einem registrierten Gerät mit angewendeter Verwaltungsrichtlinie für mobile Anwendungen auf Daten aus einer App zugreift, die nicht durch eine Verwaltungsrichtlinie für mobile Anwendungen verwaltet wird, werden die Daten wie Unternehmensdaten behandelt und durch die Richtlinie geschützt.|
    |**„Speichern unter“ verhindern**|Deaktiviert die Verwendung der Option **Speichern unter** zum Speichern von Daten an persönlichen Cloudspeicherorten (z. B. OneDrive Personal oder Dropbox) in einer beliebigen App, die dieser Richtlinie unterliegt.|
    |**Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps**|Gibt an, wie Ausschneiden, Kopieren und Einfügen mit der App verwendet werden kann. Wählen Sie aus:<br /><br />**Blockiert**: Ausschneiden, Kopieren und Einfügen zwischen dieser App und anderen Apps nicht zulassen.<br /><br />**Richtlinienverwaltete Apps**: Nur Ausschneiden, Kopieren und Einfügen zwischen dieser App und anderen verwalteten Apps zulassen.<br /><br />**Richtlinienverwaltete Apps mit Einfügen**: Ermöglicht das Einfügen von aus dieser App ausgeschnittenen oder kopierten Daten nur in andere verwaltete Apps. Einfügen der aus beliebigen Apps ausgeschnittenen oder kopierten Daten in diese App zulassen.<br /><br />**Jede App**: Keine Einschränkungen beim Ausschneiden, Kopieren und Einfügen in oder aus dieser App.<br /><br />Zum Kopieren und Einfügen von Daten zwischen verwalteten Apps muss für beide Apps entweder die Einstellung **Richtlinienverwaltete Apps** oder **Richtlinienverwaltete Apps mit Einfügen** konfiguriert werden.|
    |**Einfache PIN für Zugriff erforderlich**|Der Benutzer muss eine PIN-Nummer eingeben, um die App zu verwenden. Benutzer werden aufgefordert, diese beim ersten Ausführen der App zu erstellen.|
    |**Anzahl der Versuche vor dem Zurücksetzen der PIN**|Geben Sie die Anzahl der möglichen PIN-Eingabeversuche, bevor der Benutzer die PIN zurücksetzen muss.|
    |**Unternehmensanmeldeinformationen für Zugriff erforderlich**|Erfordert, dass der Benutzer die Unternehmensanmeldeinformationen eingeben muss, bevor er auf die Anwendung zugreifen kann.|
    |**Gerätekonformität mit Unternehmensrichtlinien für Zugriff erforderlich**|Lässt die Verwendung der App nur dann zu, wenn das Gerät nicht per Jailbreak oder Rooting manipuliert wurde.|
    |**Überprüfen der Zugriffsanforderungen nach (Minuten)**|Geben Sie im Feld **Timeout** den Zeitraum ein, bevor die Zugriffsanforderungen für die App nach dem Starten der App erneut geprüft werden müssen.|
    |**Offline-Toleranzperiode**|Wenn das Gerät offline ist, geben Sie den Zeitraum ein, bevor die Zugriffsanforderungen für die App erneut geprüft werden.|
    |**App-Daten verschlüsseln**|Gibt an, dass alle mit dieser App verknüpften Daten verschlüsselt werden, einschließlich extern gespeicherte Daten, z. B. SD-Karten.<br /><br />**Verschlüsselung für iOS**<br /><br />Für Apps, die einer Intune-Verwaltungsrichtlinie für mobile Anwendungen zugeordnet sind, werden Daten im Ruhezustand mit vom Betriebssystem bereitgestellter Verschlüsselung auf Geräteebene verschlüsselt. Dies wird durch die Geräte-PIN-Richtlinie aktiviert, die vom IT-Administrator festgelegt werden muss. Wenn eine PIN erforderlich ist, werden die Daten gemäß den Einstellungen in der mobilen Anwendungsverwaltungsrichtlinie verschlüsselt. Wie in der Apple-Dokumentation angegeben, [sind die von iOS 7 verwendeten Module FIPS 140-2-zertifiziert](http://support.apple.com/en-us/HT202739).<br /><br />**Verschlüsselung für Android**<br /><br />Für Apps, die einer Intune-Verwaltungsrichtlinie für mobile Anwendungen zugeordnet sind, wird die Verschlüsselung von Microsoft bereitgestellt. Daten werden während der Datei-E/A-Vorgänge synchron verschlüsselt.  Inhalt auf dem Speicher des Geräts wird immer verschlüsselt. Die Verschlüsselungsmethode ist nicht FIPS 140-2-zertifiziert.|
    |**Blockieren von Bildschirmaufnahmen** (nur Android-Geräte)|Gibt an, dass die Screen Capture-Funktionen des Geräts blockiert werden, wenn Sie diese App verwenden.|

4.  Wählen Sie danach die Option **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## **Schritt 4:** Verknüpfen Sie die App mit einer Verwaltungsrichtlinie für mobile Anwendungen, und stellen Sie dann die App bereit.
Wenn Sie die App bereitstellen, wählen Sie die Verwaltungsrichtlinie für mobile Anwendungen auf der Seite **Mobile App-Verwaltung** aus, um die App mit der Richtlinie zu verknüpfen.

Weitere Informationen finden Sie unter [Bereitstellen von Apps in Microsoft Intune](deploy-apps.md).

> [!IMPORTANT] Für Geräte, die ältere Betriebssysteme als iOS 7.1 ausführen, werden verknüpfte Richtlinien nicht entfernt, wenn die App deinstalliert wird.
>
> Wenn das Gerät von Intune abgemeldet wird, werden die Richtlinien nicht aus den Apps entfernt. Alle Apps, auf die Richtlinien angewendet waren, behalten die Richtlinieneinstellungen bei, auch nachdem die App deinstalliert und neu installiert wurde.

### Maßnahmen, wenn eine App bereits auf Geräten bereitgestellt wurde
Es kann die Situation eintreten, dass Sie eine App bereitstellen und von einem der Benutzer oder auf einem der Geräte bereits eine nicht verwaltete Version der App installiert wurde. Beispiel: Ein Benutzer hat Microsoft Word über den App-Store installiert.

In diesem Fall müssen Sie den Benutzer bitten, die nicht verwaltete Version manuell zu deinstallieren, damit die von Ihnen konfigurierte verwaltete Version installiert werden kann.

Bei Geräten unter iOS 9 und höher wird der Benutzer automatisch um die Genehmigung gebeten, dass Intune die Verwaltung der vorhandenen App übernehmen darf. Wenn der Benutzer zustimmt, wird die App von Intune verwaltet, und alle Verwaltungsrichtlinien für mobile Anwendungen, die Sie der App zugeordnet haben, werden ebenfalls angewendet.

> [!TIP] Wenn sich das Gerät im überwachten Modus befindet, übernimmt Intune die Verwaltung der vorhandenen App, ohne den Benutzer vorher um Genehmigung zu bitten.

## **Schritt 5:** Überwachen Sie die App-Bereitstellung.
Nachdem Sie eine mit einer Verwaltungsrichtlinie für mobile Anwendungen verknüpfte App erstellt und bereitgestellt haben, verwenden Sie das folgende Verfahren, um die App zu überwachen und alle Richtlinienkonflikte zu lösen.

#### Anzeigen des Status der Bereitstellung

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Gruppen** &gt; **Übersicht**.

2.  Führen Sie einen der folgenden Schritte aus:

    -   Wählen Sie **Alle Benutzer**, und doppelklicken Sie auf den Benutzer, dessen Geräte Sie überprüfen möchten. Wählen Sie auf der Seite **Benutzereigenschaften** die Option **Geräte**, und doppelklicken Sie dann auf das Gerät, das Sie untersuchen möchten.

    -   Wählen Sie **Alle Geräte** &gt; **Alle mobilen Geräte**. Wählen Sie auf der Seite **Gerätegruppeneigenschaften** die Option **Geräte**, und doppelklicken Sie dann auf das Gerät, das Sie untersuchen möchten.

3.  Wählen Sie auf der Seite **Eigenschaften für mobile Geräte** die Option **Richtlinie**, um eine Liste der Verwaltungsrichtlinien für mobile Anwendungen anzuzeigen, die auf dem Gerät bereitgestellt wurden.

4.  Wählen Sie die Verwaltungsrichtlinie für mobile Anwendungen aus, deren Status Sie anzeigen möchten. Sie können die Details der Richtlinie im unteren Bereich anzeigen und den Knoten erweitern, um ihre Einstellungen anzuzeigen.

5.  Unter der Spalte **Status** jeder Verwaltungsrichtlinie für mobile Anwendungen wird **Konform**, **Konform (Ausstehend)**oder **Fehler** angezeigt. Besteht in der ausgewählten Richtlinie für eine oder mehrere Einstellungen ein Konflikt, wird **Fehler** in diesem Feld angezeigt.

6.  Nachdem Sie einen Konflikt ermittelt haben, können Sie in Konflikt stehende Richtlinieneinstellungen überarbeiten, sodass sie die dieselbe Einstellung verwenden, oder nur eine Richtlinie für die App und die Benutzer bereitstellen.

### Wie Richtlinienkonflikte gelöst werden
Wenn bei einer Verwaltungsrichtlinie für mobile Anwendungen bei der ersten Bereitstellung für den Benutzer oder das Gerät ein Konflikt auftritt, wird der jeweilige in Konflikt stehende Einstellungswert aus der Richtlinie für die App entfernt, und die App verwendet einen vorgegebenen Konfliktwert.

Wenn bei einer späteren Bereitstellung ein Konflikt in der Verwaltungsrichtlinie für mobile Anwendungen für den Benutzer oder das Gerät auftritt, wird der jeweilige in Konflikt stehende Einstellungswert nicht in der Richtlinie für die App aktualisiert, und die App verwendet den vorhandenen Wert für diese Einstellung.

In Fällen, in denen das Gerät oder der Benutzer zwei in Konflikt stehende Richtlinien erhält, gilt Folgendes:

-   Wenn bereits eine Richtlinie mit dem Gerät bereitgestellt wurde, werden die vorhandenen Richtlinieneinstellungen nicht überschrieben.

-   Wenn keine Richtlinie für das Gerät bereitgestellt wurde und zwei widersprüchliche Einstellungen bereitgestellt werden, wird die in das Gerät integrierte Standardeinstellung verwendet.


<!--HONumber=Jun16_HO2-->


