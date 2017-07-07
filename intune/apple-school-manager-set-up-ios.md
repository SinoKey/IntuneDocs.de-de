---
title: "Einrichten der Registrierung von iOS-Geräten über das Apple School Manager-Programm"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie das Apple School Manager-Programm für die Registrierung von unternehmenseigenen iOS-Geräten bei Intune einrichten\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Aktivieren der iOS-Geräteregistrierung mit Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema unterstützt IT-Administratoren dabei, die iOS-Geräteregistrierung für Geräte zu aktivieren, die über das Programm [Apple School Manager](https://school.apple.com/) (ASM) erworben wurden. Microsoft Intune kann drahtlos (Over The Air) ein Registrierungsprofil bereitstellen, das ASM-Geräte für die Verwaltung registriert. Der Administrator muss nicht jedes einzelne verwaltete Gerät physisch konfigurieren. Ein ASM-Profil enthält Verwaltungseinstellungen, die während der Registrierung auf Geräte angewendet werden, einschließlich Optionen für den Setup-Assistenten.

**Schritte zur ASM-Registrierung**
1. [Abrufen eines ASM-Tokens und Zuweisen von Geräten](#get-the-asm-token-and-assign-devices)
2. [Erstellen eines Anmeldungsprofils](#create-an-apple-enrollment-profile)
3. [Verbinden mit School Data Sync](#connect-school-data-sync) (optional)
4. [Synchronisieren von über ASM verwalteten Geräten](#sync-asm-managed-devices)
5. [Zuweisen eines ASM-Profils zu Geräten](#assign-an-asm-profile-to-devices)
6. [Verteilen von Geräten an Benutzer](#distribute-devices-to-users)

>[!NOTE]
>Die ASM-Registrierung kann nicht in Zusammenhang mit dem [Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md) (Device Enrollment Program, DEP) von Apple oder dem Intune-Konto [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) verwendet werden.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Abrufen des Apple ASM-Tokens und Zuweisen von Geräten

Bevor Sie unternehmenseigene iOS-Geräte mit dem Apple School Manager registrieren können, benötigen Sie ein ASM-Token (P7M-Datei) von Apple. Mit diesem Token kann Intune Informationen zu Geräten synchronisieren, die zum ASM-Programm gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profilen Geräte zuweisen. Im Apple-Portal können Sie auch Geräteseriennummern für die Verwaltung zuweisen.

**Voraussetzungen**
- [Apple-MDM-Push-Zertifikat](apple-mdm-push-certificate-get.md)
- Für [Apple School Management](http://school.apple.com) registriert

**Schritt 1: Laden Sie ein Intune-Zertifikat mit öffentlichem Schlüssel herunter, das zum Erstellen eines Apple-ASM-Tokens erforderlich ist.**<br>
1. Wählen Sie im Azure [Intune-Portal](https://aka.ms/intuneportal) nacheinander die Optionen **Geräteregistrierung** und **Registrierungsprogrammtoken** aus.
2. Wählen Sie auf dem Blatt **Registrierungsprogrammtoken** die Option **Laden Sie Ihr Zertifikat mit öffentlichem Schlüssel herunter** aus, um die Verschlüsselungsschlüsseldatei (PEM) herunterzuladen und lokal zu speichern. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple School Manager-Portal anzufordern.

**Schritt 2: Rufen Sie ein ASM-Token ab, und weisen Sie Geräte zu.**<br>
Wählen Sie **Token über Apple School Manager erstellen**, und melden Sie sich mit Ihrer Apple-Unternehmens-ID an. Sie können diese Apple-ID auch zum Erneuern Ihres ASM-Tokens verwenden.

   1.  Wechseln Sie im [Apple School Manager-Portal](https://school.apple.com) zu **MDM-Server**, und wählen Sie **MDM-Server hinzufügen** (oben rechts).
   2.  Geben Sie den **MDM-Servernamen** ein. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.
   3.  Wählen Sie im Apple-Portal die Option **Datei hochladen...**, navigieren Sie zur PEM-Datei, und wählen Sie **MDM-Server speichern** (unten rechts).
   4.  Klicken Sie auf **Token abrufen**, und laden Sie die Servertokendatei (P7M) auf Ihren Computer herunter.
   5. Wechseln Sie zu **Gerätezuweisungen**, und verwenden Sie die Option **Gerät auswählen**, indem Sie **Seriennummern** oder **Bestellnummer** manuell eingeben oder eine **CSV-Datei hochladen**.
   6.   Wählen Sie die Aktion **Zu Server zuweisen**, und wählen Sie den von Ihnen erstellten **MDM-Server** aus.
   7. Geben Sie an, wie Sie **Geräte auswählen**, fügen Sie dann Geräteinformationen hinzu, und geben Sie die Details zum Gerät wie **Seriennummer** und **Bestellnummer** an, oder **laden Sie eine CSV-Datei hoch**.
   8. Wählen Sie **Zu Server zuweisen** aus. Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; und anschließend **OK** aus.

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-ASM-Tokens verwendete Apple-ID ein.**<br>Diese ID muss zum Erneuern Ihres Apple-ASM-Tokens verwendet werden und wird zur späteren Referenz gespeichert.

**Schritt 4: Suchen Sie Ihr Token, und laden Sie es hoch.**<br>
Wechseln Sie zur Zertifikatsdatei (P7M), und wählen Sie **Öffnen** und anschließend **Hochladen** aus. Intune synchronisiert Ihre ASM-Geräte automatisch mit Apple.

## <a name="create-an-apple-enrollment-profile"></a>Erstellen eines Apple-Registrierungsprofils
Ein Geräteregistrierungsprofil definiert die Einstellungen, die während der Registrierung auf eine Gruppe von Geräten angewendet werden.

1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
2. Wählen Sie unter **Registrierungsprogramm** den Eintrag **Profile des Registrierungsprogramms** aus.
3. Wählen Sie auf dem Blatt **Profile des Registrierungsprogramms** die Option **Erstellen** aus.
4. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen **Namen** und eine **Beschreibung** für das Profil ein, das im Intune-Portal angezeigt wird.
5. Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

 - **Mit Benutzeraffinität registrieren:** Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Wählen Sie die Benutzeraffinität für über ASM verwaltete Geräte, bei denen Benutzer sich mit ihrer verwalteten Apple-ID anmelden.

 >[!NOTE]
 >Die mehrstufige Authentifizierung (Multifactor Authentication, MFA) funktioniert während der Registrierung auf ASM-Geräten mit Benutzeraffinität nicht. Nach der Registrierung funktioniert die MFA auf diesen Geräten wie erwartet.

  Der Apple School Manager-Modus „Gemeinsam genutztes iPad“ erfordert, dass Benutzer sich mit Affinität registrieren.

 >[!NOTE]
    >Für ASM mit Benutzeraffinität muss der [Endpunkt WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) aktiviert sein, damit ein Benutzertoken angefordert werden kann. [Erfahren Sie mehr über WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Ohne Benutzeraffinität registrieren:** Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die Benutzeraffinität erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

6. Wählen Sie **Geräteverwaltungseinstellungen** aus. Diese Elemente werden während der Aktivierung festgelegt und erfordern ein Zurücksetzen auf die Werkseinstellungen, damit die Änderungen wirksam werden. Konfigurieren Sie die folgenden Profileinstellungen, und wählen Sie dann **Speichern** aus:

    - **Überwacht:** Dieser Verwaltungsmodus ermöglicht weitere Verwaltungsoptionen und deaktiviert standardmäßig die Aktivierungssperre. Wenn Sie das Kontrollkästchen nicht aktivieren, stehen Ihnen nur beschränkte Verwaltungsfunktionen zur Verfügung.

    - **Registrierung gesperrt:**: (Erfordert den Vorbereitungsmodus „Überwacht“) Deaktiviert iOS-Einstellungen, die das Entfernen des Verwaltungsprofils zulassen könnten. Wenn Sie dieses Kontrollkästchen nicht aktivieren, kann das Verwaltungsprofil aus dem Menü „Einstellungen“ entfernt werden.

  - **Gemeinsam genutztes iPad**: (erfordert die Option **Mit Benutzeraffinität registrieren** und den Modus **Überwacht**.) Diese Einstellung ermöglicht es, dass mehrere Benutzer sich mithilfe einer verwalteten Apple-ID bei registrierten iPads anmelden können. Verwaltete Apple-IDs werden im Apple School Manager-Portal erstellt.

  >[!NOTE]
  >Wenn der Modus **Gemeinsam genutztes iPad** in einem Profil aktiviert ist und dann entweder die **Benutzeraffinität** oder der Modus **Überwacht** **deaktiviert** wird, wird der Modus „Gemeinsam genutztes iPad“ für das Registrierungsprofil deaktiviert.

  - **Maximale Anzahl zwischengespeicherter Benutzer**: (Erfordert die Einstellung **Gemeinsam genutztes iPad** = **Ja**) Erstellt auf dem Gerät eine Partition für jeden Benutzer. Der empfohlene Wert ist die Anzahl von Studierenden, die das Gerät in einem bestimmten Zeitraum wahrscheinlich verwenden werden. Wenn unter der Woche voraussichtlich sechs Studierende das Gerät regelmäßig verwenden werden, legen Sie diesen Wert auf 6 fest.  

    - **Kopplung zulassen:** Gibt an, ob iOS-Geräte mit Computern synchronisiert werden können. Wenn Sie **Apple Configurator nach Zertifikat zulassen** auswählen, müssen Sie unter **Apple Configurator-Zertifikate** ein Zertifikat auswählen.

    - **Apple Configurator-Zertifikate:** Wenn Sie **Apple Configurator nach Zertifikat zulassen** unter **Kopplung zulassen** ausgewählt haben, wählen Sie ein Apple Configurator-Zertifikat aus, das Sie importieren möchten.

7. Wählen Sie **Einstellungen des Einrichtungs-Assistenten** aus, konfigurieren Sie die folgenden Profileinstellungen, und wählen Sie dann **Speichern** aus:

    - **Abteilungsname:** Wird angezeigt, wenn Benutzer während der Aktivierung auf **Info zur Konfiguration** tippen.

    - **Abteilungstelefonnummer:** Wird angezeigt, wenn der Benutzer während der Aktivierung auf die Schaltfläche „Benötigen Sie Hilfe?“ klickt.
    - **Setup-Assistent-Optionen**: Wenn diese Einstellungen im Setup-Assistenten ausgeschlossen wurden, können sie später im iOS-Menü **Einstellungen** eingerichtet werden.
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

8. Wählen Sie zum Speichern der Profileinstellungen **Erstellen** auf dem Blatt **Registrierungsprofil erstellen** aus.

## <a name="connect-school-data-sync"></a>Verbinden mit School Data Sync
(Optional) ASM unterstützt die Synchronisierung von Kursplandaten mit Azure Active Directory (AD) über Microsoft School Data Sync (SDS). Führen Sie die folgenden Schritte aus, um SDS zum Synchronisieren von Schul- bzw. Unidaten zu verwenden.

1. Klicken Sie auf dem Blatt **Registrierungsprogrammtoken** entweder auf das blaue Informationsbanner oder auf **SDS verbinden**.
2. Legen Sie die Einstellung **Der Microsoft-Synchronisierung von Schul-/Unidaten die Verwendung dieses Tokens gestatten** auf **Zulassen** fest. Mit dieser Einstellung kann Intune in Office 365 eine Verbindung mit SDS herstellen.
3. Um eine Verbindung zwischen ASM und Azure AD zu ermöglichen, wählen Sie **Microsoft-Synchronisierung von Schul-/Unidaten einrichten** aus. Erfahren Sie mehr über [das Einrichten von School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Klicken Sie zum Speichern und Fortfahren auf **OK**.

## <a name="sync-asm-managed-devices"></a>Synchronisieren von über ASM verwalteten Geräten
Nachdem Intune nun die Berechtigung zum Verwalten Ihrer ASM-Geräte zugewiesen wurde, können Sie Intune mit dem ASM-Dienst synchronisieren, um Ihre verwalteten Geräte im Intune-Portal anzuzeigen.

1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
2. Wählen Sie unter **Geräte des Registrierungsprogramms** die Option **Synchronisieren**. Die Statusanzeige zeigt die Zeitdauer, die Sie warten müssen, bevor Sie die Synchronisierung erneut anfordern können.

    Zur Einhaltung der Apple-Bedingungen für zulässigen ASM-Datenverkehr erzwingt Intune die folgenden Einschränkungen:
     -  Eine vollständige ASM-Synchronisation kann nicht häufiger als einmal alle sieben Tage erfolgen. Während einer vollständigen Synchronisierung aktualisiert Intune jede Seriennummer, die Intune von Apple zugewiesen wurde, und zwar unabhängig davon, ob die Seriennummer vorher synchronisiert wurde oder nicht. Wenn eine vollständige Synchronisierung innerhalb von sieben Tagen nach der vorherigen vollständigen Synchronisierung versucht wird, aktualisiert Intune nur Seriennummern, die nicht bereits in Intune aufgeführt sind.
     -  Synchronisierungsanforderungen müssen innerhalb von 15 Minuten abgeschlossen sein. Während dieser Zeit oder bis zum erfolgreichen Erfüllen der Anforderung wird die Schaltfläche **Synchronisieren** deaktiviert.

>[!NOTE]
>Sie können auch über das Blatt **Geräte des Registrierungsprogramms** ASM-Seriennummern zu Geräten zuweisen.

## <a name="assign-an-asm-profile-to-devices"></a>Zuweisen eines ASM-Profils zu Geräten
ASM-Geräten, die von Intune verwaltet werden, muss vor der Registrierung ein ASM-Profil zugewiesen werden.

1. Wählen Sie im Intune-Portal die Option **Geräteregistrierung** > **Apple-Registrierung** und dann **Profile des Registrierungsprogramms** aus.
2. Wählen Sie in der Liste **Profile des Registrierungsprogramms** das Profil aus, das den Geräten zugewiesen werden soll, und wählen Sie anschließend **Gerätezuweisungen** aus.
3. Wählen Sie **Zuweisen** und dann die ASM-Geräte aus, denen dieses Profil zugewiesen werden soll. Sie können die Ansicht nach für ASM verfügbaren Geräten filtern:
  - **Nicht zugewiesen**
  - **Beliebig**
  - **&lt;ASM-Profilname&gt;**
4. Wählen Sie die Geräte aus, die zugewiesen werden sollen. Mit dem Kontrollkästchen oberhalb der Spalte können bis zu 1.000 gelistete Geräte ausgewählt werden. Klicken Sie auf **Zuweisen**. Um mehr als 1000 Geräte zu registrieren, wiederholen Sie die Zuweisungsschritte, bis allen Geräten ein ASM-Profil zugewiesen ist.

## <a name="distribute-devices-to-users"></a>Verteilen von Geräten an Benutzer

Ihre unternehmenseigenen Geräte können jetzt an Benutzer verteilt werden. Wenn ein iOS-ASM-Gerät eingeschaltet wird, wird es für die Verwaltung durch Intune registriert. Wenn das Gerät aktiviert wurde und verwendet wird, kann das Profil erst angewendet werden, wenn das Gerät auf die Werkseinstellungen zurückgesetzt wird.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installieren und Verwenden das Unternehmensportals auf Geräten

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Nachdem Benutzer ihre Geräte erhalten haben, müssen sie den Setup-Assistenten ausführen und die Unternehmensportal-App installieren.
