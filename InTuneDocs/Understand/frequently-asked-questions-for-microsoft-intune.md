---
# required metadata

title: Häufig gestellte Fragen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Häufig gestellte Fragen zu Intune
In diesem Artikel werden einige häufig gestellte Fragen zu Intune behandelt. Wenn Sie hier keine Antwort auf Ihre Frage finden, [teilen Sie es uns mit](https://microsoftintune.uservoice.com/).

## Allgemeine Probleme

-   **Wie kann ich feststellen, ob der Microsoft Intune-Dienst aktualisiert wurde?**

    Melden Sie sich bei Ihrem Konto bei „manage.microsoft.com“ an. Wählen Sie in der Verwaltungsübersicht **Dienststatus anzeigen** aus. Dort werden der Speicherort Ihres Mandanten und der Zeitplan für die Datenbankwartung aufgeführt. Informationen über Dienstupdates finden Sie im Artikel [Neues](/intune/deploy-use/whats-new-in-microsoft-intune).

-   **Wenn ein Benutzer ein Gerät innerhalb der Unternehmensportal-App umbenennt, wird dadurch auch der Name in Intune oder im Konfigurations-Manager geändert?**

    Nein, diese Namensänderung dient nur zur Vereinfachung für den Benutzer.

-   **Gibt es eine Funktion zur Remoteunterstützung für mobile Geräte in Intune?**

    Nein, gibt es nicht. Hier können unter Umständen aber Apps von Drittanbietern, wie [Bomgar](http://www.bomgar.com/) und [TeamViewer](https://www.teamviewer.com/), nützlich sein.

## Konten

-   **Wenn ich Intune teste und einen neuen Mandanten für die Testversion erstelle, kann ich Office 365 mit dem gleichen Mandanten zur Evaluierung hinzufügen?**

    Ja. Melden Sie sich mithilfe eines globalen Administrators in Ihrem vorhandenen Intune-Mandanten/-Abonnement an, wie z. B. *globaleradmin@&lt;Unternehmen&gt;.onmicrosoft.com*..

-   **Wenn ich Intune während eines Testabonnements MDM-Autorität zuweise, erschwert das den Wechsel zum Dienst eines anderen Unternehmens, falls ich meine Meinung zu Intune ändere?**

    Auch wenn Sie diese Entscheidung bezüglich Intune treffen sollten, wirkt sich die Wahl der MDM-Autorität nicht auf einen Wechsel zu einem anderen Dienst aus. Dies ist eine spezielle Option von Intune oder Intune mit System Center Configuration Manager.

-   **Kann ich meinen vorhandenen Office 365-Domänennamen für mein nachfolgendes Intune-Konto verwenden?**

    Ja, wenn Sie sich mit der Organisations-ID anmelden, die Ihrem vorhandenen Office 365-Mandanten und der überprüften Domäne beim Erstellen der Intune-Testversion oder beim Aktivieren der Lizenzen zugeordnet wurde.

    Intune verwendet dann die gleichen Domänen, Benutzer usw. wie für das Office 365-Konto. Beachten Sie, dass jeder Office 365-Benutzer als Intune-Benutzer mit einer Intune-Lizenz aktiviert werden muss. Dies müsste vom globalen Administrator ausgeführt werden, der den Mandanten verwaltet.

## Anmeldung

-   **Wo können Benutzer erfahren, wie sie ihre Geräte registrieren?**

    Sie können dazu die Informationen aus den [Intune-Endbenutzer-Registrierungsanweisungen für IT-Administratoren](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) (End-user Intune enrollment instructions for IT administrators) verwenden oder anpassen..

-   **Wie behebe ich Fehler bei der Geräteregistrierung?**

    Methoden zur Behandlung allgemeiner Probleme bei der Registrierung finden Sie unter [Behandlung von Problemen bei der Geräteregistrierung bei Intune](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune)..

-   **Wie kann ich Registrierungsprotokolle erfassen, wenn bei einem Benutzer Registrierungsprobleme auftreten?**

    Befolgen Sie [diese Anweisungen](http://www.microsoft.com/en-us/download/46391)..

## Verwaltung mobiler Geräte

-   **MDM – allgemein**

    -   **Kann Intune Geräte mit Jailbreak erkennen?**

        Ja, bei einigen Betriebssystemen. Informationen zum Verwalten von Geräten, die mittels eines Jailbreaks manipuliert wurden, finden Sie unter [Erstellen einer Geräte-Kompatibilitätsrichtlinie](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md) (Create a device compliance policy)..

    -   **Kann ich Unternehmensdaten von einem Gerät selektiv zurücksetzen?**

        Ja. Informationen zum selektiven Zurücksetzen finden Sie unter [Schützen Ihrer Daten mit Remotezurücksetzen, Remotesperre und Kennungszurücksetzung](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md) (Help protect your data with remote wipe, remote lock, or passcode reset)..

    -   **Gibt es eine Möglichkeit zum Blockieren bestimmter Websites auf dem mobilen Gerätebrowser über Intune?**

        Nicht in den systemeigenen Browsern aller Plattformen. Sie können URLs jedoch zulassen oder blockieren, wenn Sie den über Intune verwalteten Webbrowser auf iOS- und Android-Geräten bereitgestellt haben. Weitere Informationen finden Sie unter [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md) (Manage Internet access using managed browser policies)..

    -   **Können wir verhindern, dass ein Benutzer eine App deinstalliert?**

        Im Allgemeinen nicht. Allerdings können Sie auf einem überwachten iOS-Gerät verhindern, dass ein Benutzer eine App deinstalliert, die mithilfe von Apple Configurator verteilt wurde. 

    -   **Gibt es eine Möglichkeit zum Verwalten der mobilen Datennutzung?**

        Nicht direkt, Sie können jedoch sicherstellen, dass WLAN die bevorzugte Methode zum Herstellen einer Verbindung ist, indem Sie WLAN-Profile auf die Geräte übertragen, wie unter [Benutzern mithilfe von WLAN-Profilen die Verbindung mit Unternehmensnetzwerken erleichtern](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md) (Help users connect to company networks using Wi-Fi profiles) beschrieben. Zudem ermöglichen einige Plattformen (z. B. iOS und Android KNOX) die Steuerung von Einstellungen wie Sprach- und Datenroaming.

    -   **Gibt es eine Möglichkeit, zu verhindern, dass ein Benutzer die Registrierung eines Geräts aufhebt? Wie sieht dies bei einem Gerät in Unternehmensbesitz aus?**

        In der Regel nicht. Allerdings können Sie die Aufhebung der Registrierung unter Windows Phone 8.1 mithilfe von benutzerdefinierten Windows Phone-Einstellungen verhindern. Darüber hinaus kann bei iOS-Geräten, die überwacht und im Registrierungsprogramm für Apple-Geräte (DEP) registriert werden, verhindert werden, dass ein Benutzer eine Geräteregistrierung aufhebt.

    -   **Kann ich die gewählte MDM-Autorität wechseln?**

        In einigen Situationen können Sie die MDM-Autorität wechseln. Wenden Sie sich dazu an den Support, wie unter [Anfordern von Support für Microsoft Intune](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md) beschrieben. In der folgenden Tabelle wird beschrieben, welche Änderungen möglich sind. Eine Änderung der MDM-Autorität erfordert die erneute Registrierung der Geräte.

        ||**An:** Intune!**An:** O365|**An:** Configuration Manager with Intune|
        |**Von:** Intune| |Ja&#42;|Ja|
        |**Von:** O365||Ja&#42;||Ja|
        |**Von:** Configuration Manager mit Intune|Ja|Ja| |
        
        &#42;O365- und Intune-MDM-Autoritäten können gleichzeitig verwendet werden, Sie müssen mobile Geräte also nicht erneut anmelden.



-   **Windows**

    -   **Kann ich eine Windows Store-App per Sideload auf ein Gerät übertragen?**

        Öffentlich verfügbare Apps können nicht per Sideload übertragen werden. Obwohl Sie die XAP herunterladen können, kann sie nicht in Intune hochgeladen werden, da es sich um eine öffentliche XAP handelt, die verschlüsselt und mit dem Codesignaturzertifikat des Entwicklers signiert wurde. Sie können nur Apps per Sideload übertragen, die Sie entwickeln und mit Ihrem eigenen Codesignaturzertifikat signieren.

    -   **Erfordern Windows Phone Store-Apps, die über das Unternehmensportal verteilt werden, dass der Endbenutzer ein Microsoft-Konto hat?**

        Ja, der Endbenutzer kann die Apps nicht ohne Microsoft-Konto abrufen. Ausgenommen davon sind private LOB-Apps, die per Sideload übertragen werden und auf einem Gerät ohne Microsoft-Konto bereitgestellt werden können.

    -   **Ist ein Microsoft-Konto auf einem Windows Phone 8.1 erforderlich, damit es mit Intune verwaltet werden kann?**

        Nein. Allerdings ist es erforderlich, um die meisten Apps aus dem öffentlichen Store zu installieren.

        **Warum erfordert Windows Phone ein Symantec-Zertifikat für die Verwaltung?**
        Windows Phone steuert, wie Sie Apps installieren können. Jeder Benutzer mit einem Microsoft-Konto kann Apps aus dem Windows Phone Store installieren. Unternehmen können ihre intern entwickelten Branchen-Apps über einen besonderen Prozess installieren oder per Sideload-Verfahren übertragen, das in der Windows Phone-Dokumentation beschrieben wird. Bei der Installation von Branchenanwendungen unterstützen Windows Phones nur eine spezielle Art von Symantec-Zertifikat. Sie können keine anderen gewerblich oder privat generiertes Zertifikat verwenden. Diese Anforderung gilt für alle Mobilgeräteverwaltungslösungen, nicht nur Intune.

        Das Symantec-Zertifikat erstellt ein Anwendungsregistrierungs-Token (AET). Das AET kann auf einem Gerät installiert werden, wenn das Gerät sich für die Verwaltung mobiler Geräte registriert, oder es kann Out-of-Band von einer sicheren Website oder aus einen E-Mail-Anhang installiert werden. Administratoren müssen alle Branchen-Apps mit dem Symantec-Zertifikat signieren, mit den Tools aus dem [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439). Wenn Benutzer versuchen, Branchen-Apps zu installieren, vergleicht das Windows Phone-Betriebssystem die Signatur im AET mit der Signatur der App. Wenn die Signaturen übereinstimmen, kann die Installation fortgesetzt werden. Wenn das AET nicht überprüft werden kann, schlägt die Installation fehl. Es gibt verschiedene Gründe dafür, dass das AET nicht überprüft werden kann:

        -   Das AET wurde nie auf dem Gerät installiert.

        -   Das AET ist abgelaufen.

        -   Das AET wurde nicht mit demselben Symantec-Zertifikat erstellt, das zum Signieren der App verwendet wurde.

        Windows Phone erfordert nicht, dass das AET während der MDM-Registrierung vorhanden ist. Vor der November 2014-Version erforderte Intune jedoch das AET und eine signierte ssp.xap, da es keine andere Möglichkeit zum Installieren des AET und der ssp.xap außer während der Registrierung gab.

    **Wie wird das AET für Intune Benutzer erstellt?**
  Wenn Administratoren die .pfx-Datei für ihr Symantec-Zertifikat hochladen, erstellt Intune das AET automatisch und stellt es auf registrierten Windows Phones bereit. Es ist nicht erforderlich, dass Intune-Administratoren das AET Generator-Tool aus dem Windows Phone SDK verwenden.

      > [!IMPORTANT]
        > Intune unterstützt nicht die manuelle Erstellung des AET und seine Out-of-Band-Bereitstellung.

    **Welche Änderungen haben dazu geführt, dass nicht unbedingt ein Symantec-Zertifikat erforderlich ist?**
       Für die November 2014-Version wurden Änderungen an Intune vorgenommen, um Szenarios zuzulassen, in denen Unternehmen nicht über ein Symantec-Zertifikat verfügen.

       -   Das Unternehmensportal für Windows Phone 8.1 kann aus dem Store installiert werden. D. h. es muss nicht mit einem Symantec-Zertifikat signiert sein und mit einem AET validiert werden. Stattdessen wird die App als Teil des Store-Veröffentlichungsprozesses validiert.

        -   Windows Phone 8.1-Geräte können sich mit oder ohne einen AET auf dem Telefon registrieren. Wenn ein AET verfügbar ist, wird er zum ersten Mal installiert, wenn das Gerät mit Intune synchronisiert wird. Wenn kein AET vorhanden ist, kann das Gerät weiterhin von Intune verwaltet werden. Benutzer können das Unternehmensportal aus dem Store installieren und die meisten Funktionen des Unternehmensportals ohne ein Symantec-Zertifikat zum Signieren von Apps verwenden.

        Die Symantec-Anforderung für Windows Phone 8-Geräte besteht weiterhin. Für Windows Phone 8-Geräte müssen die signierte ssp.xap und das AET während der Registrierung vorhanden sein. Andernfalls werden sie für die Registrierung blockiert.

        **Welche Funktionen werden unterstützt, wenn ein Windows Phone 8.1-Gerät registriert wird, aber kein Symantec-Zertifikat vorhanden ist?**
        Wenn ein Windows Phone 8.1-Gerät registriert wird, aber kein Symantec-Zertifikat vorhanden ist, können Sie:

        -   Richtlinien erstellen und sie an das Gerät weiterleiten

        -   Kontaktinformationen für die IT-Abteilung konfigurieren, die im Unternehmensportal anzeigt werden

        -   Deep Links im Speicher erstellen und für das Unternehmensportal bereitstellen

        -   Links zu Webseiten erstellen und für das Unternehmensportal bereitstellen

        -   Bedingungen erstellen, die von Benutzern akzeptiert werden müssen, bevor das Unternehmensportal verwendet werden kann

        Das Einzige, was ohne ein Symantec-Zertifikat nicht möglich ist, ist Branchen-Apps bereitzustellen.

        > [!IMPORTANT]
        > Der Intune Software Publisher überprüft nicht, ob Apps signiert sind, wenn Sie sie hochladen. Wenn Sie nicht signierte Apps bereitstellen, schlagen sie fehl, wenn Benutzer versuchen, diese zu installieren.

        **Was können Benutzer tun, wenn sie ein Unternehmensportal haben, jedoch kein Symantec-Zertifikat?**
        Windows Phone 8.1-Geräte müssen nicht registriert werden, bevor Benutzer das Unternehmensportal aus dem Store installieren. Wenn das Gerät nicht registriert ist, werden Benutzer aufgefordert, es zu registrieren. Durch Berühren der Eingabeaufforderung im Unternehmensportal gelangen Benutzer direkt zu **Einstellungen/Arbeitsplatz**, wo sie ihre Geräte registrieren können.

        Benutzer können selbst ohne Registrierung des Geräts die folgenden Aktionen im Unternehmensportal durchführen, das aus dem Store installiert wurde:

        -   Akzeptieren Sie die Bedingungen, die vom Administrator konfiguriert wurden, oder lehnen Sie sie ab. Wenn Benutzer die Bedingungen ablehnen, wird das Unternehmensportal geschlossen.

        -   Kontaktinformationen für die IT-Abteilung anzeigen

        -   Alle registrierten Geräte anzeigen, einschließlich iOS-, Android- und Windows-Geräte

        -   Deep Links zu Apps im Store verwenden

        -   Weblinks verwenden, um Webseiten zu öffnen

        Wenn das Gerät registriert ist, können Benutzer das Gerät in der Liste **Meine Geräte** anzeigen. Nach der Registrierung unterliegt das Gerät allen bereitgestellten Intune-Richtlinien. Geräte müssen registriert werden, um das AET zu erhalten und Branchen-Apps zu installieren. Ein nicht registriertes Gerät, das versucht, eine Branchen-App zu installieren, wird zur Registrierung weitergeleitet.

        Das Einzige, was Benutzer nicht tun können, wenn das Unternehmen nicht über ein Symantec-Zertifikat verfügt, ist, vom Administrator bereitgestellt Branchen-Apps zu installieren.

        **Unser Unternehmen verfügt bereits über ein Zertifikat und hat Windows Phone 8.1-Geräte registriert. Muss ich zusätzlich etwas tun, da das Unternehmensportal jetzt im Store verfügbar ist?**
        Die aktuelle ssp.xap aus dem Download Center funktioniert weiterhin auf Windows Phone 8.1-Geräten. Sie können weiterhin Benutzer weiterleiten, um sich zu registrieren und das Unternehmensportal während der Installation abzurufen.

        **Was sind die Vor- und Nachteile, wenn Benutzer das Unternehmensportal aus dem Store abrufen?**
        Vorteile:

        -   Benutzer erhalten Deep Links und Weblinks, selbst wenn das Windows Phone 8.1-Gerät nicht registriert ist.

        -   Wenn Microsoft das Unternehmensportal aktualisiert, wird die Store-App automatisch ohne Herunterladen, Signieren und erneutes Bereitstellen der ssp.xap aktualisiert.

        -   Die Dokumentation für Windows Phone 8.1-, iOS-, Android- und Windows-Benutzer ist konsistent: „Wechseln Sie zum Store, und installieren Sie das Unternehmensportal.“

        -   Benutzer sehen die App während sie Installiert wird und erhalten Registrierungsanweisungen, wenn sie geöffnet wird.

        Nachteile:

        -   Benutzer sehen ein Kontrollkästchen zum Installieren eines**Unternehmens-Hub**. Sie werden jedoch nicht zum Unternehmensportal in der App-Liste des Geräts weitergeleitet.

        -   Benutzer müssen keine benutzerdefinierten Bedingungen akzeptieren, bis sie das Unternehmensportal öffnen.

        In den folgenden Situationen können Sie weiterhin Benutzer zur Registrierung und Installation der ssp.xap bei der Registrierung weiterleiten:

        -   Wenn die Unternehmensblöcke auf den Store von Windows Phones zugreifen, müssen Benutzer die ssp.xap abrufen, die bei der Registrierung installiert wird.

        -   Wenn Benutzer keine Microsoft-Konten auf ihren Windows Phones konfiguriert haben, können sie nicht das Unternehmensportal aus dem Store installieren.

        -   Wenn in der vorhandenen Dokumentation für die Windows Phone-Registrierung steht, dass der Benutzer zunächst zu "Einstellungen" > "Arbeitsplatz" gehen soll, kann es dauern, bis die Dokumentation aktualisiert wird und die Benutzer zum Store weitergeleitet werden.

        **Was ist der Unterschied zwischen de ssp.xap im Download Center und der App im Store?**

        -   Das Unternehmensportal im Store muss nicht durch ein zu installierendes Symantec-Zertifikat signiert werden.

        -   Das Unternehmensportal im Store stellt dem Benutzer die Bedingungen bereit, die ssp.xap im Download Center nicht.

        -   Das Unternehmensportal im Speicher ist eine .appx und keine .xap.

        **Kann ich die Unternehmensportaldatei abrufen und sie an meine Benutzer weiterleiten, statt sie auf den Store zu verweisen?**
        Ja. Die Unternehmensportal-App kann für die folgenden Betriebssysteme aus dem Download Center heruntergeladen werden:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Können Unternehmen weiterhin das Support Tool for Windows Intune Trial Management of Windows Phone verwenden, wenn sie nicht über ein Symantec-Zertifikat verfügen, und müssen Benutzer weiterhin das Unternehmensportal aus dem Store installieren?**
        Ja. Wenn Sie eine Machbarkeitsstudie durchführen müssen, die die Installation von Branchen-Apps beinhaltet, nutzt das Trial Management Tool die Store-Version des Unternehmensportals. Da das AET aus dem Symantec-Zertifikat nicht mehr erforderlich ist, um Windows Phone 8.1-Geräte zu registrieren, können Unternehmen jedoch die App-Installation mit Deep Links zu Apps im Store testen.

        Das Support Tool for Windows Intune Trial Management of Windows Phone ist nur für Testabonnements von Intune verfügbar.

        > [!IMPORTANT]
        > Verwenden Sie nur die Trial Management Tool-Tests. Für mit dem AET aus dem Trial Management Tool registrierte Geräte müssen Sie die Registrierung aufheben und sie erneut registrieren, wenn das Symantec-Zertifikat für das Trial Management Tool nicht mehr verfügbar ist oder wenn das Unternehmen ein eigenes Symantec-Zertifikat für das Signieren von Apps erhält.

        **Können Unternehmen ohne ein Symantec-Zertifikat beginnen und es später hinzufügen, selbst nachdem Windows Phone 8.1-Geräte registriert wurden?**
        Ja. Selbst wenn Windows Phone 8.1-Geräte bereits registriert wurden, können Sie ein Symantec-Zertifikat erhalten, die ssp.xap signieren, sie und die pfx-Datei hochladen. Intune generiert dann das AET. Windows Phone 8.1-Geräte erhalten das AET bei der nächsten Synchronisierung, bis zu acht Stunden. Stellen Sie Branchen-Apps erst acht Stunden nach dem Hochladen der xap und pfx bereit.


-   **Android**

    -   **Wie lange dauert es, ein Android-Gerät zu verschlüsseln?**

        Dies hängt in erster Linie von der Geschwindigkeit des Geräteprozessors und der Menge des gesamten und genutzten Arbeitsspeichers ab, da es keine Funktion von Intune ist.

-   **iOS**

    -   **Benötigt das Gerät eine Apple-ID-Angabe, um die Installation fortzusetzen, wenn bei der Bereitstellung von iOS-Apps mit Intune die IPA- und Manifest-Datei der Anwendung hochgeladen wurde?**

        Nein. Wenn Intune die Bits bereitstellt (IPA wurde in Intune hochgeladen), werden die Anwendungen per Sideload übertragen und benötigen keine Apple-ID.

    -   **Gibt es eine Möglichkeit, Apps auf iOS zu installieren, ohne Zugriff auf den Apple Store zu gewähren?**

        Nein, Sie können jedoch den App Store aktivieren und zugelassene bzw. blockierte Apps auf iOS verwenden, um Benutzeraktionen zu überwachen. Per Sideload übertragene LOB-Apps erfordern keinen Zugriff auf den Apple App Store.

    -   **Erfordern Apple Store-Apps, die über das Unternehmensportal verteilt werden, dass der Endbenutzer über ein iTunes-Konto verfügt?**

        Ja, der Endbenutzer kann die Apps nur mit einem iTunes-Konto abrufen.

    -   **Kann ich den App Store blockieren?**

        Ja, dadurch werden jedoch alle App-Installationen und Updates aus dem App Store blockiert, nicht nur die vom Benutzer initiierten. Dies bedeutet, dass bei allen öffentlichen App Store-Apps, die Sie über Intune bereitstellen, ebenfalls ein Fehler auftritt.

## Anwendungsbereitstellung

-   **Wie kann ich eine empfohlene App hinzufügen?**

    In Intune sind diese unter „Empfohlene Apps“ aufgeführt, und die diesbezügliche Dokumentation finden Sie unter [Bereitstellen von Apps in Microsoft Intune](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md)..

-   **Kann ich zusätzlichen Cloudspeicher für Apps erhalten, die bereitgestellt werden sollen?**

    Ja. Weitere Informationen hierzu finden Sie unter [Bereitstellen von Apps](/Intune/Deploy-Use/deploy-apps.md) im Abschnitt *Cloudspeicheranforderungen*..

## Sicherheit

-   **Kann BitLocker-Schutz von Intune erzwungen werden?**

    Der OMA-DM-Agent von Windows 8.1/RT ermöglicht das Lesen (Abrufen) des Verschlüsselungsstatus. Dies kann nicht festgelegt werden. Dies gilt für Intune und andere Verwaltungsdienste für mobile Geräte.

-   **Kann ich bei einem Windows 8-Tablet mit BitLocker-Verschlüsselung ein vollständiges Zurücksetzen des Geräts erzwingen, wenn eine Benutzeranmeldung mehrmals hintereinander fehlschlägt?**

    Kein Verwaltungsdienst für mobile Geräte, einschließlich Intune, bietet eine Option zum vollständigen Zurücksetzen von Geräten mit Windows 8.1/RT. Intune bietet für diese Geräte selektives Zurücksetzen. Weitere Informationen zum Zurücksetzen/selektiven Zurücksetzen in Intune finden Sie unter [Schützen von Apps und Daten mit Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md) (Protect apps and data with Microsoft Intune)..

## Unternehmensportal

-   **Kann ich das Unternehmensportal anpassen?**

    Ja. Wechseln Sie für diese Einstellungen in der Intune-Administratorkonsole zu **Admin&gt;Unternehmensportal**.

## Microsoft Intune mit Configuration Manager

-   **Über welche Konsole verwalte ich meine Geräte, wenn ich Configuration Manager mit Intune verwende?**

    Verwalten Sie all Ihre Geräte selbst dann über die Configuration Manager-Konsole, wenn Geräte mit Intune-Agent in der Intune-Konsole angezeigt werden. Mobile Geräte werden nicht in der Intune-Konsole angezeigt.

-   **Kann ich selektives Zurücksetzen auf Geräten ausführen?**

    Wenn Sie System Center 2012 R2 Configuration Manager oder höher mit Intune verwenden, können Sie Unternehmensdaten per selektivem Zurücksetzen entfernen. Weitere Informationen finden Sie unter [Schützen von Apps und Daten mit Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md) (Protect apps and data with Microsoft Intune)..

-   **Wenn ich Configuration Manager mit Intune verwende, kann ich trotzdem das Intune-Verwaltungsportal weiterhin verwenden?**

    Ja, jedoch können Sie nur Computer mit installiertem Intune-Agent über dieses Portal verwalten. Das Portal bietet einige nützliche Informationen zu Dienstbenachrichtigungen, zum Dienststatus usw. Die Geräteverwaltungseinstellungen dort werden jedoch nicht auf registrierte Geräte angewendet.



<!--HONumber=May16_HO1-->


