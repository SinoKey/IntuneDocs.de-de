---
title: Konfigurieren von Zertifikaten mit Intune
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit Intune Zertifikate erstellen und zuweisen, mit denen Sie WLAN-, VPN- und andere Verbindungen schützen können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 364534ad788466f8b268b4091decee5326b94163
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Konfigurieren von Zertifikaten in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Wenn Sie Benutzern den Zugriff auf Unternehmensressourcen über VPN-, WLAN- oder E-Mail-Profile gestatten, können Sie diesen Zugriff mit einem Zertifikat schützen, das auf jedem Benutzergerät installiert wird. Der grundlegende Workflow sieht folgendermaßen aus:

1. Stellen Sie sicher, dass Sie die richtige Zertifikatinfrastruktur eingerichtet haben. Sie können [SCEP-Zertifikate](configure-certificate-infrastructure-for-scep.md) und [PKCS-Zertifikate](configure-certificate-infrastructure-for-pfx.md) verwenden.
2. Installieren Sie auf jedem Gerät ein Stammzertifikat oder ein Zertifikat einer Zwischenzertifizierungsstelle, damit das Gerät die Rechtmäßigkeit Ihrer Zertifizierungsstelle erkennt. Erstellen Sie zu diesem Zweck ein **vertrauenswürdiges Zertifikatprofil** und weisen Sie es zu. Wenn Sie dieses Profil zuweisen, wird das Stammzertifikat von den Geräten, die Sie mit Intune verwalten, angefordert und empfangen. Sie müssen für jede Plattform ein eigenes Profil erstellen. Vertrauenswürdige Zertifikatprofile sind für folgende Plattformen verfügbar:
    - iOS 8.0 und höher
    - macOS 10.9 und höher
    - Android 4.0 und höher <!--Android for Work --->
    - Windows 8.1 und höher
    - Windows Phone 8.1 und höher
    - Windows 10 und höher
3. Erstellen Sie Zertifikatprofile, damit Geräte ein Zertifikat für die Authentifizierung des VPN-, WLAN- und E-Mail-Zugriffs anfordern. Sie können ein **PKCS**- oder ein **SCEP**-Zertifikatprofil für Geräte auf diesen Plattformen erstellen und bereitstellen:
    - iOS 8.0 und höher
    - Android 4,0 und höher
    - Android for Work
    - Windows 10 (Desktop und Mobile) und höher

    Ein SCEP-Zertifikatprofil können Sie nur bei folgenden Plattformen anwenden:

-     macOS 10.9 und höher
-     Windows Phone 8.1 und höher

Sie müssen für jede Geräteplattform ein eigenes Profil erstellen. Nachdem Sie das Profil erstellt haben, ordnen Sie es dem bereits erstellten vertrauenswürdigen Stammzertifikatprofil zu.

### <a name="further-considerations"></a>Weitere Überlegungen

- Wenn Sie über keine Unternehmenszertifizierungsstelle verfügen, müssen Sie eine erstellen.
- Wenn Sie sich basierend auf Ihren Geräteplattformen entschließen, das SCEP-Profil (Simple Certificate Enrollment Protocol) zu verwenden, müssen Sie auch einen NDES-Server (Network Device Enrollment Service) konfigurieren.
- Unabhängig davon, ob Sie SCEP- oder PKCS-Profile verwenden möchten, müssen Sie den Microsoft Intune Certificate Connector herunterladen und konfigurieren.

## <a name="before-you-start"></a>Vorbereitung


### <a name="if-you-want-to-use-scep-certificates"></a>Wenn Sie SCEP-Zertifikate verwenden möchten

Die erforderlichen Voraussetzungen finden Sie unter [Zertifikatinfrastruktur für SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### <a name="if-you-want-to-use-pkcs-certificates"></a>Wenn Sie PKCS-Zertifikate verwenden möchten

Die erforderlichen Voraussetzungen finden Sie unter [Zertifikatinfrastruktur für PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Aufgabe 1: Exportieren des Zertifikats der vertrauenswürdigen Stamm-CA
Exportieren Sie das Zertifikat vertrauenswürdigen Stammzertifizierungsstelle als **CER**-Datei aus der ausstellenden Zertifizierungsstelle oder von einem beliebigen Gerät, das die ausstellende Zertifizierungsstelle als vertrauenswürdig erachtet. Exportieren Sie auf keinen Fall den privaten Schlüssel.

Sie importieren dieses Zertifikat, wenn Sie ein vertrauenswürdiges Zertifikatprofil einrichten.

## <a name="task-2-create-trusted-certificate-profiles"></a>Aufgabe 2: Erstellen von vertrauenswürdigen Zertifikatprofilen
Sie müssen ein Profil mit einem vertrauenswürdigen Zertifikat erstellen, bevor Sie ein SCEP- oder PKCS-Zertifikatprofil erstellen können. Sie benötigen ein Profil mit einem vertrauenswürdigen Zertifikat und ein SCEP- oder PKCS-Profil für jede Geräteplattform.

### <a name="to-create-a-trusted-certificate-profile"></a>So erstellen Sie ein vertrauenswürdiges Zertifikatprofil

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das vertrauenswürdige Zertifikatprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für das vertrauenswürdige Zertifikat aus. Derzeit können Sie eine der folgenden Plattformen für die Einstellungen für Geräteeinschränkungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Vertrauenswürdiges Zertifikat** aus.
7. Navigieren Sie zu dem Zertifikat, das Sie in Aufgabe 1 gespeichert haben, und klicken Sie dann auf **OK**.
8. Wählen Sie (nur bei Windows 8.1- und Windows 10-Geräten) den **Zielspeicher** für das vertrauenswürdige Zertifikat aus:
    - **Computerzertifikatspeicher – Stamm**
    - **Computerzertifikatspeicher – Zwischenspeicher**
    - **Benutzerzertifikatspeicher – Zwischenspeicher**
8. Klicken Sie zum Abschluss auf **OK**. Navigieren Sie, wenn Sie fertig sind, zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md) nach.


> [!Note]
> Android-Geräte zeigen eine Benachrichtigung an, dass ein Drittanbieter ein vertrauenswürdiges Zertifikat installiert hat.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Aufgabe 3: Erstellen von SCEP- oder PKCS-Zertifikatprofilen
Nachdem Sie ein Profil des vertrauenswürdigen Zertifikats erstellt haben, erstellen Sie SCEP- oder PKCS-Zertifikatprofile für jede Plattform, die Sie verwenden möchten. Wenn Sie ein SCEP-Zertifikatprofil erstellen, müssen Sie ein vertrauenswürdiges Zertifikatprofil für dieselbe Plattform angeben. Auf diese Weise werden die beiden Zertifikatprofile verknüpft. Sie müssen jedes Profil trotzdem separat zuweisen.

### <a name="to-create-an-scep-certificate-profile"></a>So erstellen Sie ein SCEP-Zertifikatprofil

1. Wählen Sie im Azure-Portal die Workload **Konfigurieren von Geräten** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das SCEP-Zertifikatprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für dieses SCEP-Zertifikat aus. Derzeit können Sie eine der folgenden Plattformen für die Einstellungen für Geräteeinschränkungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **SCEP-Zertifikat** aus.
7. Konfigurieren Sie auf dem Blatt **SCEP-Zertifikat** die folgenden Einstellungen:
    - **Gültigkeitsdauer des Zertifikats:** Wenn Sie den Befehl **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** für die ausstellende Zertifizierungsstelle ausgeführt haben, die eine benutzerdefinierte Gültigkeitsdauer ermöglicht, können Sie die verbleibende Dauer bis zum Ablauf des Zertifikats angeben.<br>Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein. 
    - **Schlüsselspeicheranbieter (KSP):** (Windows Phone 8.1, Windows 8.1, Windows 10) Geben Sie an, wo der Schlüssel für das Zertifikat gespeichert wird. Wählen Sie einen der folgenden Werte aus:
        - **Bei TPM-KSP (Trusted Platform Module) registrieren, falls vorhanden, andernfalls Software-KSP**
        - **Bei TPM-KSP (Trusted Platform Module) registrieren, andernfalls Fehler**
        - **Bei Passport registrieren, andernfalls Fehler (Windows 10 und höher)**
        - **Bei Software-KSP registrieren**
    - **Format des Antragstellernamens:** Wählen Sie in der Liste aus, wie Intune den Antragstellernamen in der Zertifikatanforderung automatisch erstellt. Wenn das Zertifikat für einen Benutzer bestimmt ist, können Sie auch die E-Mail-Adresse des Benutzers im Antragstellernamen einschließen. Wählen Sie aus:
        - **Nicht konfiguriert**
        - **Allgemeiner Name**
        - **Allgemeiner Name einschließlich E-Mail-Adresse**
        - **Allgemeiner Name als E-Mail-Adresse**
    - **Alternativer Antragstellername:** Geben Sie an, wie die Werte für den alternativen Antragstellernamen (Subject Alternative Name, SAN) in der Zertifikatanforderung von Intune automatisch erstellt werden sollen. Beispiel: Wenn Sie einen Benutzerzertifikattyp ausgewählt haben, könnten Sie in den alternativen Antragstellernamen den Benutzerprinzipalnamen (User Principal Name, UPN) aufnehmen. Wenn das Clientzertifikat für die Authentifizierung bei einem Netzwerkrichtlinienserver verwendet werden soll, müssen Sie den alternativen Antragstellernamen auf den Benutzerprinzipalnamen festlegen. 
    - **Schlüsselverwendung:** Geben Sie Schlüsselverwendungsoptionen für das Zertifikat an. Sie können unter folgenden Optionen wählen: 
        - **Schlüsselverschlüsselung:** Lässt den Schlüsselaustausch nur zu, wenn der Schlüssel verschlüsselt ist. 
        - **Digitale Signatur:** Lässt den Schlüsselaustausch nur zu, wenn der Schlüssel durch eine digitale Signatur geschützt ist. 
    - **Schlüsselgröße (Bits):** Wählen Sie die Anzahl der Bits aus, die im Schlüssel enthalten sein sollen. 
    - **Hashalgorithmus:** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) Wählen Sie einen der verfügbaren Hashalgorithmustypen aus, der für dieses Zertifikat verwendet werden soll. Wählen Sie die höchste Sicherheitsebene aus, die die verbundenen Geräten unterstützen. 
    - **Stammzertifikat:** Wählen Sie ein Profil für ein Stamm-Zertifizierungsstellenzertifikat aus, das Sie zuvor konfiguriert und dem Benutzer oder Gerät zugewiesen haben. Dieses Zertifizierungsstellenzertifikat muss das Stammzertifikat für die Zertifizierungsstelle sein, die das Zertifikat ausstellt, das Sie in diesem Zertifikatprofil konfigurieren. 
    - **Erweiterte Schlüsselverwendung:** Wählen Sie **Hinzufügen** aus, um Werte für den beabsichtigten Zweck des Zertifikats hinzuzufügen. In den meisten Fällen erfordert das Zertifikat **Clientauthentifizierung** , damit der Benutzer bzw. das Gerät auf einem Server authentifiziert werden kann. Sie können jedoch nach Bedarf weitere Schlüsselverwendungen hinzufügen. 
    - **Registrierungseinstellungen**
        - **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
        - **SCEP-Server-URLs:** Geben Sie eine oder mehrere URLs für die NDES-Server an, die Zertifikate über SCEP ausstellen. 
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

Befolgen Sie die Anweisungen auf der Profilkonfigurationsseite, um die SCEP-Zertifikatprofileinstellungen zu konfigurieren.
>[!Note]
> Nur bei iOS-Geräten: Wählen Sie unter „Format des Antragstellernamens“ die Option „Benutzerdefiniert“ aus, um ein benutzerdefiniertes Format für den Antragstellernamen einzugeben.
> Die derzeit unterstützten beiden Variablen für das benutzerdefinierte Format sind **Allgemeiner Name (CN)** und **E-Mail (E)**. Durch eine Kombination dieser Variablen mit statischen Zeichenfolgen können Sie ein benutzerdefiniertes Format wie dieses für den Antragstellernamen erstellen: **CN={{Benutzername}},E={{E-Mail-Adresse}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** In diesem Beispiel haben Sie ein Format für den Antragstellernamen erstellt, das neben den Variablen „CN“ und „E“ noch Zeichenfolgen für die Organisationseinheit, den Standort, den Bundesstaat und das Land verwendet. In [diesem Thema](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) werden die **CertStrToName**-Funktion und die unterstützten Zeichenfolgen gezeigt.


### <a name="to-create-a-pkcs-certificate-profile"></a>So erstellen Sie ein PKCS-Zertifikatprofil

Wählen Sie im Azure-Portal die Workload **Konfigurieren von Geräten** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das PKCS-Zertifikatprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für dieses PKCS-Zertifikat aus:
    - **Android**
    - **iOS**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **PKCS-Zertifikat** aus.
7. Konfigurieren Sie auf dem Blatt **PKCS-Zertifikat** die folgenden Einstellungen:
    - **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
    - **Gültigkeitsdauer des Zertifikats:** Wenn Sie den Befehl **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** für die ausstellende Zertifizierungsstelle ausgeführt haben, die eine benutzerdefinierte Gültigkeitsdauer ermöglicht, können Sie die verbleibende Dauer bis zum Ablauf des Zertifikats angeben.<br>Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.
    - **Schlüsselspeicheranbieter (KSP)** (Windows 10) -
    - **Zertifizierungsstelle** -
    - **Name der Zertifizierungsstelle** -
    - **Name der Zertifikatvorlage:** Geben Sie den Namen der Zertifikatvorlage ein, der im Registrierungsdienst für Netzwerkgeräte konfiguriert ist und der einer ausstellenden Zertifizierungsstelle hinzugefügt wurde.
    Stellen Sie sicher, dass der Name genau mit einer der in der Registrierung des Servers mit dem Registrierungsdienst für Netzwerkgeräte aufgeführten Zertifikatvorlagen übereinstimmt. Achten Sie darauf, dass Sie den Namen der Zertifikatvorlage und nicht den Anzeigenamen der Zertifikatvorlage angeben. 
    Navigieren Sie zu dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP“, um die Namen von Zertifikatvorlagen zu suchen. Die Zertifikatvorlagen werden als Werte für **EncryptionTemplate**, **GeneralPurposeTemplate**und **SignatureTemplate**aufgeführt. Standardmäßig ist der Wert für die drei Zertifikatvorlagen IPSECIntermediateOffline. Dieser Wert entspricht dem Anzeigenamen **IPSec (Offlineanforderung)**. 
    - **Format des Antragstellernamens:** Wählen Sie in der Liste aus, wie Intune den Antragstellernamen in der Zertifikatanforderung automatisch erstellt. Wenn das Zertifikat für einen Benutzer bestimmt ist, können Sie auch die E-Mail-Adresse des Benutzers im Antragstellernamen einschließen. Wählen Sie aus:
        - **Nicht konfiguriert**
        - **Allgemeiner Name**
        - **Allgemeiner Name einschließlich E-Mail-Adresse**
        - **Allgemeiner Name als E-Mail-Adresse**
    - **Alternativer Antragstellername:** Geben Sie an, wie die Werte für den alternativen Antragstellernamen (Subject Alternative Name, SAN) in der Zertifikatanforderung von Intune automatisch erstellt werden sollen. Beispiel: Wenn Sie einen Benutzerzertifikattyp ausgewählt haben, könnten Sie in den alternativen Antragstellernamen den Benutzerprinzipalnamen (User Principal Name, UPN) aufnehmen. Wenn das Clientzertifikat für die Authentifizierung bei einem Netzwerkrichtlinienserver verwendet werden soll, müssen Sie den alternativen Antragstellernamen auf den Benutzerprinzipalnamen festlegen.
    - **Erweiterte Schlüsselverwendung:** (Android) Wählen Sie **Hinzufügen** aus, um Werte für den beabsichtigten Zweck des Zertifikats hinzuzufügen. In den meisten Fällen erfordert das Zertifikat **Clientauthentifizierung** , damit der Benutzer bzw. das Gerät auf einem Server authentifiziert werden kann. Sie können jedoch nach Bedarf weitere Schlüsselverwendungen hinzufügen. 
    - **Stammzertifikat:** (Android) Wählen Sie ein Profil für ein Stamm-Zertifizierungsstellenzertifikat aus, das Sie zuvor konfiguriert und dem Benutzer oder Gerät zugewiesen haben. Dieses Zertifizierungsstellenzertifikat muss das Stammzertifikat für die Zertifizierungsstelle sein, die das Zertifikat ausstellt, das Sie in diesem Zertifikatprofil konfigurieren.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="task-4-assign-certificate-profiles"></a>Aufgabe 4: Bereitstellen von Zertifikatprofilen

Beachten Sie Folgendes, bevor Sie Gruppen Zertifikatprofile zuweisen:

- Wenn Sie Gruppen Zertifikatprofile zuweisen, wird die Zertifikatsdatei aus dem Profil des vertrauenswürdigen Zertifizierungsstellenzertifikats auf dem Gerät installiert. Das Gerät verwendet das SCEP- oder PKCS-Zertifikatprofil, um eine Zertifikatanforderung zu erstellen.
- Zertifikatprofile werden nur auf den Geräten installiert, auf denen die beim Erstellen des Profils verwendete Plattform ausgeführt wird.
- Sie können Zertifikatprofile für Benutzer- oder Gerätesammlungen bereitstellen.
- Damit Zertifikate möglichst schnell nach deren Registrierung auf Geräten veröffentlicht werden können, stellen Sie das Zertifikatprofil lieber für eine Benutzergruppe bereit (und nicht für eine Gerätegruppe). Wenn Sie es für eine Gerätegruppe bereitstellen, muss eine vollständige Geräteregistrierung stattfinden, bevor das Gerät Richtlinien empfängt.
- Obwohl Sie jedes Profil separat bereitstellen, müssen Sie auch die vertrauenswürdige Stamm-CA und die SCEP- oder PKCS-Profile bereitstellen. Andernfalls schlägt die SCEP- oder PKCS-Zertifikatrichtlinie fehl.

## <a name="next-steps"></a>Nächste Schritte
Allgemeine Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen](how-to-assign-device-profiles.md).

