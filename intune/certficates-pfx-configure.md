---
title: Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune
titleSuffix: Intune on Azure
description: Erfahren Sie, wie Sie Ihre Infrastruktur konfigurieren und dann PKCS-Zertifikate mit Intune erstellen und zuweisen."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 305a4d79aa81bd599369e72bc0cb307fdf452643
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema erläutert, wie Sie Ihre Infrastruktur konfigurieren und dann PKCS-Zertifikatprofile mit Intune erstellen und zuweisen.

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
|**Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle**|Sie exportieren dies als **CER**-Datei von der ausstellenden Zertifizierungsstelle oder von einem Gerät, das der ausstellenden Zertifizierungsstelle vertraut, und weisen es Geräten mithilfe des Zertifikatprofils der vertrauenswürdigen Zertifizierungsstelle zu.<br /><br />Sie verwenden für jede Betriebssystemplattform ein einzelnes Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ordnen es dem jeweiligen vertrauenswürdigen Stammzertifikatprofil zu, das Sie erstellen.<br /><br />Sie können bei Bedarf zusätzliche vertrauenswürdige Stammzertifizierungsstellenzertifikate verwenden. Sie können dies zum Beispiel vornehmen, um einer Zertifizierungsstelle eine Vertrauensstellung zu gewähren, die die Serverauthentifizierungszertifikate für Ihre WLAN-Zugriffspunkte signiert.|


## <a name="configure-your-infrastructure"></a>Konfigurieren der Infrastruktur
Bevor Sie Zertifikatprofile konfigurieren können, müssen Sie die folgenden Schritte ausführen. Diese Schritte setzen Kenntnisse in Windows Server 2012 R2 und Active Directory-Zertifikatdiensten voraus:

- **Schritt 1**: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle
- **Schritt 2**: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>Schritt 1: Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle

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

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>Schritt 2: Aktivieren, Installieren und Konfigurieren des Intune Certificate Connectors
In diesem Schritt führen Sie die folgenden Aktionen aus:

- Aktivieren der Unterstützung für den Certificate Connector
- Herunterladen, Installieren und Konfigurieren des Certificate Connectors

### <a name="to-enable-support-for-the-certificate-connector"></a>So aktivieren Sie die Unterstützung für den Certificate Connector

1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2.  Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Setup** > **Zertifizierungsstelle** aus.
2.  Wählen Sie unter **Schritt 1** die Option **Aktivieren** aus.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>So wird der Certificate Connector heruntergeladen, installiert und konfiguriert

1.  Wählen Sie auf dem Blatt **Geräte konfigurieren** die Option **Setup** > **Zertifizierungsstelle** aus.
2.  Wählen Sie **Certificate Connector herunterladen** aus.
2.  Nachdem der Download abgeschlossen ist, führen Sie das heruntergeladene Installationsprogramm (**ndesconnectorssetup.exe**) aus.
  Führen Sie das Installationsprogramm auf dem Computer aus, der eine Verbindung mit der Zertifizierungsstelle herstellen kann. Wählen Sie die Option „PKCS/PFX-Verteilung“ aus, und klicken Sie auf **Installieren**. Fahren Sie nach Abschluss der Installation mit dem Erstellen eines Zertifikatprofils fort, wie unter [Konfigurieren von Zertifikatprofilen](certificates-configure.md) beschrieben.

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


### <a name="how-to-create-a-pkcs-certificate-profile"></a>So erstellen Sie ein PKCS-Zertifikatprofil

Wählen Sie im Azure-Portal die Workload **Konfigurieren von Geräten** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das PKCS-Zertifikatprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für dieses PKCS-Zertifikat aus:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **PKCS-Zertifikat** aus.
7. Konfigurieren Sie auf dem Blatt **PKCS-Zertifikat** die folgenden Einstellungen:
    - **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
    - **Gültigkeitsdauer des Zertifikats:** Wenn Sie den Befehl **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** für die ausstellende Zertifizierungsstelle ausgeführt haben, die eine benutzerdefinierte Gültigkeitsdauer ermöglicht, können Sie die verbleibende Dauer bis zum Ablauf des Zertifikats angeben.<br>Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.
    - **Schlüsselspeicheranbieter** (Windows 10): Geben Sie an, wo der Schlüssel für das Zertifikat gespeichert wird. Wählen Sie einen der folgenden Werte aus:
        - **Bei TPM-KSP (Trusted Platform Module) registrieren, falls vorhanden, andernfalls Software-KSP**
        - **Bei TPM-KSP (Trusted Platform Module) registrieren, andernfalls Fehler**
        - **Bei Passport registrieren, andernfalls Fehler (Windows 10 und höher)**
        - **Bei Software-KSP registrieren**
    - **Zertifizierungsstelle**: Eine Unternehmenszertifizierungsstelle (Certification Authority; CA), die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. Anleitungen zum Einrichten einer Zertifizierungsstelle finden Sie unter [Installieren der Zertifizierungsstelle](http://technet.microsoft.com/library/jj125375.aspx). Wenn die Zertifizierungsstelle unter Windows Server 2008 R2 ausgeführt wird, müssen Sie [den Hotfix von KB2483564 installieren](http://support.microsoft.com/kb/2483564/).
    - **Name der Zertifizierungsstelle**: Geben Sie den Namen Ihrer Zertifizierungsstelle ein.
    - **Name der Zertifikatvorlage:** Geben Sie den Namen der Zertifikatvorlage ein, der im Registrierungsdienst für Netzwerkgeräte konfiguriert ist und der einer ausstellenden Zertifizierungsstelle hinzugefügt wurde.
    Stellen Sie sicher, dass der Name genau mit einer der in der Registrierung des Servers mit dem Registrierungsdienst für Netzwerkgeräte aufgeführten Zertifikatvorlagen übereinstimmt. Achten Sie darauf, dass Sie den Namen der Zertifikatvorlage und nicht den Anzeigenamen der Zertifikatvorlage angeben. 
    Navigieren Sie zu dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP“, um die Namen von Zertifikatvorlagen zu suchen. Die Zertifikatvorlagen werden als Werte für **EncryptionTemplate**, **GeneralPurposeTemplate**und **SignatureTemplate**aufgeführt. Standardmäßig ist der Wert für die drei Zertifikatvorlagen IPSECIntermediateOffline. Dieser Wert entspricht dem Anzeigenamen **IPSec (Offlineanforderung)**. 
    - **Format des Antragstellernamens:** Wählen Sie in der Liste aus, wie Intune den Antragstellernamen in der Zertifikatanforderung automatisch erstellt. Wenn das Zertifikat für einen Benutzer bestimmt ist, können Sie auch die E-Mail-Adresse des Benutzers im Antragstellernamen einschließen. Wählen Sie aus:
        - **Nicht konfiguriert**
        - **Allgemeiner Name**
        - **Allgemeiner Name einschließlich E-Mail-Adresse**
        - **Allgemeiner Name als E-Mail-Adresse**
    - **Alternativer Antragstellername:** Geben Sie an, wie die Werte für den alternativen Antragstellernamen (Subject Alternative Name, SAN) in der Zertifikatanforderung von Intune automatisch erstellt werden sollen. Beispiel: Wenn Sie einen Benutzerzertifikattyp ausgewählt haben, könnten Sie in den alternativen Antragstellernamen den Benutzerprinzipalnamen (User Principal Name, UPN) aufnehmen. Wenn das Clientzertifikat für die Authentifizierung bei einem Netzwerkrichtlinienserver verwendet wird, legen Sie den alternativen Antragstellernamen auf den Benutzerprinzipalnamen fest. 
    Sie können auch **Benutzerdefiniertes Azure AD-Attribut** auswählen. Wenn Sie diese Option auswählen, wird ein weiteres Dropdownfeld angezeigt. Im Dropdownfeld **Benutzerdefiniertes Azure AD-Attribut** finden Sie die Option **Abteilung**. Wenn Sie diese Option auswählen und die Abteilung in Azure AD nicht identifiziert wurde, wird das Zertifikat nicht ausgestellt. Um dieses Problem zu lösen, identifizieren Sie die Abteilung, und speichern Sie die Änderungen. Beim nächsten Einchecken des Geräts ist das Problem gelöst, und das Zertifikat wird ausgestellt. Die Notation für dieses Feld ist ASN.1. 
    - **Erweiterte Schlüsselverwendung:** (Android) Wählen Sie **Hinzufügen** aus, um Werte für den beabsichtigten Zweck des Zertifikats hinzuzufügen. In den meisten Fällen erfordert das Zertifikat **Clientauthentifizierung** , damit der Benutzer bzw. das Gerät auf einem Server authentifiziert werden kann. Sie können jedoch nach Bedarf weitere Schlüsselverwendungen hinzufügen. 
    - **Stammzertifikat:** (Android) Wählen Sie ein Profil für ein Stamm-Zertifizierungsstellenzertifikat aus, das Sie zuvor konfiguriert und dem Benutzer oder Gerät zugewiesen haben. Dieses Zertifizierungsstellenzertifikat muss das Stammzertifikat für die Zertifizierungsstelle sein, die das Zertifikat ausstellt, das Sie in diesem Zertifikatprofil konfigurieren. Dies ist das vertrauenswürdige Zertifikatprofil, das Sie zuvor erstellt haben.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="how-to-assign-the-certificate-profile"></a>Zuweisen des Zertifikatprofils

Beachten Sie Folgendes, bevor Sie Gruppen Zertifikatprofile zuweisen:

- Wenn Sie Gruppen Zertifikatprofile zuweisen, wird die Zertifikatsdatei aus dem Profil des vertrauenswürdigen Zertifizierungsstellenzertifikats auf dem Gerät installiert. Das Gerät verwendet das PKCS-Zertifikatprofil, um eine Zertifikatanforderung zu erstellen.
- Zertifikatprofile werden nur auf den Geräten installiert, auf denen die beim Erstellen des Profils verwendete Plattform ausgeführt wird.
- Sie können Zertifikatprofile zu Benutzer- oder Gerätesammlungen zuweisen.
- Damit Zertifikate möglichst schnell nach der Geräteregistrierung auf Geräten veröffentlicht werden können, weisen Sie das Zertifikatprofil besser einer Benutzergruppe zu (nicht einer Gerätegruppe). Wenn Sie es einer Gerätegruppe zuweisen, muss eine vollständige Geräteregistrierung stattfinden, bevor das Gerät Richtlinien empfängt.
- Obwohl Sie jedes Profil separat zuweisen, müssen Sie auch die vertrauenswürdige Stammzertifizierungsstelle und das PKCS-Profil zuweisen. Andernfalls tritt bei der PKCS-Zertifikatrichtlinie ein Fehler auf.

Informationen zum Zuweisen von Profilen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
