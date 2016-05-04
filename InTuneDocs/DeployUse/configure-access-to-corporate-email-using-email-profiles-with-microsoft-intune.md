---
title: Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
author: Nbigman
---
# Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune
Einstellungen von e-Mail-Profilen können verwendet werden, e-Mail-Zugriff für bestimmte e-Mail-Clients auf mobilen Geräten konfigurieren.   Die meisten mobile Plattformen enthalten eine *systemeigene* e-Mail-Client, die als Teil des Betriebssystems enthalten ist.  Auf unterstützten Plattformen können von Microsoft Intune Benutzern Zugriff auf ihre e-Mails im Unternehmen über die persönlichen Geräten, ohne Setup ermöglichen die systemeigene e-Mail-Clients konfiguriert werden.  

IT-Administratoren oder Benutzer können Sie die alternative e-Mail-Clients, z. B. Microsoft Outlook für Android oder iOS installieren.  Diese e-Mail-Clients unterstützen möglicherweise keine e-Mail-Profile und können nicht mithilfe von Microsoft Intune-e-Mail-Profilen konfiguriert werden.  

Sie können e-Mail-Profile verwenden, den systemeigene e-Mail-Client auf die folgenden Gerätetypen zu konfigurieren:
-   Geräte unter Windows Phone 8 und höher
-   Geräte unter Windows 10 Mobile, Windows 10 Desktop und höher
-   Geräte unter iOS 7.1 und höher
-   Geräte unter Samsung KNOX Standard (4.0 oder höher)


Zusätzlich zum Konfigurieren eines e-Mail-Kontos auf dem Gerät können Sie die synchronisierungseinstellungen z. B. wie viele e-Mails synchronisiert werden sollen, und je nach Gerätetyp, der zu synchronisierenden Inhaltstypen konfigurieren.

## Sichere e-Mail-Profile
Sie können e-Mail-Profile, die mit einer der beiden Methoden sichern:

### Zertifikate
Wenn Sie das e-Mail-Profil erstellen, wählen Sie ein Profil, das Sie zuvor, in erstellt haben [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]. Dies wird als Identitätszertifikat bezeichnet und dient zur Authentifizierung für das Profil mit einem vertrauenswürdigen Zertifikat (oder eines Stammzertifikats), um sicherzustellen, dass das Gerät des Benutzers eine Verbindung herstellen darf. Das vertrauenswürdige Zertifikat wird auf dem Computer bereitgestellt, die e-Mail-Verbindung in der Regel die e-Mail-Server authentifiziert.

Weitere Informationen zum Erstellen und Verwenden von zertifikatprofilen in [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], finden Sie unter [ermöglichen den Zugriff auf Unternehmensressourcen mithilfe von zertifikatprofilen in Microsoft Intune](enable-access-to-company-resources-using-certificate-profiles-with-microsoft-intune.md).

### Benutzername und Kennwort
Der Benutzer wird an den e-Mail-Server durch Angabe seines Benutzernamens und Kennworts authentifiziert.

Das Kennwort ist nicht im E-Mail-Profil enthalten, sodass der Benutzer dieses beim Herstellen einer Verbindung zum E-Mail-System bereitstellen muss.

### Erstellen eines E-Mail-Profils

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com)auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie einen der folgenden Richtlinientypen:

    -   **E-Mail-Profil für Samsung KNOX Standard (4.0 oder höher)**

    -   **E-Mail-Profil (iOS 7.1 und höher)**

    -   **E-Mail-Profil (Windows Phone 8 und höher)**

    -   **E-Mail-Profil (Windows 10 Desktop und Windows 10 Mobile oder höher)**

    Sie können nur benutzerdefinierte E-Mail-Profilrichtlinien erstellen. Empfohlene Einstellungen sind nicht verfügbar.

    Weitere Informationen zum Erstellen und Bereitstellen von Richtlinien finden Sie unter der [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md) Thema.

3.  Verwenden Sie in der folgenden Tabelle können Sie die e-Mail-Profil zu konfigurieren:

    |Name der Einstellung|Weitere Informationen|
    |----------------|--------------------|
    |**Name**|Eindeutiger Name für das e-Mail-Profil.|
    |**Beschreibung**|Eine Beschreibung, die Ihnen helfen identifizieren, dieses Profil.|
    |**Host**|Der Hostname der Server Ihres Unternehmens, der den systemeigenen e-Mail-Dienst hostet.|
    |**Kontoname**|Der Anzeigename für das e-Mail-Konto, wird Benutzern auf ihren Geräten angezeigt.|
    |**Benutzername**|Wie der Benutzername für das e-Mail-Konto abgerufen wird. Wählen Sie **Benutzername** für einen lokalen Exchange-Server oder Select **Benutzerprinzipalname** für Office 365.|
    |**E-Mail-Adresse**|Wie die e-Mail-Adresse für den Benutzer auf jedem Gerät generiert wird. Wählen Sie **primäre SMTP-Adresse** melden Sie sich bei Exchange oder verwenden Sie die primäre SMTP-Adresse mit  **Benutzerprinzipalname** den vollständigen Benutzerprinzipalnamen als e-Mail-Adresse verwenden.|
    |**Authentifizierungsmethode** (Samsung KNOX und iOS)|Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als die Authentifizierungsmethode, die vom e-Mail-Profil verwendet wird.|
    |**Wählen Sie ein Clientzertifikat für die Clientauthentifizierung (Identitätszertifikat)** (Samsung KNOX und iOS)|Wählen Sie das zuvor erstellte SCEP-Clientzertifikat aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll. Weitere Informationen zur Verwendung von zertifikatprofilen in [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], finden Sie unter [Zertifikate in Microsoft Intune](certificates-in-microsoft-intune-for-securing-access-to-resources.md).<br /><br />Diese Option wird nur angezeigt, wenn die Authentifizierungsmethode **Zertifikate**.|
    |**S/MIME verwenden** (Samsung KNOX und iOS)|Ausgehende E-Mails werden mithilfe von S/MIME-Verschlüsselung gesendet.|
    |**Signaturzertifikat** (Samsung KNOX und iOS)|Wählen Sie das Signaturzertifikat aus, das zum Signieren von ausgehenden E-Mails verwendet werden soll.<br /><br />Diese Option wird nur angezeigt, wenn Sie auswählen, **mit S/MIME-**.|
    |**Anzahl der Tage für die E-Mail-Synchronisierung**|Die Anzahl der Tage von e-Mails, die Sie synchronisieren möchten oder wählen Sie **unbegrenzt** alle verfügbaren e-Mail-Nachrichten zu synchronisieren.|
    |**Synchronisierungszeitplan** (Samsung KNOX, Windows Phone 8 und höher, Windows 10)|Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden. Sie können auch auswählen, **Wenn Nachrichten eintreffen** die Daten synchronisiert, sobald es ankommt, oder **Manuelle**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.|
    |**SSL verwenden**|Verwendet SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.<br /><br />Für Geräte mit Samsung KNOX 4.0 oder höher, müssen Sie Ihr Exchange Server SSL-Zertifikat exportieren und als ein Android Trusted Certificate Profile in bereitstellen, [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]. [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] unterstützt nicht den Zugriff auf dieses Zertifikat, wenn es mit anderen Mitteln auf dem Exchange Server installiert ist.|
    |**Zu synchronisierender Inhaltstyp**|Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen.|


    > [!IMPORTANT]
    > If you have deployed an email profile and then wish to change the values for **host** or **Email address**, you must delete the existing email profile and create a new one with the required values.

4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## Nächste Schritte
Stellen Sie das E-Mail-Profil für eine oder mehrere Gruppen von Benutzern oder Geräten in Ihrem Unternehmen bereit. Nach der erfolgreichen Bereitstellung werden Benutzergeräte mit den richtigen Einstellungen auf e-Mails im Unternehmen bereitgestellt werden.

Weitere Informationen zum Bereitstellen von Richtlinien finden Sie unter [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md).

Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich **Dashboard** angezeigt.

> [!NOTE]
> Wenn Sie ein E-Mail-Profil von einem Gerät entfernen, bearbeiten Sie die Bereitstellung, und entfernen Sie alle Gruppen, in denen das Gerät Mitglied ist.

## Siehe auch
[Zertifikate in Microsoft Intune](certificates-in-microsoft-intune-for-securing-access-to-resources.md)


<!--HONumber=Mar16_HO4-->


