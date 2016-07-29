---
title: "Konfigurieren der Zertifikatinfrastruktur für PFX | Microsoft Intune"
description: Erstellen Sie PFX-Zertifikatprofile, und stellen Sie sie bereit.
keywords: 
author: nbigman
manager: Arob98
ms.date: 05/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: f654dba31198115851feeeec90f04b8ad767e549



---
# Konfigurieren der Zertifikatinfrastruktur
In diesem Thema werden die Anforderungen beschrieben, die zum Erstellen und Bereitstellen von PFX-Zertifikatprofilen erfüllt sein müssen.

Für jede zertifikatbasierte Authentifizierung im Unternehmen benötigen Sie eine Unternehmenszertifizierungsstelle.

Damit Sie PFX-Zertifikatprofile verwenden können, benötigen Sie zusätzlich zur Unternehmenszertifizierungsstelle auch Folgendes:

-   einen Computer, der mit der Zertifizierungsstelle kommunizieren kann (Sie können auch den Computer der Zertifizierungsstelle selbst verwenden).

 -  den Intune Zertifikatconnector, der auf dem Computer ausgeführt wird, der mit der Zertifizierungsstelle kommunizieren kann.

## Beschreibung der lokalen Infrastruktur


-    **Active Directory-Domäne**: Alle in diesem Abschnitt aufgeführten Server (außer dem Webanwendungsproxy-Server) müssen der Active Directory-Domäne angehören.

-  **Zertifizierungsstelle** (Certification Authority, CA): Eine Unternehmenszertifizierungsstelle, die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. Anleitungen zum Einrichten einer Zertifizierungsstelle finden Sie unter [Installieren der Zertifizierungsstelle](http://technet.microsoft.com/library/jj125375.aspx).
    Wenn die Zertifizierungsstelle unter Windows Server 2008 R2 ausgeführt wird, müssen Sie [den Hotfix von KB2483564 installieren](http://support.microsoft.com/kb/2483564/).

 -  **Computer, der mit der Zertifizierungsstelle kommunizieren kann**: Verwenden Sie alternativ den Computer der Zertifizierungsstelle selbst.
-  **Microsoft Intune-Zertifikatconnector**: Sie verwenden die Intune-Verwaltungskonsole zum Herunterladen des Installationsprogramms für den **Zertifikatconnector** (**ndesconnectorssetup.exe**). Führen Sie **ndesconnectorssetup.exe** dann auf dem Computer aus, auf dem Sie den Zertifikatconnector installieren möchten. Installieren Sie für PFX-Zertifikatprofile den Zertifikatconnector auf dem Computer, der mit der Zertifizierungsstelle kommuniziert.
-  **Webanwendungsproxy-Server** (optional): Sie können einen Server mit Windows Server 2012 R2 oder höher als Webanwendungsproxy-Server (WAP) verwenden. Diese Konfiguration:
    -  ermöglicht Geräten das Empfangen von Zertifikaten über eine Internetverbindung,
    -  ist eine Sicherheitsempfehlung, wenn Geräte eine Verbindung über das Internet herstellen, um Zertifikate zu empfangen oder zu erneuern.

 > [!NOTE]           
> -    Auf dem Server, der den WAP hostet, [muss ein Update installiert werden](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) , das die Unterstützung für lange URLs aktiviert, die vom Registrierungsdienst für Netzwerkgeräte verwendet werden. Dieses Update ist im [Updaterollup vom Dezember 2014](http://support.microsoft.com/kb/3013769)enthalten oder kann auch einzeln von [KB3011135](http://support.microsoft.com/kb/3011135)heruntergeladen werden.
>-  Zudem muss der Server, der WAP hostet, über ein SSL-Zertifikat verfügen, das mit dem Namen übereinstimmt, der für externe Clients veröffentlicht wird. Ferner muss der Server dem SSL-Zertifikat vertrauen, das auf dem NDES-Server verwendet wird. Diese Zertifikate ermöglichen dem WAP-Server, die SSL-Verbindung von Clients zu beenden und eine neue SSL-Verbindung mit dem NDES-Server herzustellen.
    Weitere Informationen über Zertifikate für WAP finden Sie im Abschnitt **Planen von Zertifikaten** des Themas [Installieren und Konfigurieren des Webanwendungsproxys für die Veröffentlichung interner Anwendungen](https://technet.microsoft.com/library/dn383650.aspx). Allgemeine Informationen zu WAP-Servern finden Sie unter [Verwenden des Webanwendungsproxys](http://technet.microsoft.com/library/dn584113.aspx).|


### Zertifikate und Vorlagen

|Objekt|Details|
|----------|-----------|
|**Zertifikatvorlage**|Sie konfigurieren diese Vorlage auf der ausstellenden Zertifizierungsstelle.|
|**Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle**|Sie exportieren dies als eine **CER** -Datei von der ausstellenden Zertifizierungsstelle oder von Geräten, die der ausstellenden Zertifizierungsstelle vertrauen, und stellen es mit dem Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle für Geräte bereit.<br /><br />Sie verwenden für jede Betriebssystemplattform ein einzelnes Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ordnen es dem jeweiligen vertrauenswürdigen Stammzertifikatprofil zu, das Sie erstellen.<br /><br />Sie können bei Bedarf zusätzliche vertrauenswürdige Stammzertifizierungsstellenzertifikate verwenden. Sie können dies zum Beispiel vornehmen, um einer Zertifizierungsstelle eine Vertrauensstellung zu gewähren, die die Serverauthentifizierungszertifikate für Ihre WLAN-Zugriffspunkte signiert.|


## Konfigurieren der Infrastruktur
Vor dem Konfigurieren von Zertifikatprofilen müssen Sie die folgenden Aufgaben ausführen, für die Sie Kenntnisse über Windows Server 2012 R2 und Active Directory-Zertifikatdienste (ADCS) benötigen:

**Aufgabe 1**: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle **Aufgabe 2**: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors

### Aufgabe 1: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle
Bei dieser Aufgabe veröffentlichen Sie die Zertifikatvorlage.

##### So konfigurieren Sie die Zertifizierungsstelle

1.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifikatsvorlagen-Snap-In, um eine neue benutzerdefinierte Vorlage zu erstellen oder eine vorhandene Vorlage zu kopieren. Bearbeiten Sie dann eine vorhandene Vorlage (z.B. die Vorlage „Benutzer“) für die Verwendung mit PFX.

    Die Vorlage muss wie folgt konfiguriert sein:

    -   Geben Sie einen aussagekräftigen **Vorlagenanzeigenamen** für die Vorlage ein.

    -   Wählen Sie auf der Registerkarte **Antragstellername** die Option **Informationen werden in der Anforderung angegeben**. (Sicherheit wird durch das Intune-Richtlinienmodul für NDES erzwungen.)

    -   Stellen Sie sicher, dass auf der Registerkarte **Erweiterungen** die **Beschreibung der Anwendungsrichtlinien** die **Clientauthentifizierung**umfasst.

        > [!IMPORTANT]
        > Bearbeiten Sie für iOS- und Mac OS X-Zertifikatvorlagen auf der Registerkarte **Erweiterungen** die Option **Schlüsselverwendung** , und stellen Sie sicher, dass die Option **Signatur ist Ursprungsnachweis** nicht aktiviert ist.


3.  Prüfen Sie auf der Registerkarte **Allgemein** die **Gültigkeitsdauer** der Vorlage. In der Standardeinstellung verwendet Intune den in der Vorlage konfigurierten Wert. Sie haben jedoch die Möglichkeit, die Zertifizierungsstelle so zu konfigurieren, dass dem Antragsteller ermöglicht wird, einen anderen Wert anzugeben, den Sie dann in der Intune-Verwaltungskonsole festlegen können. Wenn Sie immer den in der Vorlage festgelegten Wert verwenden möchten, überspringen Sie den Rest dieses Schritts.

    > [!IMPORTANT]
    > Die iOS- und Mac OS X-Plattformen verwenden immer den in der Vorlage festgelegten Wert, unabhängig von anderen Konfigurationen, die Sie vornehmen.

    Um die Zertifizierungsstelle so zu konfigurieren, dass der Antragsteller die Gültigkeitsdauer festlegen kann, führen Sie auf der Zertifizierungsstelle die folgenden Befehle aus:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifizierungsstellen-Snap-In, um die Zertifikatvorlage zu veröffentlichen.

    1.  Wählen Sie den Knoten **Zertifikatvorlagen** aus, klicken Sie auf **Aktion** -&gt; **Neu** &gt; **Auszustellende Zertifikatvorlage**, und wählen Sie dann die Vorlage aus, die Sie in Schritt 2 erstellt haben.

    2.  Überprüfen Sie, ob die Vorlage veröffentlicht wurde, indem Sie sie im Ordner **Zertifikatvorlagen** anzeigen.

5.  Stellen Sie auf dem Zertifizierungsstellencomputer sicher, dass der Computer, der den Intune Certificate Connector hostet, die Berechtigung „Registrieren“ hat, damit dieser auf die Vorlage zugreifen kann, die zum Erstellen des PFX-Profils verwendet wurde. Legen Sie diese Berechtigung auf der Registerkarte **Sicherheit** in den Eigenschaften des Computers mit der Zertifizierungsstelle fest.

### Aufgabe 2: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

Herunterladen, Installieren und Konfigurieren des Certificate Connectors

##### So aktivieren Sie die Unterstützung für den Zertifikatconnector

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), und klicken Sie auf **Verwaltung** &gt; **Certificate Connector**.

2.  Klicken Sie auf **Lokalen Certificate Connector konfigurieren**.

3.  Wählen Sie **Zertifikatconnector aktivieren**aus, und klicken Sie dann auf **OK**.

##### So wird der Zertifikatconnector heruntergeladen, installiert und konfiguriert

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), und klicken Sie dann auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Certificate Connector** &gt; **Certificate Connector herunterladen**.

2.  Nachdem der Download abgeschlossen ist, führen Sie das heruntergeladene Installationsprogramm (**ndesconnectorssetup.exe**) aus:

  Führen Sie das Installationsprogramm auf dem Computer aus, der eine Verbindung mit der Zertifizierungsstelle herstellen kann. Wählen Sie die Option „PFX-Verteilung“ aus, und klicken Sie auf „Installieren“. Fahren Sie nach Abschluss der Installation mit dem Erstellen eines Zertifikatprofils fort, wie unter [Konfigurieren von Zertifikatprofilen](configure-intune-certificate-profiles.md) beschrieben.

   <!-- Not sure about step 3 below -->

3.  Wenn Sie zur Eingabe des Clientzertifikats für den Certificate Connector aufgefordert werden, klicken Sie auf **Auswählen**, und wählen Sie das **Clientauthentifizierungszertifikat** aus, das Sie in Aufgabe 3 installiert haben.

    Nachdem Sie das Clientauthentifizierungszertifikat ausgewählt haben, wird erneut die Oberfläche **Clientzertifikat für den Microsoft Intune-Zertifikatconnector** angezeigt. Auch wenn das ausgewählte Zertifikat nicht angezeigt wird, klicken Sie auf **Weiter** , um die Eigenschaften des Zertifikats anzuzeigen. Klicken Sie dann auf **Weiter**, und klicken Sie anschließend auf **installieren**.

4.  Nach Abschluss des Assistenten, jedoch vor dem Schließen des Assistenten, klicken Sie auf **Zertifikatconnector-Benutzeroberfläche starten**.

    > [!TIP]
    > Wenn Sie den Assistenten schließen, bevor Sie die Benutzeroberfläche des Zertifikatconnectors starten, können Sie sie mit dem folgenden Befehl erneut öffnen:
    >
    > **&lt;Installationspfad&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Gehen Sie auf der Benutzeroberfläche von **Zertifikatconnector** so vor:

    Klicken Sie auf **Anmelden**, und geben Sie die Anmeldeinformationen des Intune-Dienstadministrators oder für einen Mandantenadministrator mit der globalen Administratorberechtigung ein.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    Wählen Sie die Registerkarte **Erweitert** aus, und geben Sie dann die Anmeldeinformationen für ein Konto ein, das über die Berechtigung **Zertifikate ausgeben und verwalten** für die ausstellende Zertifizierungsstelle verfügt, und klicken Sie dann auf **Anwenden**.

    Sie können jetzt die Benutzeroberfläche des Zertifikatconnectors schließen.

6.  Öffnen Sie eine Eingabeaufforderung, und geben Sie **services.msc** ein. Drücken Sie dann die **EINGABETASTE**, klicken Sie mit der rechten Maustaste auf **Intune-Connectordienst**, und klicken Sie dann auf **Neu starten**.

Um zu überprüfen, das der Dienst ausgeführt wird, öffnen Sie einen Browser, und geben Sie die folgenden URL ein. Es sollte ein **403** -Fehler zurückgegeben werden:

**http:// &lt;FQDN_des_NDES_Servers&gt;/certsrv/mscep/mscep.dll**

### Nächste Schritte
Sie sind jetzt bereit, Zertifikatprofile gemäß der Beschreibung in [Konfigurieren von Zertifikatprofilen](Configure-Intune-certificate-profiles.md) zu konfigurieren.



<!--HONumber=Jul16_HO3-->


