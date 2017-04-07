---
title: "Registrieren von iOS-Geräten – Programm zur Geräteregistrierung"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mithilfe des Programms zur Geräteregistrierung von Apple (Device Enrollment Program, DEP) registrieren."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 3e1898441b7576c07793e8b70f3c3f09f1cac534
ms.openlocfilehash: ddeaeb2d532635802c615d09b4625dee0a824919
ms.lasthandoff: 02/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune kann ein Registrierungsprofil bereitstellen, das über das Programm zur Geräteregistrierung (Device Enrollment Program, DEP) erworbene iOS-Geräte drahtlos registriert. Ein Profil enthält die Verwaltungseinstellungen, die Sie auf Geräte anwenden möchten. Das Registrierungspaket kann Optionen für den Setup-Assistenten für das Gerät enthalten. Die Registrierung von Geräten über DEP kann von Benutzern nicht rückgängig gemacht werden.

>[!NOTE]
>Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](enroll-devices-using-device-enrollment-manager.md) verwendet werden.

Zum Verwalten unternehmenseigener iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Details zu diesem Prozess finden Sie unter:  [https://deploy.apple.com](https://deploy.apple.com). Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass ein USB-Kabel für die Verbindung jedes Geräts mit einem Computer verwendet werden muss.

Bevor Sie unternehmenseigene iOS-Geräte mit dem Programm zur Geräteregistrierung registrieren können, benötigen Sie ein [DEP-Token](get-apple-dep-token.md) von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profile Geräte zuweisen.

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](choose-ios-enrollment-method.md) beschriebenen.

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von iOS-Geräten erfüllt sein:

- [Konfigurieren von Domänen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Festlegen der MDM-Autorität](set-mdm-authority.md)
- [Erstellen von Gruppen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Zuweisen von Benutzerlizenzen im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Abrufen eines Apple-MDM-Push-Zertifikats](get-an-apple-mdm-push-certificate.md)
- [Abrufen eines Apple-DEP-Tokens](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Erstellen eines Apple-DEP-Profils für Geräte

Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit dem Programm zur Geräteregistrierung registriert werden.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

3. Wählen Sie unter **APPLE-DEP-EINSTELLUNGEN (PROGRAMM ZUR GERÄTEREGISTRIERUNG) VERWALTEN** die Option **DEP-Profile** aus.

4. Wählen Sie auf dem Blatt **DEP-Profile** die Option **Erstellen** aus.

5. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.

6. Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

 - **Mit Benutzeraffinität registrieren:** Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Wählen Sie die Benutzeraffinität für DEP-verwaltete Geräte aus, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie z.B. die Installation von Apps nutzen zu können. Beachten Sie, dass die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) während der Registrierung auf DEP-Geräten mit Benutzeraffinität nicht funktioniert. Nach der Registrierung funktioniert die MFA auf diesen Geräten wie erwartet. Neue Benutzer, die bei der ersten Anmeldung ihr Kennwort ändern müssen, können während der Registrierung auf DEP-Geräten nicht aufgefordert werden. Außerdem werden Benutzer, deren Passwörter abgelaufen sind, während der Registrierung nicht aufgefordert, ihr Kennwort zurückzusetzen; sie müssen ihr Kennwort von einem anderen Gerät aus zurücksetzen.

    >[!NOTE]
    >Für DEP mit Benutzeraffinität muss der Endpunkt WS-Trust 1.3 Username/Mixed aktiviert sein, um Benutzertoken anzufordern.

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

1. Wechseln Sie zum [Device Enrollment Program-Portal](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit der Apple-ID Ihres Unternehmens an.

2. Wechseln Sie zu **Bereitstellungsprogramm** &gt; **Programm zur Geräteregistrierung** &gt; **Geräte verwalten**.

3. Geben Sie an, wie Sie **Geräte auswählen**, fügen Sie dann Geräteinformationen hinzu, und geben Sie die Details zum Gerät wie **Seriennummer** und **Bestellnummer** an, oder **laden Sie eine CSV-Datei hoch**.

4. Wählen Sie **Zu Server zuweisen** aus. Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; und anschließend **OK** aus.

## <a name="synchronize-dep-managed-devices"></a>Synchronisieren von DEP-verwalteten Geräten

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

3. Wählen Sie unter **APPLE-DEP-EINSTELLUNGEN (PROGRAMM ZUR GERÄTEREGISTRIERUNG) VERWALTEN** die Option **DEP-Seriennummern** aus.

4. Wählen Sie auf dem Blatt **DEP-Seriennummern** die Option **Synchronisieren** aus.

5. Wählen Sie auf dem Blatt **Synchronisieren** die Option **Synchronisierung anfordern** aus. Die Statusanzeige zeigt die Zeitdauer, die Sie warten müssen, bevor Sie die Synchronisierung erneut anfordern können.

    Zur Einhaltung der Apple-Bedingungen für zulässigen DEP-Datenverkehr erzwingt Intune die folgenden Einschränkungen:
     -    Eine vollständige DEP-Synchronisation kann nicht öfter als einmal alle sieben Tage erfolgen. Während einer vollständigen Synchronisierung aktualisiert Intune jede Seriennummer, die Intune von Apple zugewiesen wurde, und zwar unabhängig davon, ob die Seriennummer vorher synchronisiert wurde oder nicht. Wenn eine vollständige Synchronisierung innerhalb von sieben Tagen nach der vorherigen vollständigen Synchronisierung versucht wird, aktualisiert Intune nur Seriennummern, die nicht bereits in Intune aufgeführt sind.
     -    Synchronisierungsanforderungen müssen binnen 10 Minuten abgeschlossen werden. Während dieser Zeit oder bis zum erfolgreichen Erfüllen der Anforderung wird die Schaltfläche **Synchronisieren** deaktiviert.

>[!NOTE]
>Sie können auch auf dem Blatt **DEP-Seriennummern** Profilen DEP-Seriennummern zuweisen.

## <a name="distribute-devices-to-users"></a>Verteilen von Geräten an Benutzer

Ihre unternehmenseigenen Geräte können jetzt an Benutzer verteilt werden. Wenn ein iOS-Gerät eingeschaltet wird, wird es für die Verwaltung durch Intune registriert.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installieren und Verwenden das Unternehmensportals auf Geräten

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Nachdem Benutzer ihre Geräte erhalten haben, müssen sie zusätzliche, unten beschriebene Schritte ausführen, um den Setup-Assistenten abzuschließen und die Unternehmensportal-App zu installieren.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Registrieren von firmeneigenen iOS-Geräten mit Benutzeraffinität durch Benutzer

1. Wenn Benutzer ihr Gerät einschalten, werden sie aufgefordert, den Setup-Assistenten zu durchlaufen. Während des Setups werden Benutzer zur Eingabe ihrer Anmeldeinformationen aufgefordert. Sie müssen die Anmeldeinformationen (d.h. den eindeutigen persönlichen Namen) verwenden, die ihrem Abonnement in Intune zugeordnet sind.

2. Während des Setups werden Benutzer zur Eingabe einer Apple ID aufgefordert. Sie müssen eine Apple-ID angeben, damit das Gerät das Unternehmensportal installieren kann. Sie können die ID auch nach Abschluss des Setups über das iOS-Menü „Einstellungen“ angeben.

3. Nach Abschluss des Setups muss die Unternehmensportal-App aus dem App Store installiert werden.

4. Benutzer können sich nun mit dem eindeutigen persönlichen Namen, der beim Setup des Geräts verwendet wurde, beim Unternehmensportal anmelden.

5. Nach der Anmeldung werden die Benutzer aufgefordert, ihr Gerät zu registrieren. Der erste Schritt besteht im Identifizieren des Geräts. Die App zeigt eine Liste mit iOS-Geräten, die bereits vom Unternehmen registriert und dem Intune-Konto des Benutzers zugewiesen wurden. Der Benutzer sollte das entsprechende Gerät auswählen. Wenn das Gerät nicht bereits vom Unternehmen registriert wurde, sollten sie „Neues Gerät“ auswählen, um den Standardregistrierungsvorgang fortzusetzen.

6. Auf dem nächsten Bildschirm bestätigen die Benutzer die Seriennummer des neuen Geräts. Zu diesem Zweck wählen sie einen Link aus, der angezeigt wird. Der Link startet die Einstellungs-App, die es den Benutzern ermöglicht, ihre Seriennummer zu überprüfen. Die Benutzer müssen dann die letzten vier Zeichen der Seriennummer in der Unternehmensportal-App eingeben.

   Dieser Schritt dient zum Überprüfen, ob das Gerät das vom Unternehmen in Intune registrierte Gerät ist. Wenn die Seriennummer des Geräts nicht übereinstimmt, wurde das falsche Gerät ausgewählt. Der Benutzer muss zum vorherigen Bildschirm zurückkehren, und ein anderes Gerät auswählen.

7. Nachdem die Seriennummer überprüft wurde, wird die Unternehmensportal-App zur Unternehmensportal-Website umgeleitet, um die Registrierung abzuschließen. Anschließend fordert die Website den Benutzer auf, zur App zurückzukehren.

Die Registrierung ist damit abgeschlossen, und die Benutzer können nun die Funktionen des Geräts in vollem Umfang nutzen.

