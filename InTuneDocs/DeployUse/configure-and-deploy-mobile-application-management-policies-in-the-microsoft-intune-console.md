---
title: Configure and deploy mobile application management policies in the Microsoft Intune console
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
author: robstackmsft
---
# Configure and deploy mobile application management policies in the Microsoft Intune console
Verwaltungsrichtlinien für Mobile Anwendung in Microsoft Intune können Sie die Funktionalität von apps ändern, die Sie bereitstellen, um sie mit Ihrem Unternehmen Compliance-und Sicherheitsrichtlinien anzupassen. Sie können z. B. Ausschneide-, Kopier- und Einfügevorgänge innerhalb einer verwalteten App einschränken oder eine App so konfigurieren, dass alle Weblinks innerhalb des Managed Browser geöffnet werden.

Unterstützung der Verwaltungsrichtlinien für mobile Anwendungen:

-   Geräte unter Android 4 und höher.

-   Geräte unter iOS 7 und höher.

> [!TIP]
> Verwaltungsrichtlinien für Mobile unterstützt Geräte, die mit Intune registriert sind.
> 
> Wenn Sie Informationen über das Erstellen von app-Verwaltungsrichtlinien für Geräte, die nicht von Intune verwaltet werden, finden Sie unter Suchen [Loss Prevention app Datenrichtlinien mit Microsoft Intune konfigurieren](configure-data-loss-prevention-app-policies-with-microsoft-intune.md).

Im Gegensatz zu anderen Intune-Richtlinien denen Sie eine Verwaltungsrichtlinie für mobile Anwendung nicht direkt bereitgestellt. Stattdessen verknüpfen Sie die Richtlinie mit der App, die Sie einschränken möchten. Wenn die Anwendung bereitgestellt wird und auf Geräten installiert ist, werden die von Ihnen angegebenen Einstellungen wirksam.

Zum Anwenden von Einschränkungen zu einer Anwendung muss die app Microsoft App Software Development Kit (SDK) integriert. Es gibt zwei Möglichkeiten, um diesen App-Typ zu beziehen:

-   **Verwenden eine richtlinienverwalteten app** – verfügt über die integrierte App SDK. Um diesen App-Typ hinzuzufügen, geben Sie in einem App Store wie iTunes Store oder Google Play einen Link zur App an. Es ist keine weitere Bearbeitung für diesen App-Typ erforderlich. Eine Liste der [Microsoft-apps Sie mit Microsoft Intune mobile Application Management-Richtlinien können](microsoft-apps-you-can-use-with-microsoft-intune-mobile-application-management-policies.md).

-   **Verwenden einer "umschlossene" app** -Apps, die neu gepackt werden, um das App SDK enthalten die **Microsoft Intune App Wrapping Tool**. Dieses Tool wird normalerweise verwendet, um Unternehmensanwendungen zu verarbeiten, die intern erstellt wurden. Es kann nicht verwendet werden, um Apps zu verarbeiten, die aus dem App Store heruntergeladen wurden. Finden Sie unter [Vorbereiten von iOS-apps für mobile Application Management mit dem Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [Vorbereiten von Android-apps für die Verwaltung der mobilen Anwendung mit dem Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Einige verwaltete apps, wie die Outlook-app für iOS und Android-Unterstützung **mehrere Identitäten**. Dies bedeutet, dass Intune Verwaltungseinstellungen nur auf Unternehmenskonten oder Daten in der App anwendet.

Beispiel für die Verwendung der Outlook-App:

-   Wenn der Benutzer eine Unternehmens-App und ein persönliches e-Mail-Konto konfiguriert, Intune gilt nur Einstellungen für das Unternehmenskonto und das persönliche Konto wird nicht verwaltet.

-   Wenn das Gerät abgekoppelt oder abgemeldet wird, werden darauf nur unternehmensbezogene Outlook-Daten entfernt.

-   Das verwendete Unternehmenskonto muss dasselbe Konto, das verwendet wurde, das Gerät mit Intune registrieren.

> [!TIP]
> Wenn Sie Intune mit Configuration Manager verwenden, finden Sie unter [Steuerelement Apps mithilfe von Mobile Application Management-Richtlinien in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## Erstellen und Bereitstellen einer App mit einer Verwaltungsrichtlinie für mobile Anwendungen

-   **Schritt 1:** Rufen Sie den Link zu einer richtlinienverwalteten App ab, oder erstellen Sie eine umschlossene App.

-   **Schritt 2:** Veröffentlichen Sie die App in Ihrem Cloudspeicher.

-   **Schritt 3:** Erstellen Sie eine Verwaltungsrichtlinie für mobile Anwendungen.

-   **Schritt 4:** Stellen Sie die App bereit, und wählen Sie die Option zum Verknüpfen der App mit einer Verwaltungsrichtlinie für mobile Anwendungen aus.

-   **Schritt 5:** Überwachen Sie die App-Bereitstellung.

## **Schritt 1:** rufen Sie den Link zu einer Richtlinie verwaltete app aus, oder erstellen Sie eine umschlossene app.

-   **Rufen Sie einen Link zu einer Richtlinie verwalteten app** – Klicken Sie im app Store, suchen, und beachten Sie die URL der richtlinienverwalteten app, die Sie bereitstellen möchten.

    Die URL des Microsoft Word für iPad-app ist z. B. **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**

-   **Erstellen Sie eine umschlossene app** -Verwenden Sie die Informationen in den Themen [Vorbereiten von iOS-apps für mobile Application Management mit dem Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) und [Vorbereiten von Android-apps für die Verwaltung der mobilen Anwendung mit dem Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) um eine umschlossene app zu erstellen.

    Das Tool erstellt eine verarbeitete App, die Sie verwenden, wenn Sie die App in Ihrem Cloud-Speicher veröffentlichen.

## **Schritt 2:** Veröffentlichen Sie die App in Ihrem Cloudspeicher.
Beim Veröffentlichen einer verwalteten App unterscheiden sich die Verfahren abhängig davon, ob Sie eine richtlinienverwaltete App veröffentlichen oder eine App, die mit dem Microsoft Intune App Wrapping Tool für iOS verarbeitet wurde.

#### So veröffentlichen Sie eine richtlinienverwaltete App

1.  Wenn Sie die app in Ihrem Cloud-Speicher hochladen möchten, führen Sie die Schritte [Veröffentlichen von Software für mobile Geräte in Microsoft Intune-cloudspeicher](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md#BKMK_PublishSoftware).

2.  Verwenden Sie für iOS-Apps unter **Wählen Sie aus, wie diese Software für Geräte bereitgestellt werden soll**die Option **Verwaltete iOS-App aus dem App Store**.

    Wählen Sie für Android-Apps **Externer Link**aus.

3.  Geben Sie unter **Geben Sie die URL an**die zuvor notierte URL zur richtlinienverwalteten App ein.

Nach Abschluss des Uploads wird **Ja** für die **App-Verwaltungsrichtlinien** auf der Seite der **Softwareeigenschaften** für die hochgeladene App angezeigt.

Nachdem Sie überprüft haben, dass die Anwendung erfolgreich hochgeladen wurde, fahren Sie mit Schritt 3 fort.

#### So veröffentlichen Sie eine App, die mit dem Microsoft Intune App Wrapping Tool verarbeitet wurde

1.  Wenn Sie die app in Ihrem Cloud-Speicher hochladen möchten, führen Sie die Schritte [Veröffentlichen von Software für mobile Geräte in Microsoft Intune-cloudspeicher](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md#BKMK_PublishSoftware).

2.  Geben Sie unter **Wählen Sie aus, wie diese Software für Geräte bereitgestellt werden soll**die Option **Software Installer**an.

3.  Wählen Sie **App-Paket für iOS (& #42;. IPA-Datei)** unter **Dateityp des Softwareinstallationsprogramms**.

Nach Abschluss des Uploads wird **Ja** für die **App-Verwaltungsrichtlinien** auf der Seite der **Softwareeigenschaften** für die hochgeladene App angezeigt.

Nachdem Sie überprüft haben, dass die Anwendung erfolgreich hochgeladen wurde, fahren Sie mit Schritt 3 fort.

## <a name="bkmk_step3"></a>**Schritt 3:** Erstellen Sie eine Verwaltungsrichtlinie für mobile Anwendungen.

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com)auf **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren und stellen Sie eine der folgenden **Software** -Richtlinien bereit, je nach Gerätetyp, für den Sie Apps konfigurieren möchten:

    -   **Richtlinie zur mobilen Anwendungsverwaltung (Android 4 und höher)**

    -   **Richtlinie zur mobilen Anwendungsverwaltung (iOS 7 und höher)**

    Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Weitere Informationen finden Sie unter [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

3.  Konfigurieren Sie die folgenden Einstellungen nach Bedarf. Die Optionen unterscheiden sich je nach Gerätetyp, für den Sie die Richtlinie konfigurieren.

|Name der Einstellung|Details|
    |---------|--------------------|
    |**Name**|Geben Sie einen Namen für diese Richtlinie ein.|
    |**Beschreibung**|Geben Sie optional eine Beschreibung für diese Richtlinie ein.|
    |**Einschränken von anzuzeigenden Webinhalten in einem unternehmensverwalteten Browser**|Wenn diese Einstellung aktiviert ist, werden alle Links aus der App in Managed Browser geöffnet. Sie müssen diese App auf Geräten bereitstellen, damit diese Option funktioniert.|
    |**Verhindern von Android-Sicherungen** oder **Verhindern von iTunes- und iCloud-Sicherungen**|Deaktiviert die Sicherung von Informationen aus der App.|
    |**App Übertragung von Daten an andere Apps erlauben**|Gibt die Apps an, denen diese App Daten senden kann. Sie können auswählen, die Datenübertragung an eine beliebige App nicht zu erlauben, nur die Übertragung an andere verwaltete Apps zu erlauben oder die Übertragung an beliebige Apps zuzulassen. Diese Einstellung steuert nicht die Verwendung der **Öffnen In** Features auf mobilen Geräten.<br /><br />Wenn Sie beispielsweise Datenübertragungen nicht zulassen, schränken Sie die Datenübertragung an Dienste wie SMS-Messaging, das Zuweisen von Bildern zu Kontakten und das Posten von Beiträgen in Facebook oder Twitter ein.<br /><br />Für iOS-Geräte von Dokumenten zwischen verwalteten und nicht verwalteten apps zu verhindern müssen Sie auch konfigurieren und Bereitstellen eine Sicherheitsrichtlinie für mobile Geräte, die die Einstellung deaktiviert **verwaltete Dokumente in anderen nicht verwalteten apps zulassen** bei Auswahl von nur Zulassung der Übertragung an andere verwaltete apps werden die Intune PDF- und Image-Viewer (sofern bereitgestellt) verwendet werden, um den Inhalt der jeweiligen öffnen...<br /><br />Darüber hinaus, wenn Sie diese Option auf **Richtlinienverwaltete Apps** oder **keine**, die iOS 9-Funktion, Spotlight-suchen, um Daten in apps suchen können, blockiert werden.|
    |**App Empfang von Daten aus anderen Apps erlauben**|Gibt die Apps an, von denen diese App Daten empfangen kann. Datenübertragung aus beliebigen Apps nicht zulassen können sollen nur die Übertragung von anderen verwalteten apps zulassen oder die Übertragung aus beliebigen Apps zulassen<br /><br />Für iOS-apps, die mehrere Identitäten unterstützen (, in dem Intune verwaltungseinstellungen nur auf Unternehmenskonten oder Daten in der app anwendet) angewendet IPR registrierten Geräten mit einer mobilen Anwendung, wenn ein Benutzer greift auf Daten aus einer Anwendung, die nicht von einer Richtlinie zur mobilen anwendungsverwaltung, die Daten verwaltet wird als Unternehmensdaten behandelt und durch die Richtlinie geschützt.|
    |** "Speichern unter" verhindern**|Deaktiviert die Verwendung der Option **Speichern unter** zum Speichern von Daten an persönlichen Cloudspeicherorten (z. B. OneDrive Personal oder Dropbox) in einer beliebigen App, die dieser Richtlinie unterliegt.|
    |**Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps**|Gibt an, wie Ausschneiden, Kopieren und Einfügen mit der App verwendet werden kann. Wählen Sie aus:<br /><br />**Blockiert** – Ausschneiden, kopieren und Einfügen zwischen dieser app und anderen apps nicht erlauben.<br /><br />**Richtlinienverwaltete Apps** – nur zulassen, Ausschneiden, kopieren und Einfügen zwischen dieser app und anderen verwalteten apps.<br /><br />**Richtlinienverwaltete Apps mit einfügen** – ermöglichen Sie die Daten Ausschneiden oder aus dieser app kopiert werden, nur dann eingefügt werden, in andere apps verwaltete. Einfügen der aus beliebigen Apps ausgeschnittenen oder kopierten Daten in diese App zulassen.<br /><br />**Jede Anwendung** – keine Einschränkungen beim Ausschneiden, kopieren und Einfügen in oder aus dieser app.<br /><br />Zum Kopieren und Einfügen von Daten zwischen verwalteten apps, die apps müssen entweder die **Richtlinienverwaltete Apps** oder **Richtlinienverwaltete Apps mit einfügen** Einstellungen konfiguriert.|
    |**Einfache PIN für Zugriff erforderlich**|Der Benutzer muss eine PIN-Nummer eingeben, um die App zu verwenden. Benutzer werden aufgefordert, diese beim ersten Ausführen der App zu erstellen.|
    |**Anzahl der Versuche vor dem Zurücksetzen der PIN**|Geben Sie die Anzahl der möglichen PIN-Eingabeversuche, bevor der Benutzer die PIN zurücksetzen muss.|
    |**Unternehmensanmeldeinformationen für Zugriff erforderlich**|Erfordert, dass der Benutzer die Unternehmensanmeldeinformationen eingeben muss, bevor er auf die Anwendung zugreifen kann.|
    |**Gerätekonformität mit Unternehmensrichtlinien für Zugriff erforderlich**|Lässt die Verwendung der App nur dann zu, wenn das Gerät nicht per Jailbreak oder Rooting manipuliert wurde.|
    |**Überprüfen der Zugriffsanforderungen nach (Minuten)**|Geben Sie im Feld **Timeout** den Zeitraum ein, bevor die Zugriffsanforderungen für die App nach dem Starten der App erneut geprüft werden müssen.|
    |**Offline-Toleranzperiode**|Wenn das Gerät offline ist, geben Sie den Zeitraum ein, bevor die Zugriffsanforderungen für die App erneut geprüft werden.|
    |**App-Daten verschlüsseln**|Gibt an, dass alle mit dieser App verknüpften Daten verschlüsselt werden, einschließlich extern gespeicherte Daten, z. B. SD-Karten.<br /><br />**Verschlüsselung für iOS**<br /><br />Für apps, die eine Intune mobile Application Management-Richtlinie zugeordnet sind, werden die Daten im Ruhezustand mit Verschlüsselung auf Geräteebene vom Betriebssystem bereitgestellter verschlüsselt. Dies wird durch die Geräte-PIN-Richtlinie aktiviert, die vom IT-Administrator festgelegt werden muss. Wenn eine PIN erforderlich ist, werden die Daten gemäß den Einstellungen in der mobilen Anwendungsverwaltungsrichtlinie verschlüsselt. Wie in der Apple-Dokumentation angegeben, [sind die von iOS 7 verwendeten Module FIPS 140-2-zertifiziert](http://support.apple.com/en-us/HT202739).<br /><br />**Verschlüsselung für Android**<br /><br />Für apps, die eine Intune mobile Application Management-Richtlinie zugeordnet sind, wird die Verschlüsselung von Microsoft bereitgestellt. Daten werden während der E/A-Dateivorgänge gemäß der Einstellung in der mobilen Anwendungsverwaltungsrichtlinie synchron verschlüsselt. Verwaltete Apps auf Android verwenden AES-128-Verschlüsselung im CBC-Modus mit den Plattform-Kryptografie-Bibliotheken. Die Verschlüsselungsmethode ist nicht FIPS 140-2-zertifiziert. Inhalt auf dem Speicher des Geräts wird immer verschlüsselt.|
    |**Blockieren von Bildschirmaufnahmen** (nur Android-Geräte)|Gibt an, dass die Screen Capture-Funktionen des Geräts blockiert werden, wenn Sie diese App verwenden.|

4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## **Schritt 4:** Verknüpfen Sie die App mit einer Verwaltungsrichtlinie für mobile Anwendungen, und stellen Sie dann die App bereit.
Wenn Sie die App bereitstellen, wählen Sie die Verwaltungsrichtlinie für mobile Anwendungen auf der Seite **Mobile App-Verwaltung** aus, um die App mit der Richtlinie zu verknüpfen.

Weitere Informationen finden Sie unter [Bereitstellen von apps für mobile Geräte in Microsoft Intune - gelöscht](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md).

> [!IMPORTANT]
> Für Geräte, die ältere Betriebssysteme als iOS 7.1 ausführen, werden verknüpfte Richtlinien nicht entfernt, wenn die App deinstalliert wird.
> 
> Wenn das Gerät von Intune abgemeldet wird, Richtlinien werden nicht aus den apps entfernt; Alle apps, die Richtlinien angewendet waren, behält die Richtlinien, auch nachdem die app deinstalliert und neu installiert wird.

### Maßnahmen, wenn eine App bereits auf Geräten bereitgestellt wurde
Es kann die Situation eintreten, dass Sie eine App bereitstellen und von einem der Benutzer oder auf einem der Geräte bereits eine nicht verwaltete Version der App installiert wurde. Beispiel: Ein Benutzer hat Microsoft Word über den App-Store installiert.

In diesem Fall müssen Sie den Benutzer bitten, die nicht verwaltete Version manuell zu deinstallieren, damit die von Ihnen konfigurierte verwaltete Version installiert werden kann.

Allerdings für Geräte unter iOS 9, und Intune wird später automatisch beim Benutzer die Berechtigung zur Verwaltung der vorhandenen App übernehmen. Wenn sie zustimmen, wird die app von Intune verwaltet werden, und alle Richtlinien zur mobilen anwendungsverwaltung, die Sie mit der Anwendung verknüpft werden auch angewendet werden.

> [!TIP]
> Wenn das Gerät im überwachten Modus befindet, Intune über die Verwaltung der vorhandenen App gelangen Benutzer Rückfrage.

## **Schritt 5:** Überwachen Sie die App-Bereitstellung.
Nachdem Sie eine mit einer Verwaltungsrichtlinie für mobile Anwendungen verknüpfte App erstellt und bereitgestellt haben, verwenden Sie das folgende Verfahren, um die App zu überwachen und alle Richtlinienkonflikte zu lösen.

#### Anzeigen des Status der Bereitstellung

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com)auf **Gruppen** &gt; **Übersicht**.

2.  Führen Sie einen der folgenden Schritte aus:

    -   Klicken Sie auf **alle Benutzer**, und doppelklicken Sie auf den Benutzer, dessen Geräte Sie überprüfen möchten. Einer der **Benutzereigenschaften** auf **Geräte**, doppelklicken Sie dann auf das Gerät, das Sie untersuchen möchten.

    -   Klicken Sie auf **Alle Geräte** &gt; **Alle mobilen Geräte**. Auf der **Gerät Gruppeneigenschaften** auf **Geräte**, doppelklicken Sie dann auf das Gerät, das Sie untersuchen möchten.

3.  Klicken Sie auf der Seite **Eigenschaften für mobile Geräte** auf **Richtlinie** , um eine Liste der Verwaltungsrichtlinien für mobile Anwendungen anzuzeigen, die auf dem Gerät bereitgestellt wurden.

4.  Wählen Sie die Verwaltungsrichtlinie für mobile Anwendungen aus, deren Status Sie anzeigen möchten. Sie können die Details der Richtlinie im unteren Bereich anzeigen und den Knoten erweitern, um ihre Einstellungen anzuzeigen.

5.  Unter der Spalte **Status** jeder Verwaltungsrichtlinie für mobile Anwendungen wird **Konform**, **Konform (Ausstehend)**oder **Fehler** angezeigt. Besteht in der ausgewählten Richtlinie für eine oder mehrere Einstellungen ein Konflikt, wird **Fehler** in diesem Feld angezeigt.

6.  Nachdem Sie einen Konflikt ermittelt haben, können Sie in Konflikt stehende Richtlinieneinstellungen überarbeiten, sodass sie die dieselbe Einstellung verwenden, oder nur eine Richtlinie für die App und die Benutzer bereitstellen.

### <a name="BKMK_Conf"></a>Wie Richtlinienkonflikte gelöst werden
Wenn bei einer Verwaltungsrichtlinie für mobile Anwendungen bei der ersten Bereitstellung für den Benutzer oder das Gerät ein Konflikt auftritt, wird der jeweilige in Konflikt stehende Einstellungswert aus der Richtlinie für die App entfernt, und die App verwendet einen vorgegebenen Konfliktwert.

Wenn bei einer späteren Bereitstellung ein Konflikt in der Verwaltungsrichtlinie für mobile Anwendungen für den Benutzer oder das Gerät auftritt, wird der jeweilige in Konflikt stehende Einstellungswert nicht in der Richtlinie für die App aktualisiert, und die App verwendet den vorhandenen Wert für diese Einstellung.

In Fällen, in denen das Gerät oder der Benutzer zwei in Konflikt stehende Richtlinien erhält, gilt Folgendes:

-   Wenn bereits eine Richtlinie mit dem Gerät bereitgestellt wurde, werden die vorhandenen Richtlinieneinstellungen nicht überschrieben.

-   Wenn keine Richtlinie für das Gerät bereitgestellt wurde und zwei widersprüchliche Einstellungen bereitgestellt werden, wird die in das Gerät integrierte Standardeinstellung verwendet.

### Siehe auch
[Schützen von Daten und Geräten mit Microsoft Intune](protect-data-and-devices-with-microsoft-intune.md)
[Bereitstellen und Konfigurieren von Apps mit Microsoft Intune](deploy-and-configure-apps-with-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


