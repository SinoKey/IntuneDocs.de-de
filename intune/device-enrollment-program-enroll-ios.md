---
title: "Registrieren von iOS-Geräten – Programm zur Geräteregistrierung"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mithilfe des Programms zur Geräteregistrierung (Device Enrollment Program, DEP) registrieren."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f509f5332b2f8b5f6745816f8795a9a54c10ce2d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Einrichten der Registrierung von iOS-Geräten mithilfe des Programms zur Geräteregistrierung

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema unterstützt IT-Administratoren dabei, die iOS-Geräteregistrierung für Geräte zu aktivieren, die über das [Programm zur Geräteregistrierung (Device Enrollment Program, DEP)](https://deploy.apple.com) von Apple erworben wurden. Microsoft Intune kann ein Registrierungsprofil für Geräte, die über DEP erworben wurden, auch „drahtlos“ bereitstellen. Der Administrator muss nicht jedes einzelne verwaltete Gerät physisch konfigurieren. Ein DEP-Profil enthält Verwaltungseinstellungen, die während der Registrierung auf Geräte angewendet werden, einschließlich Optionen für den Setup-Assistenten.

Zur Aktivierung der DEP-Registrierung können Sie sowohl das Intune-Portal als auch das Apple DEP-Portal verwenden. Sie benötigen auch eine Liste oder Bestellnummer Ihrer DEP-Geräte, um sie Intune zur Verwaltung im Apple-Portal zuweisen zu können.

>[!NOTE]
>Die Registrierung mit DEP kann nicht mit dem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) verwendet werden.

**Schritte zum Aktivieren der Registrierungsprogramme von Apple**
1. [Abrufen eines Apple-DEP-Tokens und Zuweisen von Geräten](#get-the-apple-dep-certificate)
2. [Erstellen eines Anmeldungsprofils](#create-anapple-enrollment-profile)
3. [Synchronisieren von DEP-verwalteten Geräten](#sync-dep-managed-devices)
4. [Zuweisen des DEP-Profils zu Geräten](#assign-a-dep-profile-to-devices)
5. [Verteilen von Geräten an Benutzer](#distribute-devices-to-users)

## <a name="get-the-apple-dep-token"></a>Abrufen des Apple-DEP-Tokens

Bevor Sie unternehmenseigene iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) registrieren können, benötigen Sie eine DEP-Tokendatei (P7M) von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profilen Geräte zuweisen.

> [!NOTE]
> Wenn Ihr Intune-Mandant von der klassischen Intune-Konsole zum Azure-Portal migriert wurde, und Sie haben ein Apple-DEP-Token aus der Intune-Verwaltungskonsole während des Migrationszeitraums gelöscht, kann das DEP-Token möglicherweise in Ihrem Intune-Konto wiederhergestellt worden sein. Sie können das DEP-Token erneut aus dem Azure-Portal löschen.

**Voraussetzungen**
- [Apple-MDM-Push-Zertifikat](apple-mdm-push-certificate-get.md)
- Registrierung für die Teilnahme am [Apple-Programm zur Geräteregistrierung](http://deploy.apple.com) durchgeführt

**Schritt 1: Laden Sie ein Intune-Zertifikat mit öffentlichem Schlüssel herunter, das zum Erstellen eines Apple-DEP-Tokens erforderlich ist.**<br>
1. Wählen Sie im Intune-Portal die Optionen **Geräteregistrierung**, **Apple-Registrierung** und dann **Registrierungsprogrammtoken** aus.
![Screenshot des Bereichs „Registrierungsprogrammtoken“ im Arbeitsbereich „Apple-Zertifikate“](./media/enrollment-program-token-add.png)
2. Wählen Sie **Laden Sie Ihr Zertifikat mit öffentlichem Schlüssel herunter** aus, um die Verschlüsselungsschlüsseldatei (PEM) herunterzuladen und lokal zu speichern. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.
![Screenshot des Bereichs „Registrierungsprogrammtoken“ im Arbeitsbereich „Apple-Zertifikate“ zum Herunterladen des öffentlichen Schlüssels](./media/enrollment-program-token-download.png)

**Schritt 2: Erstellen Sie ein Apple-DEP-Token und laden Sie es herunter.**<br>
Wählen Sie **Create a token via Apple's Device Enrollment Program** (Token über das Programm zur Geräteregistrierung von Apple erstellen) aus, um das Portal des Bereitstellungsprogramms von Apple zu öffnen. Melden Sie sich mit der Apple-ID Ihres Unternehmens an. Diese Apple-ID kann später zum Erneuern Ihres DEP-Token verwendet werden.
  ![Screenshot des Bereichs „Registrierungsprogrammtoken“ im Arbeitsbereich „Apple-Zertifikate“](./media/enrollment-program-token-create.png)

  ![Screenshot des Bereichs „Registrierungsprogrammtoken“ im Arbeitsbereich „Apple-Zertifikate“ zum Herunterladen des öffentlichen Schlüssels](./media/enrollment-program-token-sign.png)
   1.  Wählen Sie im [Portal des Bereitstellungsprogramms](https://deploy.apple.com) von Apple die Option **Erste Schritte** für das **Programm zur Geräteregistrierung** aus.
   ![Screenshot des Registrierungsprogramms bei Klick auf „Erste Schritte“ für das Programm zur Geräteregistrierung](./media/enrollment-program-token-started.png)
   2. Wählen Sie auf der Seite **Server verwalten** die Option **MDM-Server hinzufügen** aus.
   3. Geben Sie den **MDM-Servernamen** ein, und wählen Sie anschließend **Weiter** aus. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.

   ![Screenshot zum Hinzufügen eines MDM-Servernamens für DEP und Klick auf „Weiter“.](./media/enrollment-program-token-add-server.png)
   4.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet, und die Meldung **Laden Sie Ihren öffentlichen Schlüssel hoch** wird angezeigt. Wählen Sie **Datei auswählen** aus, um die PEM-Datei hochzuladen, und wählen Sie anschließend **Weiter** aus.
   ![Screenshot der Schaltfläche der öffentlichen Schlüsseldatei und Klick auf „Weiter“](./media/enrollment-program-token-choose-file.png)
   4.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und wählen Sie anschließend **Fertig** aus.
   ![Screenshot der Schaltfläche der öffentlichen Schlüsseldatei und Klick auf „Weiter“](./media/enrollment-program-token-your-token.png)
   5. Wechseln Sie zu **Bereitstellungsprogramme** &gt; **Programm zur Geräteregistrierung** &gt; **Geräte verwalten**.
   6. Geben Sie unter **Geräte auswählen nach** an, wie die Geräte identifiziert werden sollen:
    - **Seriennummer**
    - **Reihenfolge**
    - **Upload der CSV-Datei**

   ![Screenshot bei Festlegen von „Geräte auswählen nach“ auf „Seriennummer“, der Einstellung „Aktion auswählen“ auf „Zu Server zuweisen“ und der Auswahl des Servernamens.](./media/enrollment-program-token-specify-serial.png)

   7. Wählen Sie unter **Aktion auswählen** die Option **Zu Server zuweisen** aus. Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; aus, und klicken Sie dann auf **OK**. Das Apple-Portal weist die angegebenen Geräte dem Intune-Server für die Verwaltung zu und zeigt dann **Zuweisung abgeschlossen** an.

   Wechseln Sie im Apple-Portal zu **Bereitstellungsprogramme** &gt; **Programm zur Geräteregistrierung** &gt; **Zuweisungsverlauf anzeigen**, um eine Liste der Geräte und ihre MDM-Server-Zuordnung anzuzeigen.

**Schritt 3: Geben Sie die zum Erstellen Ihres Registrierungsprogrammtokens verwendete Apple-ID ein.**<br>Geben Sie im Intune-Portal für die zukünftige Verwendung Ihre Apple-ID an. Verwenden Sie diese ID zur Erneuerung Ihres Registrierungsprogrammtokens, damit Sie nicht alle Geräte erneut registrieren müssen.
![Screenshot der Angabe der Apple-ID zur Erstellung des Registrierungsprogrammtokens und Navigieren zu diesem Token](./media/enrollment-program-token-apple-id.png)
**Schritt 4. Navigieren Sie zu Ihrem Registrierungsprogrammtoken, das hochgeladen werden soll.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird. Intune führt eine automatische Synchronisierung mit Apple durch, um Ihr Registrierungsprogrammkonto anzuzeigen.

## <a name="create-an-apple-enrollment-profile"></a>Erstellen eines Apple-Registrierungsprofils

Ein Geräteregistrierungsprofil definiert die Einstellungen, die während der Registrierung auf eine Gruppe von Geräten angewendet werden.

1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
2. Wählen Sie unter **Apple-Registrierungsprogramm** die Option **Profile des Registrierungsprogramms** aus, und wählen Sie dann auf dem Blatt **Profile des Registrierungsprogramms** die Option **Erstellen** aus.
![Screenshot des ausgewählten Links „Erstellen“ zum Erstellen eines neuen Profils des Registrierungsprogramms](./media/enrollment-program-profile-create.png)
3. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen **Namen** und eine **Beschreibung** für das Profil zu administrativen Zwecken ein. Benutzer können diese Informationen nicht sehen.
![Screenshot der Angabe von „Name“ und „Beschreibung“ sowie der Auswahl „Mit Benutzeraffinität registrieren“ für ein neues Profil des Registrierungsprogramms](./media/enrollment-program-profile-name.png)
Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

 - **Mit Benutzeraffinität registrieren:** Ein Benutzer muss während der Installation Geräten zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Wählen Sie die **Benutzeraffinität** für Geräte aus, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie z.B. die Installation von Apps nutzen zu können.

<<<<<<< HEAD
 > [!NOTE]
 > Mehrstufige Authentifizierung (Multifactor authentication, MFA) funktioniert nicht während der Registrierung auf Geräten mit Benutzeraffinität, die mit einem Registrierungsprogramm verwaltet werden. Nach der Registrierung funktioniert die MFA auf diesen Geräten wie erwartet. Neue Benutzer, die bei der ersten Anmeldung ihr Kennwort ändern müssen, können während der Registrierung auf den Geräten nicht aufgefordert werden. Außerdem werden Benutzer, deren Kennwörter abgelaufen sind, während der Registrierung nicht aufgefordert, ihr Kennwort zurückzusetzen; sie müssen ihr Kennwort von einem anderen Gerät aus zurücksetzen.

 >[!NOTE]
 >Für die Verwaltung von Registrierungsprogrammen mit Benutzeraffinität muss der [Endpunkt WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) aktiviert sein, um Benutzertoken anzufordern. [Erfahren Sie mehr über WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
=======
    >[!NOTE]
    >Für DEP mit Benutzeraffinität muss der [Endpunkt WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) aktiviert sein, um Benutzertoken anzufordern. [Erfahren Sie mehr über WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
>>>>>>> 0c3fe0dee88e8ef4d8ad8ad28c0f8957831dd5b3

 - **Ohne Benutzeraffinität registrieren:** Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

4. Wählen Sie **Geräteverwaltungseinstellungen** aus, um die folgenden Profileinstellungen zu konfigurieren: ![Screenshot der Verwaltungsmodi „Überwacht“, „Registrierung gesperrt“ und „Kopplung zulassen“ mit der Auswahl „Alle verweigern“ und nicht verfügbare Apple Configurator-Zertifikate für ein neues Profil des Registrierungsprogramms](./media/enrollment-program-profile-mode.png)
    - **Überwacht:** Dieser Verwaltungsmodus ermöglicht weitere Verwaltungsoptionen und deaktiviert standardmäßig die Aktivierungssperre. Wenn Sie das Kontrollkästchen nicht aktivieren, stehen Ihnen nur beschränkte Verwaltungsfunktionen zur Verfügung.

    - **Registrierung gesperrt:**: (Erfordert den Vorbereitungsmodus „Überwacht“) Deaktiviert iOS-Einstellungen, die das Entfernen des Verwaltungsprofils zulassen könnten. Wenn Sie dieses Kontrollkästchen nicht aktivieren, kann das Verwaltungsprofil aus dem Menü „Einstellungen“ entfernt werden. Diese Option wird während der Aktivierung festgelegt und kann ohne Zurücksetzen des Geräts auf die Werkseinstellungen nicht geändert werden.

    - **Kopplung zulassen:** Gibt an, ob iOS-Geräte mit Computern synchronisiert werden können. Wenn Sie **Apple Configurator nach Zertifikat zulassen** auswählen, müssen Sie unter **Apple Configurator-Zertifikate** ein Zertifikat auswählen.

    - **Apple Configurator-Zertifikate:** Wenn Sie **Apple Configurator nach Zertifikat zulassen** unter **Kopplung zulassen** ausgewählt haben, wählen Sie ein Apple Configurator-Zertifikat aus, das Sie importieren möchten.

  Wählen Sie **Speichern** aus.

5. Wählen Sie **Einstellungen des Setup-Assistenten** aus, um die folgenden Profileinstellungen zu konfigurieren: ![Screenshot der Auswahl für Konfigurationseinstellungen mit den verfügbaren Einstellungen für ein neues Profil des Registrierungsprogramms](./media/enrollment-program-profile-settings.png)
    - **Abteilungsname:** Wird angezeigt, wenn Benutzer während der Aktivierung auf **Info zur Konfiguration** tippen.

    - **Abteilungstelefonnummer:** Wird angezeigt, wenn der Benutzer während der Aktivierung auf die Schaltfläche „Benötigen Sie Hilfe?“ klickt.
    - **Setup-Assistent-Optionen**: Diese optionalen Einstellungen können später im iOS-Menü **Einstellungen** eingerichtet werden.
        - **Kennung**: Aufforderung zur Eingabe der Kennung während der Aktivierung. Fordern Sie immer eine Kennung an, es sei denn, das Gerät und der Zugriff darauf werden auf andere Weise geschützt (d.h. im Kioskmodus zum Einschränken des Geräts auf eine App).
        - **Ortungsdienste**: Falls aktiviert, fordert der Setup-Assistent den Dienst während der Aktivierung an.
        - **Wiederherstellen**: Falls aktiviert, fordert der Setup-Assistent die iCloud-Sicherung während der Aktivierung an.
        - **Apple-ID**: Falls aktiviert, fordert iOS Benutzer zur Angabe einer Apple-ID an, wenn Intune versucht, eine App ohne eine ID zu installieren. Eine Apple-ID ist erforderlich, um iOS App Store-Apps herunterzuladen, einschließlich der Apps, die von Intune installiert wurden.
        - **Geschäftsbedingungen**: Falls aktiviert, fordert der Setup-Assistenten Benutzer auf, die Apple-Geschäftsbedingungen während der Aktivierung zu akzeptieren.
        - **Touch ID**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Apple Pay**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Zoom**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Siri** – Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf
        - **Diagnosedaten:** Bei Aktivierung fordert der Setup-Assistent während der Aktivierung zur Ausführung dieses Dienst auf.

    Wählen Sie **Speichern** aus.
9. Wählen Sie zum Speichern der Profileinstellungen **Erstellen** auf dem Blatt **Registrierungsprofil erstellen** aus. Das Registrierungsprofil wird in der Liste der Registrierungsprofile des Apple-Registrierungsprogramms angezeigt.

## <a name="sync-managed-devices"></a>Synchronisieren verwalteter Geräte
Nachdem Intune nun die Berechtigung zum Verwalten Ihrer Geräte besitzt, können Sie Intune mit Apple synchronisieren, um Ihre verwalteten Geräte im Intune-Portal anzuzeigen.

1. Wählen Sie im Intune-Portal die Optionen **Geräteregistrierung** &gt;  **Apple-Registrierung** &gt; **Geräte des Registrierungsprogramms** aus.
2. Wählen Sie unter **Geräte des Registrierungsprogramms** die Option **Synchronisieren**. Das Blatt **Synchronisieren** wird angezeigt.
![Screenshot des ausgewählten Knotens „Geräte des Registrierungprogramms“ und des ausgewählten Links „Synchronisierung“](./media/enrollment-program-device-sync.png)
3. Wählen Sie auf dem Blatt **Synchronisieren** die Option **Synchronisierung anfordern** aus. Die Statusanzeige zeigt die Zeitdauer, die Sie warten müssen, bevor Sie die Synchronisierung erneut anfordern können.
![Screenshot des Blatts „Synchronisierung“ mit ausgewähltem Link „Synchronisierung anfordern“](./media/enrollment-program-device-request-sync.png)
    Zur Einhaltung der Apple-Bedingungen für zulässigen Datenverkehr des Registrierungsprogramms erzwingt Intune die folgenden Einschränkungen:
     -  Eine vollständige Synchronisation kann nicht öfter als einmal alle sieben Tage erfolgen. Während einer vollständigen Synchronisierung aktualisiert Intune jede Seriennummer, die Intune von Apple zugewiesen wurde, und zwar unabhängig davon, ob die Seriennummer vorher synchronisiert wurde oder nicht. Wenn eine vollständige Synchronisierung innerhalb von sieben Tagen nach der vorherigen vollständigen Synchronisierung versucht wird, aktualisiert Intune nur Seriennummern, die nicht bereits in Intune aufgeführt sind.
     -  Synchronisierungsanforderungen müssen innerhalb von 15 Minuten abgeschlossen sein. Während dieser Zeit oder bis zum erfolgreichen Erfüllen der Anforderung wird die Schaltfläche **Synchronisieren** deaktiviert.
4. Wählen Sie im Arbeitsbereich „Geräte des Registrierungsprogramms“ die Option **Aktualisieren** aus, um Ihre Geräte anzuzeigen.

## <a name="assign-an-enrollment-profile-to-devices"></a>Zuweisen eines Registrierungsprofils an Geräte
Geräten, die von Intune verwaltet werden, muss vor der Registrierung ein Profil des Registrierungsprogramms zugewiesen werden.

>[!NOTE]
>Sie können auch auf dem Blatt **Apple-Seriennummern** Profilen Seriennummern zuweisen.

1. Wählen Sie im Intune-Portal die Option **Geräteregistrierung** > **Apple-Registrierung** und dann **Profile des Registrierungsprogramms** aus.
2. Wählen Sie aus der Liste **Profile des Registrierungsprogramms** das Profil aus, das den Geräten zugewiesen werden soll, und wählen Sie anschließend **Geräte zuweisen** aus.
![Screenshot des Blatts „Synchronisierung“ mit ausgewähltem Link „Synchronisierung anfordern“](./media/enrollment-program-device-assign.png)
3. Wählen Sie **Zuweisen** und anschließend die Geräte aus, die diesem Profil zugewiesen werden sollen. Sie können die Ansicht nach verfügbaren Geräten filtern:
  - **Nicht zugewiesen**
  - **Beliebig**
  - **&lt;Profilname&gt;**
4. Wählen Sie die Geräte aus, die zugewiesen werden sollen. Mit dem Kontrollkästchen oberhalb der Spalte werden bis zu 1000 aufgelistete Geräte ausgewählt. Klicken Sie dann auf **Zuweisen**. Um mehr als 1000 Geräte zu registrieren, wiederholen Sie die Zuweisungsschritte, bis allen Geräten ein Registrierungsprofil zugewiesen ist.

  ![Screenshot der Schaltfläche „Zuweisen“ zum Zuweisen des Profils des Registrierungsprogramms im Intune-Portal](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Bedienung von verwalteten Geräten durch Endbenutzer

Sie können jetzt Geräte an Benutzer verteilen. Für Geräte mit Benutzeraffinität muss jedem Benutzer eine Intune-Lizenz zugewiesen werden. Wenn das Gerät aktiviert wurde und verwendet wird, kann das Profil erst angewendet werden, wenn das Gerät auf die Werkseinstellungen zurückgesetzt wird. Beim Einschalten von iOS-Geräten, die mit dem Registrierungsprogramm verwaltet werden, wird dem Benutzer Folgendes angezeigt:  

1. **iOS-Gerät einrichten**: Benutzern stehen folgende Optionen zur Auswahl:
  - **Als neues Gerät einrichten**
  - **Aus iCloud-Sicherung wiederherstellen**
  - **Aus iTunes-Sicherung wiederherstellen**
2. Benutzer werden darüber informiert, dass **Microsoft das Gerät automatisch konfiguriert.** Die folgenden zusätzlichen Konfigurationsinformationen sind ebenfalls verfügbar:

  **Die Konfiguration ermöglicht Microsoft die drahtlose Verwaltung dieses Geräts.**

  **Ein Administrator unterstützt Sie bei der Einrichtung von E-Mail- und -Netzwerkkonten, der Installation und Konfiguration von Apps und der Remoteverwaltung von Einstellungen.**

  **Ein Administrator kann Funktionen deaktivieren, Apps installieren und entfernen, Ihren Internetdatenverkehr überwachen und einschränken und eine Remotelöschung dieses Geräts ausführen.**

  **Die Konfiguration wird bereitgestellt von:<br> MicrosoftIntune iOS Team<br> One Microsoft Way, Redmond, WA 98052 (USA)**

3. Benutzer werden zur Eingabe ihres Benutzernamens und Kennworts für die Arbeit oder die Schule/Universität aufgefordert.
4. Benutzer werden zur Eingabe ihrer Apple-ID aufgefordert. Eine Apple-ID wird zur Installation der Intune-Unternehmensportal-App und anderer Apps benötigt. Nachdem Anmeldeinformationen bereitgestellt wurden, installiert das Gerät ein Verwaltungsprofil, das nicht entfernt werden kann. Das Intune-Verwaltungsprofil wird unter **Einstellungen** > **Allgemein** > **Geräteverwaltung** auf dem Gerät angezeigt.

Benutzer können nun die Einrichtung ihres unternehmenseigenen Geräts über das Intune-Unternehmensportal oder den Apple-Setup-Assistenten abschließen.
