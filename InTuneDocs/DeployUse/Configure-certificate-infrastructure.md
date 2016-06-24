---
# required metadata

title: Konfigurieren der Zertifikatinfrastruktur | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurieren der Zertifikatinfrastruktur
In diesem Thema werden die Anforderungen beschrieben, die zum Erstellen und Bereitstellen von Zertifikatprofilen erforderlich sind.

Für jede zertifikatbasierte Authentifizierung im Unternehmen benötigen Sie eine Unternehmenszertifizierungsstelle.

Damit Sie SCEP-Zertifikatprofile verwenden können, benötigen Sie zusätzlich zur Unternehmenszertifizierungsstelle auch Folgendes:

-   einen Server, der den Registrierungsdienst für Netzwerkgeräte ausführt,

-   den Intune Certificate Connector, der auf dem Windows Server 2012 R2-Server installiert wird, auf dem NDES ausgeführt wird.

Damit Sie PFX-Zertifikatprofile verwenden können, benötigen Sie zusätzlich zur Unternehmenszertifizierungsstelle auch Folgendes:

-  einen Computer, der mit der Zertifizierungsstelle kommunizieren oder den Computer der Zertifizierungsstelle selbst verwenden werden kann,

-  den Intune Certificate Connector, der auf dem Computer ausgeführt wird, der mit der Zertifizierungsstelle kommunizieren kann.

## Lokale Infrastruktur


-    **Active Directory-Domäne**: Alle in diesem Abschnitt aufgeführten Server (außer dem Webanwendungsproxy-Server) müssen der Active Directory-Domäne angehören.

-  **Zertifizierungsstelle** (Certification Authority, CA): Eine Unternehmenszertifizierungsstelle, die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. Anleitungen zum Einrichten einer Zertifizierungsstelle finden Sie unter [Installieren der Zertifizierungsstelle](http://technet.microsoft.com/library/jj125375.aspx).
    Wenn die Zertifizierungsstelle unter Windows Server 2008 R2 ausgeführt wird, müssen Sie [den Hotfix von KB2483564 installieren](http://support.microsoft.com/kb/2483564/).

-  **NDES Server** (nur SCEP): Auf einem Server mit Windows Server 2012 R2 oder höher müssen Sie den Registrierungsdienst für Netzwerkgeräte (Network Device Enrollment Service, NDES) einrichten. Intune unterstützt die Verwendung von NDES nicht, wenn es auf einem Server ausgeführt wird, der auch die Unternehmenszertifizierungsstelle ausführt. Im [Leitfaden für den Registrierungsdienst für Netzwerkgeräte](http://technet.microsoft.com/library/hh831498.aspx) finden Sie Anweisungen zum Konfigurieren von Windows Server 2012 R2 als Host für den Registrierungsdienst für Netzwerkgeräte.
-  **Computer, der mit der Zertifizierungsstelle kommunizieren kann** (nur PFX). Verwenden Sie alternativ den Computer der Zertifizierungsstelle selbst.
-  **Microsoft Intune Certificate Connector**: Sie verwenden die Intune-Verwaltungskonsole zum Herunterladen des Installationsprogramms für den **Certificate Connector** (**ndesconnectorssetup.exe**). Führen Sie **ndesconnectorssetup.exe** dann auf dem Computer aus, auf dem Sie den Certificate Connector installieren möchten. Installieren Sie für PFX-Zertifikatprofile den Certificate Connector auf dem Computer, der mit der Zertifizierungsstelle kommuniziert.
-  **Webanwendungsproxy-Server** (optional): Sie können einen Server mit Windows Server 2012 R2 oder höher als Webanwendungsproxy-Server (WAP) verwenden. Diese Konfiguration:
    -  ermöglicht Geräten das Empfangen von Zertifikaten über eine Internetverbindung,
    -  ist eine Sicherheitsempfehlung, wenn Geräte eine Verbindung über das Internet herstellen, um Zertifikate zu empfangen oder zu erneuern.

> [!NOTE]           
> -    Auf dem Server, der den WAP hostet, [muss ein Update installiert werden](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) , das die Unterstützung für lange URLs aktiviert, die vom Registrierungsdienst für Netzwerkgeräte verwendet werden. Dieses Update ist im [Updaterollup vom Dezember 2014](http://support.microsoft.com/kb/3013769)enthalten oder kann auch einzeln von [KB3011135](http://support.microsoft.com/kb/3011135)heruntergeladen werden.
>-  Zudem muss der Server, der WAP hostet, über ein SSL-Zertifikat verfügen, das mit dem Namen übereinstimmt, der für externe Clients veröffentlicht wird. Ferner muss der Server dem SSL-Zertifikat vertrauen, das auf dem NDES-Server verwendet wird. Diese Zertifikate ermöglichen dem WAP-Server, die SSL-Verbindung von Clients zu beenden und eine neue SSL-Verbindung mit dem NDES-Server herzustellen.
Weitere Informationen über Zertifikate für WAP finden Sie im Abschnitt **Planen von Zertifikaten** des Themas [Installieren und Konfigurieren des Webanwendungsproxys für die Veröffentlichung interner Anwendungen](https://technet.microsoft.com/library/dn383650.aspx). Allgemeine Informationen zu WAP-Servern finden Sie unter [Verwenden des Webanwendungsproxys](http://technet.microsoft.com/library/dn584113.aspx).


### Zertifikate und Vorlagen

|Objekt|Details|
|----------|-----------|
|**Zertifikatvorlage**|Sie konfigurieren diese Vorlage auf der ausstellenden Zertifizierungsstelle.|
|**Clientauthentifizierungszertifikat**|Dieses Zertifikat, das von der ausstellenden oder öffentlichen Zertifizierungsstelle angefordert wurde, installieren Sie auf dem NDES-Server.|
|**Serverauthentifizierungszertifikat**|Dieses SSL-Zertifikat, das von der ausstellenden Zertifizierungsstelle oder öffentlichen Zertifizierungsstelle angefordert wurde, installieren und binden Sie in IIS auf dem NDES-Server.|
|**Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle**|Sie exportieren dies als eine **CER** -Datei von der ausstellenden Zertifizierungsstelle oder von Geräten, die der ausstellenden Zertifizierungsstelle vertrauen, und stellen es mit dem Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle für Geräte bereit.<br /><br />Sie verwenden für jede Betriebssystemplattform ein einzelnes Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ordnen es dem jeweiligen vertrauenswürdigen Stammzertifikatprofil zu, das Sie erstellen.<br /><br />Sie können bei Bedarf zusätzliche vertrauenswürdige Stammzertifizierungsstellenzertifikate verwenden. Sie können dies zum Beispiel vornehmen, um einer Zertifizierungsstelle eine Vertrauensstellung zu gewähren, die die Serverauthentifizierungszertifikate für Ihre WLAN-Zugriffspunkte signiert.|

### Konten

|Name|Details|
|--------|-----------|
|**NDES-Dienstkonto**|Sie geben ein Domänenbenutzerkonto an, das als NDES-Dienstkonto verwendet werden soll.|

## Konfigurieren der Infrastruktur
Vor dem Konfigurieren von Zertifikatprofilen müssen Sie die folgenden Aufgaben ausführen, für die Sie Kenntnisse über Windows Server 2012 R2 und Active Directory-Zertifikatdienste (ADCS) benötigen:

**Aufgabe 1**: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle

**Aufgabe 2** (nur für SCEP-Profil): Konfigurieren der erforderlichen Komponenten auf dem NDES-Server

**Aufgabe 3** (nur für SCEP-Profile): Konfigurieren von NDES für die Verwendung mit Intune

**Aufgabe 4**: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors

## Aufgabe 1: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

-   Erstellen eines NDES-Dienstkontos

    > [!NOTE] Zum Widerrufen von Zertifikaten benötigt das NDES-Dienstkonto die Berechtigung *Zertifikate ausstellen und verwalten* für jede Zertifikatvorlage, die von einem Zertifikatprofil verwendet wird.

-   Konfigurieren einer Zertifikatvorlage für NDES

-   Veröffentlichen der Zertifikatvorlage für NDES

##### So konfigurieren Sie die Zertifizierungsstelle

1.  Erstellen Sie ein Domänenbenutzerkonto, das als NDES-Dienstkonto verwendet werden soll. Sie geben dieses Konto an, wenn Sie Vorlagen auf der ausstellenden Zertifizierungsstelle konfigurieren, bevor Sie NDES installieren und konfigurieren.

2.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifikatsvorlagen-Snap-In, um eine neue benutzerdefinierte Vorlage zu erstellen oder eine vorhandene Vorlage zu kopieren. Bearbeiten Sie dann eine vorhandene Vorlage (z. B. die Vorlage „Benutzer“) für die Verwendung mit NDES.

    Die Vorlage muss wie folgt konfiguriert sein:

    -   Geben Sie einen aussagekräftigen **Vorlagenanzeigenamen** für die Vorlage ein.

    -   Wählen Sie auf der Registerkarte **Antragstellername** die Option **Informationen werden in der Anforderung angegeben**. (Sicherheit wird durch das Intune-Richtlinienmodul für NDES erzwungen.)

    -   Stellen Sie sicher, dass auf der Registerkarte **Erweiterungen** die **Beschreibung der Anwendungsrichtlinien** die **Clientauthentifizierung**umfasst.

        > [!IMPORTANT] Bearbeiten Sie für iOS- und Mac OS X-Zertifikatvorlagen auf der Registerkarte **Erweiterungen** die Option **Schlüsselverwendung**, und stellen Sie sicher, dass die Option **Signatur ist Ursprungsnachweis** nicht aktiviert ist.

    -   Fügen Sie auf der Registerkarte **Sicherheit** das Dienstkonto für NDES hinzu, und weisen Sie ihm Berechtigungen zum **Registrieren** der Vorlage zu.

3.  Prüfen Sie auf der Registerkarte **Allgemein** die **Gültigkeitsdauer** der Vorlage. In der Standardeinstellung verwendet Intune den in der Vorlage konfigurierten Wert. Sie haben jedoch die Möglichkeit, die Zertifizierungsstelle so zu konfigurieren, dass dem Antragsteller ermöglicht wird, einen anderen Wert anzugeben, den Sie dann in der Intune-Verwaltungskonsole festlegen können. Wenn Sie immer den in der Vorlage festgelegten Wert verwenden möchten, überspringen Sie den Rest dieses Schritts.

    > [!IMPORTANT] Die iOS- und Mac OS X-Plattformen verwenden immer den in der Vorlage festgelegten Wert, unabhängig von anderen Konfigurationen, die Sie vornehmen.

    Um die Zertifizierungsstelle so zu konfigurieren, dass der Antragsteller die Gültigkeitsdauer festlegen kann, führen Sie auf der Zertifizierungsstelle die folgenden Befehle aus:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifizierungsstellen-Snap-In, um die Zertifikatvorlage zu veröffentlichen.

    1.  Wählen Sie den Knoten **Zertifikatvorlagen** aus, klicken Sie auf **Aktion** -&gt; **Neu** &gt; **Auszustellende Zertifikatvorlage**, und wählen Sie dann die Vorlage aus, die Sie in Schritt 2 erstellt haben.

    2.  Überprüfen Sie, ob die Vorlage veröffentlicht wurde, indem Sie sie im Ordner **Zertifikatvorlagen** anzeigen.

5.  Für PFX-Profile:  Stellen Sie auf dem Zertifizierungsstellencomputer sicher, dass der Computer, den Intune Certificate Connector hostet, die Berechtigung „Registrieren“ hat, damit dieser auf die Vorlage zugreifen kann, die zum Erstellen des PFX-Profils verwendet wurde. Legen Sie diese Berechtigung auf der Registerkarte **Sicherheit** in den Eigenschaften des Computers mit der Zertifizierungsstelle fest.

## Aufgabe 2 (nur für SCEP-Profile): Konfigurieren der erforderlichen Komponenten auf dem NDES-Server
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

-   Hinzufügen von NDES zu einem Windows-Server und Konfigurieren von IIS zur Unterstützung von NDES

-   Hinzufügen des NDES-Dienstkontos zur Gruppe „IIS_IUSR“

-   Festlegen des SPN für das NDES-Dienstkonto

##### So konfigurieren Sie die Voraussetzungen für den NDES-Server

1.  Auf dem Server, der NDES hosten soll, müssen Sie sich als **Unternehmensadministrator**anmelden und dann den [Assistenten zum Hinzufügen von Rollen und Features](https://technet.microsoft.com/library/hh831809.aspx) zum Installieren von NDES verwenden:

    1.  Wählen Sie im Assistenten die Option **Active Directory-Zertifikatdienste** , um Zugriff auf die Rollendienste der AD-Zertifikatdienste zu erhalten. Wählen Sie die Option **Registrierungsdienst für Netzwerkgeräte**, deaktivieren Sie die Option **Zertifizierungsstelle**, und schließen Sie den Assistenten dann ab.

        > [!TIP]
        > Klicken Sie auf der Seite **Installationsvorgang** des Assistenten nicht auf **Schließen**. Klicken Sie stattdessen auf den Link **Active Directory-Zertifikatdienste auf dem Zielserver konfigurieren**. Daraufhin wird der Assistent zur **AD CS-Konfiguration** geöffnet, den Sie für die nächste Aufgabe verwenden. Nachdem der Assistent für die AD CS-Konfiguration geöffnet wurde, können Sie den Assistenten zum Hinzufügen von Rollen und Features schließen.

    2.  Wenn NDES zum Server hinzugefügt wird, installiert der Assistent ebenfalls IIS. Stellen Sie sicher, dass IIS wie folgt konfiguriert ist:

        -   **Webserver** &gt; **Sicherheit** &gt; **Anforderungsfilterung**

        -   **Webserver** &gt; **Anwendungsentwicklung** &gt; ** ASP.NET 3.5**. Bei der Installation von ASP.NET 3,5 wird .NET Framework 3,5 installiert. Installieren Sie bei Installation von .NET Framework 3.5 sowohl das Feature **.NET Framework 3.5** als auch die **HTTP-Aktivierung**.

        -   **Webserver** &gt; **Anwendungsentwicklung** &gt; **ASP.NET 4.5**. Bei der Installation von ASP.NET 4.5 wird .NET Framework 4.5 installiert. Installieren Sie bei der Installation von .NET Framework 4.5 das Kernfeature **.NET Framework 4.5**, das Feature **ASP.NET 4.5** und das Feature **WCF-Dienste** &gt; **HTTP-Aktivierung**.

        -   **Verwaltungstools** &gt; **IIS 6-Verwaltungskompatibilität** &gt; **IIS 6-Metabasiskompatibilität**

        -   **Verwaltungstools** &gt; **IIS 6-Verwaltungskompatibilität** &gt; **IIS 6-WMI-Kompatibilität**

2.  Fügen Sie auf dem Server das NDES-Dienstkonto als Mitglied der Gruppe **IIS_IUSR** hinzu.

3.  Führen Sie den folgenden Befehl aus, um den SPN des NDES-Dienstkontos festzulegen:

    -   **setspn -s http/&lt;DNS-Name des NDES-Servers&gt; &lt;Domänenname&gt;\&lt;NDES-Dienstkontoname&gt;**

    Wenn der NDES-Server zum Beispiel den Namen **Server01**hat, die Domäne **Contoso.com**ist und das Dienstkonto **NDESService**lautet, verwenden Sie Folgendes:

    -   **setspn –s http/Server01.contoso.com contoso\NDESService**

## Aufgabe 3 (nur für SCEP-Profile): Konfigurieren von NDES für die Verwendung mit Microsoft Intune 
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

-   Konfigurieren von NDES für die Verwendung mit der ausstellenden Zertifizierungsstelle

-   Binden des Serverauthentifizierungszertifikats (SSL) in IIS

-   Konfigurieren der Anforderungsfilterung in IIS

##### So konfigurieren Sie NDES für die Verwendung mit Intune

1.  Öffnen Sie auf dem NDES-Server den AD CS-Konfigurations-Assistenten, und nehmen Sie dann die folgenden Konfigurationen vor.

    > [!TIP]
    > Dieser Assistent ist bereits geöffnet, wenn Sie in der vorherigen Aufgabe auf den Link geklickt haben. Andernfalls öffnen Sie den Server-Manager, um auf die Konfiguration nach der Bereitstellung der Active Directory-Zertifikatdienste zuzugreifen.

    -   Wählen Sie auf der Seite **Rollendienste** die Option **Registrierungsdienst für Netzwerkgeräte**.

    -   Geben Sie auf der Seite **Dienstkonto für NDES** das NDES-Dienstkonto an.

    -   Klicken Sie auf der Seite **ZS für NDES** auf **Auswählen**, und wählen Sie dann die ausstellende Zertifizierungsstelle aus, auf der Sie die Zertifikatvorlage konfiguriert haben.

    -   Legen Sie auf der Seite **Kryptografie für NDES** die Schlüssellänge entsprechend den Anforderungen Ihres Unternehmens fest.

    Klicken Sie auf der Seite **Bestätigung** auf **Konfigurieren** , um den Assistenten zu beenden.

2.  Bearbeiten Sie nach Beendigung des Assistenten den folgenden Registrierungsschlüssel auf dem NDES-Server:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Um diesen Schlüssel zu bearbeiten, ermitteln Sie den **Zweck** der Zertifikatvorlage, wie auf der entsprechenden Registerkarte **Anforderungsverarbeitung** aufgeführt, und bearbeiten Sie dann den zugehörigen Eintrag in der Registrierung. Ersetzen Sie hierzu die vorhandenen Daten durch den Namen der Zertifikatvorlage (nicht den Anzeigenamen der Vorlage), den Sie in Aufgabe 1 festgelegt haben. In der folgenden Tabelle ist der Zertifikatvorlagenzweck den Werten in der Registrierung zugeordnet:

    |Zertifikatvorlagenzweck (auf der Registerkarte „Anforderungsverarbeitung“)|Zu bearbeitender Registrierungswert|In der Intune-Verwaltungskonsole für das SCEP-Profil angezeigter Wert|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Signatur|SignatureTemplate|Digitale Signatur|
    |Verschlüsselung|EncryptionTemplate|Schlüsselverschlüsselung|
    |Signatur und Verschlüsselung|GeneralPurposeTemplate|Schlüsselverschlüsselung<br /><br />Digitale Signatur|
    Wenn der Zweck der Zertifizierungsvorlage zum Beispiel **Verschlüsselung**ist, bearbeiten Sie den Wert **EncryptionTemplate** so, dass er dem Namen der Zertifikatvorlage entspricht.

3.  Führen Sie nach dem Bearbeiten der Registrierung **iisreset** auf dem Server aus, um zu erzwingen, dass der Server die aktuellen Konfigurationsänderungen übernimmt.

##### So installieren und binden Sie Zertifikate auf dem NDES-Server

1.  Fordern Sie auf dem NDES-Server ein **Serverauthentifizierungszertifikat** von der internen oder einer öffentlichen Zertifizierungsstelle an, und installieren Sie es. Sie binden dieses SSL-Zertifikat anschließend in IIS.

    > [!TIP]
    > Nachdem Sie das SSL-Zertifikat in IIS gebunden haben, installieren Sie auch ein Clientauthentifizierungszertifikat. Dieses Zertifikat kann von jeder Zertifizierungsstelle ausgestellt werden, die vom NDES-Server als vertrauenswürdig eingestuft wird. Obwohl es sich nicht um die bewährte Methode handelt, können Sie das gleiche Zertifikat für die Server und die Clientauthentifizierung verwenden, solange das Zertifikat über beide erweiterten Schlüsselverwendungen (EKUs) verfügt. In den folgenden Schritten finden Sie Informationen zu diesen Authentifizierungszertifikaten.

    1.  Nachdem Sie das Serverauthentifizierungszertifikat erhalten haben, öffnen Sie den **IIS-Manager**, wählen im Fenster **Verbindungen** die Option **Standardwebsite** , und klicken dann im Fenster **Aktionen** auf **Bindungen** .

    2.  Klicken Sie auf **Hinzufügen**, legen Sie als **Typ** die Option **https**fest, und stellen Sie sicher, dass der Port **443**ist. (Für eigenständiges Intune wird nur Port 443 unterstützt.)

    3.  Geben Sie unter **SSL-Zertifikat**das Serverauthentifizierungszertifikat an.

        > [!NOTE] Wenn der NDES-Server sowohl einen externen als auch einen internen Namen für eine einzelne Netzwerkadresse verwendet, muss das Serverauthentifizierungszertifikat über einen **Antragstellernamen** mit einem externen öffentlichen Servernamen sowie über einen **alternativen Antragstellernamen** verfügen, der den Namen des internen Servers enthält.

2.  Fordern Sie auf dem NDES-Server ein **Clientauthentifizierungszertifikat** von der internen oder einer öffentlichen Zertifizierungsstelle an, und installieren Sie es. Dies kann dasselbe Zertifikat wie das Serverauthentifizierungszertifikat sein, wenn dieses Zertifikat über beide Funktionen verfügt.

    Das Clientauthentifizierungszertifikat muss die folgenden Eigenschaften aufweisen:

    **Erweiterte Schlüsselverwendung**: Dies muss die **Clientauthentifizierung** umfassen.

    **Antragstellername**: Dies muss mit dem DNS-Namen des Servers identisch sein, auf dem das Zertifikat installiert wird (d. h. dem NDES-Server).

##### So konfigurieren Sie die IIS-Anforderungsfilterung

1.  Öffnen Sie auf dem NDES-Server den **IIS-Manager**, wählen Sie im Fenster **Verbindungen** die Option **Standardwebsite** , und öffnen Sie dann die **Anforderungsfilterung**.

2.  Klicken Sie auf **Featureeinstellungen bearbeiten**, und legen Sie dann Folgendes fest:

    **Abfragezeichenfolge (Bytes)** = **65534**

    **Maximale URL-Länge (Bytes)** = **65534**

3.  Überprüfen Sie den folgenden Registrierungsschlüssel:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Stellen Sie sicher, dass die folgenden Werte als DWORD-Einträge festgelegt sind:

    Name: **MaxFieldLength**mit einem Dezimalwert von **65534**

    Name: **MaxRequestBytes**mit einem Dezimalwert von **65534**

4.  Starten Sie den NDES-Server neu. Der Server ist jetzt bereit zur Unterstützung des Certificate Connectors.

## Aufgabe 4: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors: Für SCEP- und PFX-Zertifikate.
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

Aktivieren der Unterstützung für NDES in Intune

Herunterladen, Installieren und Konfigurieren des Certificate Connectors auf dem NDES-Server

##### So aktivieren Sie die Unterstützung für den Certificate Connector

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), und klicken Sie auf **Verwaltung** &gt; **Certificate Connector**.

2.  Klicken Sie auf **Lokalen Certificate Connector konfigurieren**.

3.  Wählen Sie **Certificate Connector aktivieren**aus, und klicken Sie dann auf **OK**.

##### So wird der Certificate Connector heruntergeladen, installiert und konfiguriert

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), und klicken Sie dann auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Certificate Connector** &gt; **Certificate Connector herunterladen**.

2.  Nachdem der Download abgeschlossen ist, führen Sie das heruntergeladene Installationsprogramm (**ndesconnectorssetup.exe**) aus:

    -   Führen Sie für PFX-Zertifikate das Installationsprogramm auf dem Computer aus, der eine Verbindung mit der Zertifizierungsstelle herstellen kann. Wählen Sie die Option „PFX-Verteilung“ aus, und klicken Sie auf „Installieren“. Fahren Sie nach Abschluss der Installation mit dem Erstellen eines Zertifikatprofils fort, wie unter [Konfigurieren von Zertifikatprofilen](configure-intune-certificate-profiles.md) beschrieben.

    -   Führen Sie für SCEP-Zertifikate das Installationsprogramm auf einem Server mit Windows Server 2012 R2 aus.

    Bei der Option "SCEP" installiert das Installationsprogramm auch das Richtlinienmodul für NDES und der CRP-Webdienst. (Der CRP-Webdienst „CertificateRegistrationSvc“ wird als Anwendung in IIS ausgeführt.)

    > [!NOTE]
    > Bei der Installation von NDES für eigenständiges Intune wird der CRP-Dienst automatisch mit dem Certificate Connector installiert. Bei Verwendung von Intune mit dem Konfigurations-Manager installieren Sie den Zertifikatregistrierungspunkt als eine separate Standortsystemrolle.

3.  Wenn Sie zur Eingabe des Clientzertifikats für den Certificate Connector aufgefordert werden, klicken Sie auf **Auswählen**, und wählen Sie das **Clientauthentifizierungszertifikat** aus, das Sie in Aufgabe 3 auf dem NDES-Server installiert haben.

    Nachdem Sie das Clientauthentifizierungszertifikat ausgewählt haben, wird erneut die Oberfläche **Clientzertifikat für Microsoft Intune Certificate Connector** angezeigt. Auch wenn das ausgewählte Zertifikat nicht angezeigt wird, klicken Sie auf **Weiter** , um die Eigenschaften des Zertifikats anzuzeigen. Klicken Sie dann auf **Weiter**, und klicken Sie anschließend auf **installieren**.

4.  Nach Abschluss des Assistenten, jedoch vor dem Schließen des Assistenten, klicken Sie auf **Certificate Connector-Benutzeroberfläche starten**.

    > [!TIP] Wenn Sie den Assistenten schließen, bevor Sie die Benutzeroberfläche des Certificate Connectors starten, können Sie sie mit dem folgenden Befehl erneut öffnen:
    >
    > **&lt;Installationspfad&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Gehen Sie auf der Benutzeroberfläche von **Certificate Connector** so vor:

    Klicken Sie auf **Anmelden**, und geben Sie die Anmeldeinformationen des Intune-Dienstadministrators oder für einen Mandantenadministrator mit der globalen Administratorberechtigung ein.

    Wenn Ihr Unternehmen einen Proxyserver verwendet und der Proxy erforderlich ist, damit der NDES-Server auf das Internet zugreifen kann, klicken Sie auf **Proxyserver verwenden**, und geben Sie dann den Proxyservernamen, Port und die Kontoanmeldedaten für die Verbindung an.

    Wählen Sie die Registerkarte **Erweitert** aus, und geben Sie dann die Anmeldeinformationen für ein Konto ein, das über die Berechtigung **Zertifikate ausgeben und verwalten** für die ausstellende Zertifizierungsstelle verfügt, und klicken Sie dann auf **Anwenden**.

    Sie können jetzt die Benutzeroberfläche des Certificate Connectors schließen.

6.  Öffnen Sie eine Eingabeaufforderung, und geben Sie **services.msc** ein. Drücken Sie dann die **EINGABETASTE**, klicken Sie mit der rechten Maustaste auf **Intune-Connectordienst**, und klicken Sie dann auf **Neu starten**.

Um zu überprüfen, das der Dienst ausgeführt wird, öffnen Sie einen Browser, und geben Sie die folgenden URL ein. Es sollte ein **403** -Fehler zurückgegeben werden:

**http:// &lt;FQDN_des_NDES_Servers&gt;/certsrv/mscep/mscep.dll**

### Nächste Schritte
Sie sind jetzt bereit, Zertifikatprofile gemäß der Beschreibung in [Konfigurieren von Zertifikatprofilen](configure-intune-certificate-profiles.md) zu konfigurieren.


<!--HONumber=May16_HO4-->


