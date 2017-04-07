---
title: "Konfigurieren der Intune-Zertifikatinfrastruktur für PKCS"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Ihre Infrastruktur für die Verwendung von PKCS-Zertifikaten mit Intune konfigurieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: ed1d6ce687666e1630ca25b08db72d6c99ef617a
ms.lasthandoff: 03/13/2017



---
# <a name="configure-your-microsoft-intune-certificate-infrastructure-for-pkcs"></a>Konfigurieren Ihrer Microsoft Intune-Zertifikatsinfrastruktur für PKCS
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

In diesem Thema werden die Anforderungen beschrieben, die zum Erstellen und Bereitstellen von PKCS-Zertifikatprofilen mit Intune erfüllt sein müssen.

Für jede zertifikatbasierte Authentifizierung im Unternehmen benötigen Sie eine Unternehmenszertifizierungsstelle.

Damit Sie PKCS-Zertifikatprofile verwenden können, benötigen Sie zusätzlich zur Unternehmenszertifizierungsstelle auch Folgendes:

-   einen Computer, der mit der Zertifizierungsstelle kommunizieren kann (Sie können auch den Computer der Zertifizierungsstelle selbst verwenden).

-  den Intune Zertifikatconnector, der auf dem Computer ausgeführt wird, der mit der Zertifizierungsstelle kommunizieren kann.

## <a name="important-terms"></a>Wichtige Begriffe


-    **Active Directory-Domäne**: Alle in diesem Abschnitt aufgeführten Server (außer dem Webanwendungsproxy-Server) müssen der Active Directory-Domäne angehören.

-  **Zertifizierungsstelle**: Eine Unternehmenszertifizierungsstelle (Certification Authority; CA), die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. Anleitungen zum Einrichten einer Zertifizierungsstelle finden Sie unter [Installieren der Zertifizierungsstelle](http://technet.microsoft.com/library/jj125375.aspx).
    Wenn die Zertifizierungsstelle unter Windows Server 2008 R2 ausgeführt wird, müssen Sie [den Hotfix von KB2483564 installieren](http://support.microsoft.com/kb/2483564/).

-  **Computer, der mit der Zertifizierungsstelle kommunizieren kann**: Verwenden Sie alternativ den Computer der Zertifizierungsstelle selbst.
-  **Microsoft Intune Certificate Connector:** Sie laden das Installationsprogramm für den **Certificate Connector** (**ndesconnectorssetup.exe**) im Azure-Portal herunter. Führen Sie **ndesconnectorssetup.exe** dann auf dem Computer aus, auf dem Sie den Zertifikatconnector installieren möchten. Installieren Sie für PKCS-Zertifikatprofile den Certificate Connector auf dem Computer, der mit der Zertifizierungsstelle kommuniziert.
-  **Webanwendungsproxy-Server** (optional): Sie können einen Server mit Windows Server 2012 R2 oder höher als Webanwendungsproxy-Server (WAP) verwenden. Diese Konfiguration:
    -  ermöglicht Geräten das Empfangen von Zertifikaten über eine Internetverbindung,
    -  ist eine Sicherheitsempfehlung, wenn Geräte eine Verbindung über das Internet herstellen, um Zertifikate zu empfangen oder zu erneuern.

 > [!NOTE]           
> -    Auf dem Server, der den WAP hostet, [muss ein Update installiert werden](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx), das die Unterstützung für lange URLs aktiviert, die vom Registrierungsdienst für Netzwerkgeräte (Network Device Enrollment Service; NDES) verwendet werden. Dieses Update ist im [Updaterollup vom Dezember 2014](http://support.microsoft.com/kb/3013769)enthalten oder kann auch einzeln von [KB3011135](http://support.microsoft.com/kb/3011135)heruntergeladen werden.
>-  Zudem muss der Server, der den WAP hostet, über ein SSL-Zertifikat verfügen, das mit dem Namen übereinstimmt, der für externe Clients veröffentlicht wird. Ferner muss das SSL-Zertifikat, das auf dem NDES-Server verwendet wird, vertrauenswürdig sein. Diese Zertifikate ermöglichen dem WAP-Server, die SSL-Verbindung von Clients zu beenden und eine neue SSL-Verbindung mit dem NDES-Server herzustellen.
    Weitere Informationen über Zertifikate für WAP finden Sie im Abschnitt **Planen von Zertifikaten** des Themas [Installieren und Konfigurieren des Webanwendungsproxys für die Veröffentlichung interner Anwendungen](https://technet.microsoft.com/library/dn383650.aspx). Allgemeine Informationen zu WAP-Servern finden Sie unter [Verwenden des Webanwendungsproxys](http://technet.microsoft.com/library/dn584113.aspx).|


## <a name="certificates-and-templates"></a>Zertifikate und Vorlagen

|Objekt|Details|
|----------|-----------|
|**Zertifikatvorlage**|Sie konfigurieren diese Vorlage auf der ausstellenden Zertifizierungsstelle.|
|**Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle**|Sie exportieren dies als eine **CER** -Datei von der ausstellenden Zertifizierungsstelle oder von Geräten, die der ausstellenden Zertifizierungsstelle vertrauen, und stellen es mit dem Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle für Geräte bereit.<br /><br />Sie verwenden für jede Betriebssystemplattform ein einzelnes Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ordnen es dem jeweiligen vertrauenswürdigen Stammzertifikatprofil zu, das Sie erstellen.<br /><br />Sie können bei Bedarf zusätzliche vertrauenswürdige Stammzertifizierungsstellenzertifikate verwenden. Sie können dies zum Beispiel vornehmen, um einer Zertifizierungsstelle eine Vertrauensstellung zu gewähren, die die Serverauthentifizierungszertifikate für Ihre WLAN-Zugriffspunkte signiert.|


## <a name="configure-your-infrastructure"></a>Konfigurieren der Infrastruktur
Bevor Sie Zertifikatprofile konfigurieren können, müssen Sie die folgenden Aufgaben ausführen. Diese Aufgaben setzen Kenntnisse in Windows Server 2012 R2 und Active Directory-Zertifikatdiensten voraus:

- **Aufgabe 1**: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle
- **Aufgabe 2**: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors

## <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>Aufgabe 1: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle
Bei dieser Aufgabe veröffentlichen Sie die Zertifikatvorlage.

### <a name="to-configure-the-certification-authority"></a>So konfigurieren Sie die Zertifizierungsstelle

1.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifikatvorlagen-Snap-In, um eine neue benutzerdefinierte Vorlage zu erstellen oder eine vorhandene Vorlage (z.B. die Vorlage „Benutzer“) zu kopieren und anschließend für die Verwendung mit PKCS zu bearbeiten.

    Für die Vorlage müssen Sie folgende Aktionen ausführen:

    -   Geben Sie einen aussagekräftigen **Vorlagenanzeigenamen** für die Vorlage ein.

    -   Wählen Sie auf der Registerkarte **Antragstellername** die Option **Informationen werden in der Anforderung angegeben**. (Sicherheit wird durch das Intune-Richtlinienmodul für NDES erzwungen.)

    -   Stellen Sie sicher, dass auf der Registerkarte **Erweiterungen** die **Beschreibung der Anwendungsrichtlinien** die **Clientauthentifizierung**umfasst.

        > [!IMPORTANT]
        > Bearbeiten Sie für iOS- und macOS-Zertifikatvorlagen auf der Registerkarte **Erweiterungen** die Option **Schlüsselverwendung**, und stellen Sie sicher, dass die Option **Signatur ist Ursprungsnachweis** nicht aktiviert ist.

2.  Prüfen Sie auf der Registerkarte **Allgemein** die **Gültigkeitsdauer** der Vorlage. In der Standardeinstellung verwendet Intune den in der Vorlage konfigurierten Wert. Sie haben jedoch die Möglichkeit, die Zertifizierungsstelle so zu konfigurieren, dass dem Antragsteller ermöglicht wird, einen anderen Wert anzugeben, den Sie dann in der Intune-Verwaltungskonsole festlegen können. Wenn Sie immer den in der Vorlage festgelegten Wert verwenden möchten, überspringen Sie den Rest dieses Schritts.

    > [!IMPORTANT]
    > iOS und macOS verwenden immer den in der Vorlage festgelegten Wert, unabhängig von anderen Konfigurationen, die Sie vornehmen.

    Um die Zertifizierungsstelle so zu konfigurieren, dass der Antragsteller die Gültigkeitsdauer festlegen kann, führen Sie auf der Zertifizierungsstelle die folgenden Befehle aus:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Verwenden Sie auf der ausstellenden Zertifizierungsstelle das Zertifizierungsstellen-Snap-In, um die Zertifikatvorlage zu veröffentlichen.

    a.  Wählen Sie den Knoten **Zertifikatvorlagen** aus, klicken Sie auf **Aktion**-&gt; **Neu** &gt; **Auszustellende Zertifikatvorlage**, und wählen Sie dann die Vorlage aus, die Sie in Schritt 2 erstellt haben.

    b.  Überprüfen Sie, ob die Vorlage veröffentlicht wurde, indem Sie sie im Ordner **Zertifikatvorlagen** anzeigen.

4.  Stellen Sie auf dem Zertifizierungsstellencomputer sicher, dass der Computer, der den Intune Certificate Connector hostet, die Berechtigung „Registrieren“ hat, damit dieser auf die Vorlage zugreifen kann, die zum Erstellen des PKCS-Zertifikatprofils verwendet wurde. Legen Sie diese Berechtigung auf der Registerkarte **Sicherheit** in den Eigenschaften des Computers mit der Zertifizierungsstelle fest.

## <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>Aufgabe 2: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors
Im Rahmen dieser Aufgabe führen Sie die folgenden Aktionen aus:

Herunterladen, Installieren und Konfigurieren des Certificate Connectors

### <a name="to-enable-support-for-the-certificate-connector"></a>So aktivieren Sie die Unterstützung für den Zertifikatconnector

1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2.  Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Setup** > **Zertifizierungsstelle** aus.
2.  Wählen Sie unter **Schritt 1** die Option **Aktivieren** aus.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>So wird der Certificate Connector heruntergeladen, installiert und konfiguriert

1.  Wählen Sie auf dem Blatt **Geräte konfigurieren** die Option **Setup** > **Zertifizierungsstelle** aus.
2.  Wählen Sie **Certificate Connector herunterladen** aus.
2.  Nachdem der Download abgeschlossen ist, führen Sie das heruntergeladene Installationsprogramm (**ndesconnectorssetup.exe**) aus.
  Führen Sie das Installationsprogramm auf dem Computer aus, der eine Verbindung mit der Zertifizierungsstelle herstellen kann. Wählen Sie die Option „PKCS/PFX-Verteilung“ aus, und klicken Sie auf **Installieren**. Fahren Sie nach Abschluss der Installation mit dem Erstellen eines Zertifikatprofils fort, wie unter [Konfigurieren von Zertifikatprofilen](how-to-configure-certificates.md) beschrieben.

3.  Wenn Sie zur Eingabe des Clientzertifikats für den Certificate Connector aufgefordert werden, wählen Sie **Auswählen** aus, und wählen Sie das **Clientauthentifizierungszertifikat** aus, das Sie installiert haben.

    Nachdem Sie das Clientauthentifizierungszertifikat ausgewählt haben, wird erneut die Oberfläche **Clientzertifikat für den Microsoft Intune-Zertifikatconnector** angezeigt. Auch wenn das ausgewählte Zertifikat nicht angezeigt wird, klicken Sie auf **Weiter**, um die Eigenschaften des Zertifikats anzuzeigen. Wählen Sie **Weiter**, und klicken Sie anschließend **Installieren**.

4.  Nach Abschluss des Assistenten, jedoch vor dem Schließen des Assistenten, klicken Sie auf **Zertifikatconnector-Benutzeroberfläche starten**.

    > [!TIP]
    > Wenn Sie den Assistenten schließen, bevor Sie die Benutzeroberfläche des Zertifikatconnectors starten, können Sie sie mit dem folgenden Befehl erneut öffnen:
    >
    > **&lt;Installationspfad&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Gehen Sie auf der Benutzeroberfläche von **Zertifikatconnector** so vor:

    a. Klicken Sie auf **Anmelden**, und geben Sie die Anmeldeinformationen des Intune-Dienstadministrators oder eines Mandantenadministrators mit der globalen Administratorberechtigung ein.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Wählen Sie die Registerkarte **Erweitert** aus, und geben Sie anschließend die Anmeldeinformationen für ein Konto ein, das über die Berechtigung **Zertifikate ausstellen und verwalten** für die ausstellende Zertifizierungsstelle verfügt.

    c. Wählen Sie **Anwenden** aus.

    Sie können jetzt die Benutzeroberfläche des Zertifikatconnectors schließen.

6.  Öffnen Sie eine Eingabeaufforderung, und geben Sie **services.msc** ein. Drücken Sie anschließend die **EINGABETASTE**, führen Sie einen Rechtsklick auf **Intune-Connectordienst** aus, und wählen Sie **Neu starten** aus.

Um zu überprüfen, das der Dienst ausgeführt wird, öffnen Sie einen Browser, und geben Sie die folgenden URL ein. Es sollte ein **403** -Fehler zurückgegeben werden:

**http:// &lt;FQDN_des_NDES_Servers&gt;/certsrv/mscep/mscep.dll**

### <a name="next-steps"></a>Nächste Schritte
Sie sind jetzt bereit, Zertifikatprofile gemäß der Beschreibung in [Konfigurieren von Zertifikaten mit Microsoft Intune](how-to-configure-certificates.md) einzurichten.

