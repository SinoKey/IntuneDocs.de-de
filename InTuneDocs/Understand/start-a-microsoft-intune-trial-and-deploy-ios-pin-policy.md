---
# required metadata

title: Starten eines Microsoft Intune-Tests und Bereitstellen einer iOS-PIN-Richtlinie | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Starten eines Microsoft Intune-Tests und Bereitstellen einer iOS-PIN-Richtlinie
Diese schrittweisen Anweisungen unterstützen Sie beim Einrichten einer Intune-Testversion und Konfigurieren einer PIN-Richtlinie für iOS-Geräte. Eine Liste mit anderen Intune-Evaluierungsaufgaben, die Sie ausprobieren können, finden Sie unter [Allgemeine Microsoft Intune-Evaluierungsaufgaben](common-microsoft-intune-evaluation-tasks.md)..



## Überprüfen der Voraussetzungen für diese Aufgabe

-   Windows-PC mit Internet Explorer – für administrative Aufgaben

-   Gerät mit iOS 7.1 oder höher zum Testen der Validierung der Benutzerrichtlinie

-   Telefon zur Authentifizierung während der Anmeldung der Testversion

## Erstellen eines kostenlosen Intune-Testkontos
> [!NOTE]
> Wenn Sie bereits über ein Intune-Abonnement verfügen, überspringen Sie diesen Abschnitt und fahren mit dem nächsten Abschnitt fort.

1.  Klicken Sie auf einem Windows-PC mit der rechten Maustaste auf **Internet Explorer** (IE), und wählen Sie **InPrivate-Browsen** aus..

    ![InPrivate-Browsen starten](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Wechseln Sie zum [Intune-Anmeldungsportal](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), stellen Sie die erforderlichen Informationen bereit, und klicken Sie dann auf **Weiter**..

    ![Registrieren für ein Konto](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Geben Sie eine Benutzer-ID und das Kennwort für Ihr Administratorkonto ein, und klicken Sie auf **Weiter**. Sie verwenden diese ID für die Anmeldung beim Intune-Portal, um Ihre Administratoraufgaben wahrzunehmen.

    ![Erstellen einer ID](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Geben Sie Ihre Mobiltelefonnummer ein, und klicken Sie zum Überprüfen Ihrer Nummer auf **SMS**.

    ![Ihre Angaben überprüfen](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Speichern Sie die auf dem Bildschirm angezeigten Informationen, und klicken Sie dann auf **Jetzt kann es losgehen...**..

    ![Jetzt kann es losgehen](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Erstellen eines Testbenutzers

1.  Klicken Sie auf einem Windows-PC auf **Start**, um zur Seite für die Benutzerverwaltung zu wechseln.

    ![Zur Seite für die Benutzerverwaltung wechseln](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Klicken Sie auf die Schaltfläche **+**, um einen Benutzer hinzuzufügen.

    ![Hinzufügen eines Benutzers](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Auf der Seite **Neues Benutzerkonto erstellen**:

    1.  Geben Sie Informationen für den Testbenutzer an.

    2.  Wählen Sie die Option **Kennwort eingeben** aus.

    3.  Deaktivieren Sie das Kontrollkästchen **Diese Person muss ihr Kennwort bei der nächsten Anmeldung ändern**.

    4.  Klicken Sie auf **Erstellen**..

    ![Erstellen eines neuen Benutzerkontos](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Klicken Sie auf der Seite zur Bestätigung der Erstellung auf **Schließen**..

    ![Seite zur Bestätigung der Erstellung](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Klicken Sie auf die Schaltfläche **Aktualisieren**, um den von Ihnen erstellten Testbenutzer anzuzeigen.

    ![Kontobestätigung](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Konfigurieren einer iOS-PIN-Richtlinie für den Testbenutzer

1.  Legen Sie auf einem Windows-PC Intune als MDM-Autorität fest:

    1.  Wechseln Sie zur [Intune-Verwaltungskonsole](http://manage.microsoft.com/), melden Sie sich mit Ihrem Administratorkonto an, und klicken Sie auf **Verwaltung mobiler Geräte starten**. Die Seite „Autorität für die Verwaltung mobiler Geräte“ wird geöffnet.

        ![Erste Schritte in der Intune-Konsole](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Klicken Sie auf den Link **Autorität für die Verwaltung mobiler Geräte festlegen**.

        ![Festlegen der Autorität für die Verwaltung mobiler Geräte](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Aktivieren Sie iOS-Geräte für die Registrierung. Über diesen Prozess wird zwischen dem Apple Push Notification Service (APNS) und Ihrem Intune-Abonnement ein vertrauenswürdiges Zertifikat eingerichtet.

    1.  Klicken Sie auf **iOS- und Mac OS X-Plattform aktivieren**..

        ![Aktivieren der Registrierung bei iOS und Mac OS X](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Klicken Sie auf **APNS-Zertifikatanforderung herunterladen**..

        ![Herunterladen des APNS-Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Geben Sie einen Dateinamen und Speicherort für die Zertifikatsignieranforderung (CSR) an, und klicken Sie dann auf **Speichern**. Diese Datei enthält den öffentlichen Schlüssel, der mit einem privaten Schlüssel übereinstimmt, der zu Ihrem Intune-Abonnement gehört.

        ![Angeben einer Zertifikatsignierungsanforderung](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Klicken Sie auf **Apple Push Certificates-Portal**, um eine neue Registerkarte zu öffnen.

        ![Wechseln zur APNS-Zertifikatseite](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Geben Sie Ihre Apple-ID und das zugehörige Kennwort ein, und klicken Sie auf **Anmelden**. Bei dieser ID kann es sich um die ID handeln, die Sie auf Ihrem iOS-Gerät zum Abrufen von Apps aus dem iOS App Store verwenden.

        ![Anmelden beim Apple Push Certificates-Portal](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Klicken Sie auf **Zertifikat erstellen**..

        ![Erstellen eines APNS-Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Lesen Sie die Nutzungsbedingungen von Apple, aktivieren Sie das Kontrollkästchen, und klicken Sie auf **Annehmen**..

        ![Annehmen der Bedingungen](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Klicken Sie auf **Durchsuchen**..

        ![Suchen nach dem Speicherort des Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Wählen Sie die zuvor gespeicherte CSR-Datei aus, und klicken Sie auf **Öffnen**..

        ![Öffnen des Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Klicken Sie auf die Schaltfläche **Hochladen**.

        ![Hochladen des Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Wenn Sie zum Herunterladen einer JSON-Datei aufgefordert werden, klicken Sie auf **Speichern unter**..

        ![Speichern der JSON-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Geben Sie einen Speicherort für die JSON-Datei an, und klicken Sie auf **Speichern**..

        ![Angeben des Speicherorts für die JSON-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Wenn auf der Seite nach einigen Sekunden keine automatische Weiterleitung erfolgt, klicken Sie auf **Abbrechen**..

        ![Abbrechen bei ausbleibender Weiterleitung](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Um die neu erstellte Zertifikatdatei abzurufen, klicken Sie auf **Herunterladen**..

        ![Herunterladen des Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Wenn Sie zum Herunterladen einer PEM-Datei aufgefordert werden, klicken Sie auf **Speichern unter**..

        ![Herunterladen der PEM-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Geben Sie einen Speicherort für die PEM-Datei an, und klicken Sie auf **Speichern**..

        ![Speichern der PEM-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Kehren Sie zur Registerkarte der Intune-Verwaltungskonsole zurück, und klicken Sie auf die **APNS-Zertifikat hochladen**..

        ![Hochladen des APNS-Zertifikats](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Geben Sie Ihre Apple-ID ein, und klicken Sie auf **Durchsuchen**..

        ![Eingeben der Apple-ID](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Wählen Sie die soeben gespeicherte PEM-Datei aus, und klicken Sie auf **Öffnen**..

        ![Öffnen der PEM-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Klicken Sie auf **Hochladen**..

        ![Hochladen der PEM-Datei](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Ihr APNS-Zertifikat ist jetzt konfiguriert.

        ![APNS-Zertifikatkonfiguration abgeschlossen](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Erstellen Sie zum Ausrichten der Richtlinie eine Testbenutzergruppe:

    1.  Klicken Sie im linken Bereich auf **Gruppen**..

        ![Öffnen von Gruppen](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Klicken Sie ganz rechts auf **Gruppe erstellen**..

        ![Erstellen einer Gruppe](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Geben Sie einen Gruppennamen an, wählen Sie **Alle Benutzer** als übergeordnete Gruppe aus, und klicken Sie dann auf **Weiter**..

        ![Auswählen von „Alle Benutzer“ als übergeordnete Gruppe](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  Wählen Sie im Feld **Gruppenmitgliedschaft starten mit** die Option **Alle Benutzer in der übergeordneten Gruppe** aus, und klicken Sie dann auf **Fertig stellen**..

        ![Starten der Gruppenmitgliedschaft mit der übergeordneten Gruppe](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Erstellen Sie eine iOS-PIN-Richtlinie, und richten Sie diese auf die Testbenutzergruppe aus:

    1.  Klicken Sie im linken Bereich auf **Richtlinie**..

        ![Öffnen des Arbeitsbereichs „Richtlinie“](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Klicken Sie ganz rechts auf **Richtlinie hinzufügen**..

        ![Hinzufügen einer Richtlinie](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Erweitern Sie den iOS-Knoten, wählen Sie die Zeile **Allgemeine Konfiguration** aus, und klicken Sie auf **Richtlinie erstellen**..

        ![Erstellen einer allgemeinen iOS-Konfigurationsrichtlinie](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Geben Sie einen Namen für die Richtlinie ein, aktivieren Sie die Option **Kennwort zum Entsperren mobiler Geräte erforderlich**, und legen Sie für die Option **Minimale Kennwortlänge** den Wert **4** fest..

        ![Konfigurieren der Kennworteinstellungen](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Klicken Sie zum Bereitstellen der Richtlinie auf **Ja**.

        ![Bereitstellen der Richtlinie](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Klicken Sie auf die zuvor erstellte Benutzergruppe, anschließend auf **Hinzufügen** und dann auf **OK**..

        ![Auswählen der Gruppe für die Richtlinie](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Sie verfügen jetzt über eine iOS-PIN-Richtlinie, die auf Ihre Testbenutzergruppe ausgerichtet ist.

        ![Einrichtung der Richtlinie abgeschlossen](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Überprüfen, ob die Richtlinie auf einem iOS-Gerät erzwungen wird

1.  Starten Sie auf einem iPad den iOS App Store, installieren Sie die kostenlose App **Intune-Unternehmensportal**, und öffnen Sie sie anschließend.

    ![Installieren des Unternehmensportals](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Geben Sie den Namen und das Kennwort für Ihr Testbenutzerkonto ein, und tippen Sie auf **Anmelden**..

    ![Eingeben Ihrer Anmeldeinformationen](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Tippen Sie auf **Registrieren**, um mit der Registrierung des Geräts in Intune zu beginnen.

    ![Starten der Registrierung](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Tippen Sie auf dem Bildschirm **Profil installieren** auf **Installieren**..

    ![Installieren eines Profils](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  Tippen Sie im Dialogfeld **Profil installieren** auf **Installieren**..

    ![Fortsetzung der Profilinstallation](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Tippen Sie auf dem Bildschirm **Warnung** auf **Installieren**..

    ![Akzeptieren der Warnmeldung](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  Tippen Sie im Dialogfeld **Remoteverwaltung** auf **Vertrauen**..

    ![Vertrauensstellung für Remoteverwaltung](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Wenn die Installation des Verwaltungsprofils abgeschlossen ist, tippen Sie auf **Fertig**. Die Registrierung ist nun abgeschlossen.

    ![Registrierung abgeschlossen](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Wenn die Registrierung abgeschlossen ist, tippen Sie auf **OK** und schließen dann die Unternehmensportal-App.

    ![Auf OK tippen, um die Unternehmensportal-App zu schließen](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Wenn Sie zum Konfigurieren einer Kennung aufgefordert werden, tippen Sie auf **Weiter**..

    ![Akzeptieren der Aufforderung zum Konfigurieren einer Kennung](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Geben Sie Ihre Kennung ein, tippen Sie auf **Weiter**, geben Sie Ihre Kennung erneut ein, und tippen Sie auf **Speichern**..

    ![Angeben einer Kennung](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Drücken Sie den Netzschalter zum Sperren Ihres iPads, streichen Sie dann zum Entsperren über das Display, und prüfen Sie, ob Sie jetzt Ihre Kennung eingeben müssen, um das Gerät zu entsperren.

### Weitere Informationen:
[Intune-Evaluierungsanleitung](get-started-with-a-30-day-trial-of-microsoft-intune.md)


<!--HONumber=May16_HO1-->


