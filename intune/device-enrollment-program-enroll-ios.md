---
title: "Registrieren von iOS-Geräten – Programm zur Geräteregistrierung"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mithilfe des Programms zur Geräteregistrierung von Apple (Device Enrollment Program, DEP) registrieren."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5144b9e7c17a3323667b9ca68cb47829d69866c3
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Dieses Thema hilft IT-Administratoren, firmeneigene iOS-Geräte, die über das [Geräteregistrierungsprogramm von Apple (DEP)](https://deploy.apple.com) erworben wurden, zu registrieren. Microsoft Intune kann ein Registrierungsprofil bereitstellen, das das Geräteregistrierungsprogramm „per Funk“ registrieren kann, damit der Administrator nicht jedes verwaltete Gerät in die Hand nehmen muss. Ein DEP-Profil enthält die Verwaltungseinstellungen, die Sie auf Geräten während der Registrierung anwenden möchten. Das Registrierungspaket kann Optionen für den Setup-Assistenten für das Gerät enthalten.

>[!NOTE]
>Die Registrierung mit DEP kann nicht mit dem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) verwendet werden.
>Wenn Benutzer ihre iOS-Geräte mithilfe der Unternehmensportal-App registrieren und die Seriennummer dieser Geräte dann importiert und einem DEP-Profil zugewiesen werden, wird die Registrierung des Geräts in Intune wieder rückgängig gemacht.

**Schritte zur DEP-Registrierung**
1. [Abrufen eines Apple-DEP-Tokens](#get-the-apple-dep-certificate)
2. [Erstellen Sie eines DEP-Profils](#create-an-apple-dep-profile)
3. [Zuweisen von Apple-DEP-Seriennummern auf dem MDM-Server](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Synchronisieren von DEP-verwalteten Geräten](#synchronize-dep-managed-devices)
5. [Zuweisen des DEP-Profils zu Geräten](#assign-a-dep-profile-to-devices)
6. [Verteilen von Geräten an Benutzer](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Abrufen des Apple-DEP-Zertifikats
Bevor Sie unternehmenseigene iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) registrieren können, benötigen Sie ein DEP-Zertifikat (.p7m) von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profilen Geräte zuweisen.

Zum Verwalten unternehmenseigener iOS-Geräte mit DEP müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Ausführliche Informationen zu diesem Prozess finden Sie unter https://deploy.apple.com. Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass ein USB-Kabel für die Verbindung jedes Geräts mit einem Computer verwendet werden muss.

> [!NOTE]
> Wenn Ihr Intune-Mandant von der klassischen Intune-Konsole zum Azure-Portal migriert wurde, und Sie haben ein Apple-DEP-Token aus der Intune-Verwaltungskonsole während des Migrationszeitraums gelöscht, kann das DEP-Token möglicherweise in Ihrem Intune-Konto wiederhergestellt worden sein. Sie können das DEP-Token erneut aus dem Azure-Portal löschen.

**Schritt 1: Laden Sie ein Intune-Zertifikat mit öffentlichem Schlüssel herunter, das zum Erstellen eines Apple-DEP-Tokens erforderlich ist.**<br>
1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ **Geräteregistrierung** > **Apple-DEP-Token** aus.
2. Wählen Sie **Laden Sie Ihr Zertifikat mit öffentlichem Schlüssel herunter** aus, um die Verschlüsselungsschlüsseldatei (PEM) herunterzuladen und lokal zu speichern. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.

**Schritt 2: Laden Sie ein Apple-DEP-Token über die entsprechende Apple-Website herunter.**<br>
Wählen Sie [DEP-Token über Apple-Bereitstellungsprogramme erstellen](https://deploy.apple.com) (https://deploy.apple.com) aus, und melden Sie sich mit der Apple-ID Ihres Unternehmens an. Diese Apple-ID kann später zum Erneuern Ihres DEP-Token verwendet werden.

   1.  Wechseln Sie im Portal des [Programms zur Geräteregistrierung](https://deploy.apple.com) von Apple zu **Programm zur Geräteregistrierung** &gt; **Server verwalten**, und wählen Sie anschließend **MDM-Server hinzufügen** aus.
   2.  Geben Sie den **MDM-Servernamen** ein, und wählen Sie anschließend **Weiter** aus. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.
   3.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet. Wählen Sie **Datei auswählen** aus, um die PEM-Datei hochzuladen, und wählen Sie anschließend **Weiter** aus.
   4.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und wählen Sie anschließend **Fertig** aus.

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-DEP-Tokens verwendete Apple-ID ein. Diese ID kann verwendet werden, um das Apple-DEP-Token zu erneuern.**

**Schritt 4: Navigieren Sie zu Ihrem hochzuladenden Apple-DEP-Token. Intune führt automatisch eine Synchronisierung mit Ihrem DEP-Konto durch.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

## <a name="create-an-apple-dep-profile"></a>Erstellen eines Apple-DEP-Profils

Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit dem Programm zur Geräteregistrierung registriert werden.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräteregistrierung** und dann **Apple-Registrierung** aus.
3. Wählen Sie unter **APPLE-DEP-EINSTELLUNGEN (PROGRAMM ZUR GERÄTEREGISTRIERUNG) VERWALTEN** die Option **DEP-Profile** aus.
4. Wählen Sie auf dem Blatt **DEP-Profile** die Option **Erstellen** aus.
5. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.
6. Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

 - **Mit Benutzeraffinität registrieren:** Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Wählen Sie die Benutzeraffinität für DEP-verwaltete Geräte aus, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie z.B. die Installation von Apps nutzen zu können. Beachten Sie, dass die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) während der Registrierung auf DEP-Geräten mit Benutzeraffinität nicht funktioniert. Nach der Registrierung funktioniert die MFA auf diesen Geräten wie erwartet. Neue Benutzer, die bei der ersten Anmeldung ihr Kennwort ändern müssen, können während der Registrierung auf DEP-Geräten nicht aufgefordert werden. Außerdem werden Benutzer, deren Passwörter abgelaufen sind, während der Registrierung nicht aufgefordert, ihr Kennwort zurückzusetzen; sie müssen ihr Kennwort von einem anderen Gerät aus zurücksetzen.

    >[!NOTE]
    >Für DEP mit Benutzeraffinität muss der [Endpunkt WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) aktiviert sein, um Benutzertoken anzufordern. [Erfahren Sie mehr über WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Ohne Benutzeraffinität registrieren:** Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

7. Wählen Sie **Geräteverwaltungseinstellungen** aus, konfigurieren Sie die folgenden Profileinstellungen, und wählen Sie dann **Speichern** aus:

    - **Überwacht:** Dieser Verwaltungsmodus ermöglicht weitere Verwaltungsoptionen und deaktiviert standardmäßig die Aktivierungssperre. Wenn Sie das Kontrollkästchen nicht aktivieren, stehen Ihnen nur beschränkte Verwaltungsfunktionen zur Verfügung.

    - **Registrierung gesperrt:**: (Erfordert den Vorbereitungsmodus „Überwacht“) Deaktiviert iOS-Einstellungen, die das Entfernen des Verwaltungsprofils zulassen könnten. Wenn Sie dieses Kontrollkästchen nicht aktivieren, kann das Verwaltungsprofil aus dem Menü „Einstellungen“ entfernt werden. Diese Option wird während der Aktivierung festgelegt und kann ohne Zurücksetzen des Geräts auf die Werkseinstellungen nicht geändert werden.

    - **Kopplung zulassen:** Gibt an, ob iOS-Geräte mit Computern synchronisiert werden können. Wenn Sie **Apple Configurator nach Zertifikat zulassen** auswählen, müssen Sie unter **Apple Configurator-Zertifikate** ein Zertifikat auswählen.

    - **Apple Configurator-Zertifikate:** Wenn Sie **Apple Configurator nach Zertifikat zulassen** unter **Kopplung zulassen** ausgewählt haben, wählen Sie ein Apple Configurator-Zertifikat aus, das Sie importieren möchten.

8. Wählen Sie **Einstellungen des Einrichtungs-Assistenten** aus, konfigurieren Sie die folgenden Profileinstellungen, und wählen Sie dann **Speichern** aus:

    - **Abteilungsname:** Wird angezeigt, wenn Benutzer während der Aktivierung auf **Info zur Konfiguration** tippen.

    - **Abteilungstelefonnummer:** Wird angezeigt, wenn der Benutzer während der Aktivierung auf die Schaltfläche „Benötigen Sie Hilfe?“ klickt.
    - **Setup-Assistent-Optionen**: Diese optionalen Einstellungen können später im iOS-Menü **Einstellungen** eingerichtet werden.
        - **Kennung**: Aufforderung zur Eingabe der Kennung während der Aktivierung. Fordern Sie immer eine Kennung an, es sei denn, das Gerät und der Zugriff darauf werden auf andere Weise geschützt (d.h. im Kioskmodus zum Einschränken des Geräts auf eine App).
        - **Ortungsdienste**: Falls aktiviert, fordert der Setup-Assistent den Dienst während der Aktivierung an.
        - **Wiederherstellen**: Falls aktiviert, fordert der Setup-Assistent die iCloud-Sicherung während der Aktivierung an.
        - **Apple-ID**: Falls aktiviert, fordert iOS Benutzer zur Angabe einer Apple-ID an, wenn Intune versucht, eine App ohne eine ID zu installieren. Eine Apple ID ist erforderlich, um iOS App Store-Apps herunterzuladen, einschließlich Apps, die von Intune installiert wurden.
        - **Geschäftsbedingungen**: Falls aktiviert, fordert der Setup-Assistenten Benutzer auf, die Apple-Geschäftsbedingungen während der Aktivierung zu akzeptieren.
        - **Touch ID**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Apple Pay**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Zoom**: Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf.
        - **Siri** – Falls aktiviert, fordert der Setup-Assistent zur Ausführung dieses Dienst während der Aktivierung auf
        - **Diagnosedaten:** Bei Aktivierung fordert der Setup-Assistent während der Aktivierung zur Ausführung dieses Dienst auf.

9. Wählen Sie zum Speichern der Profileinstellungen **Erstellen** auf dem Blatt **Registrierungsprofil erstellen** aus.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Zuweisen von Apple-DEP-Seriennummern auf dem MDM-Server
Geräteseriennummern müssen im Apple-DEP-Webportal Ihrem Intune-MDM-Server zugewiesen werden, um Intune die Verwaltung dieser Geräte zu ermöglichen.

1. Wechseln Sie zum [Device Enrollment Program-Portal](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit der Apple-ID Ihres Unternehmens an.

2. Wechseln Sie zu **Bereitstellungsprogramm** &gt; **Programm zur Geräteregistrierung** &gt; **Geräte verwalten**.

3. Geben Sie an, wie Sie **Geräte auswählen**, fügen Sie dann Geräteinformationen hinzu, und geben Sie die Details zum Gerät wie **Seriennummer** und **Bestellnummer** an, oder **laden Sie eine CSV-Datei hoch**.

4. Wählen Sie **Zu Server zuweisen** aus. Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; und anschließend **OK** aus.

## <a name="synchronize-dep-managed-devices"></a>Synchronisieren von DEP-verwalteten Geräten
Nachdem Intune nun die Berechtigung zum Verwalten Ihrer DEP-Geräte zugewiesen wurde, können Sie Intune mit dem DEP-Dienst synchronisieren, um Ihre verwalteten Geräte im Intune-Portal anzuzeigen.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräteregistrierung** und dann **Apple-Registrierung** aus.

3. Wählen Sie unter **APPLE-DEP-EINSTELLUNGEN (PROGRAMM ZUR GERÄTEREGISTRIERUNG) VERWALTEN** die Option **DEP-Seriennummern** aus.

4. Wählen Sie auf dem Blatt **DEP-Seriennummern** die Option **Synchronisieren** aus.

5. Wählen Sie auf dem Blatt **Synchronisieren** die Option **Synchronisierung anfordern** aus. Die Statusanzeige zeigt die Zeitdauer, die Sie warten müssen, bevor Sie die Synchronisierung erneut anfordern können.

    Zur Einhaltung der Apple-Bedingungen für zulässigen DEP-Datenverkehr erzwingt Intune die folgenden Einschränkungen:
     -    Eine vollständige DEP-Synchronisation kann nicht öfter als einmal alle sieben Tage erfolgen. Während einer vollständigen Synchronisierung aktualisiert Intune jede Seriennummer, die Intune von Apple zugewiesen wurde, und zwar unabhängig davon, ob die Seriennummer vorher synchronisiert wurde oder nicht. Wenn eine vollständige Synchronisierung innerhalb von sieben Tagen nach der vorherigen vollständigen Synchronisierung versucht wird, aktualisiert Intune nur Seriennummern, die nicht bereits in Intune aufgeführt sind.
     -    Synchronisierungsanforderungen müssen binnen 10 Minuten abgeschlossen werden. Während dieser Zeit oder bis zum erfolgreichen Erfüllen der Anforderung wird die Schaltfläche **Synchronisieren** deaktiviert.

>[!NOTE]
>Sie können auch auf dem Blatt **DEP-Seriennummern** Profilen DEP-Seriennummern zuweisen.

## <a name="assign-a-dep-profile-to-devices"></a>Zuweisen des DEP-Profils zu Geräten
DEP-Geräten, die von Intune verwaltet werden, muss vor der Registrierung ein DEP-Profil zugewiesen werden.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräteregistrierung** > **Apple-Registrierung** und dann **DEP-Profile** aus.

3. Wählen Sie in der Liste **Apple-DEP-Registrierungsprofile** das Profil aus, das den Geräten zugewiesen werden soll, und anschließend **Zuweisungen von Geräten**.

4. Wählen Sie **Zuweisen** und dann die für das DEP verfügbaren Geräte aus, die diesem Profil zugewiesen werden sollen. Sie können die Ansicht der für das DEP verfügbaren Geräte filtern:
  - **Nicht zugewiesen**
  - **Beliebig**
  - **&lt;DEP-Profilname&gt;**

  ![Screenshot der Schaltfläche „Zuweisen“ zum Zuweisen des DEP-Profils im Intune-Portal](media/dep-profile-assignment.png)

5. Wählen Sie die Geräte aus, die zugewiesen werden sollen. Mit dem Kontrollkästchen oberhalb der Spalte werden bis zu 1000 aufgelistete Geräte ausgewählt. Klicken Sie dann auf **Zuweisen**. Um mehr als 1000 Geräte zu registrieren, wiederholen Sie die Zuweisungsschritte, bis allen Geräten ein DEP-Profil zugewiesen ist.

## <a name="distribute-devices-to-users"></a>Verteilen von Geräten an Benutzer

Ihre unternehmenseigenen Geräte können jetzt an Benutzer verteilt werden. Wenn ein iOS-DEP-Gerät eingeschaltet wird, wird es für die Verwaltung durch Intune registriert. Wenn das Gerät aktiviert wurde und verwendet wird, kann das Profil erst angewendet werden, wenn das Gerät auf die Werkseinstellungen zurückgesetzt wird.

Weitere Informationen finden Sie unter [So informieren sie Ihre Endbenutzer über Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Sie können die Endbenutzer auch auf [Verwenden Ihres iOS- oder Mac OS-Geräts mit Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) verweisen. 

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installieren und Verwenden das Unternehmensportals auf Geräten

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Nachdem Benutzer ihre Geräte erhalten haben, müssen sie zusätzliche, unten beschriebene Schritte ausführen, um den Setup-Assistenten abzuschließen und die Unternehmensportal-App zu installieren.

