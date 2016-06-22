---
# required metadata

title: Direkte Registrierung für iOS-Geräte | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Direkte Registrierung von iOS-Geräten mit Apple Configurator
Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird. Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode ist für Geräte mit der Einstellung **Keine Benutzeraffinität** vorgesehen und erfordert eine USB-Verbindung des iOS-Geräts mit einem Mac-Computer, um die Registrierung beim Unternehmen einzurichten. Die Unternehmensportal-App wird für direkte registrierte Geräte nicht unterstützt. Diese Anleitung setzt voraus, dass Sie Apple Configurator 2.0 auf einem Mac-Computer verwenden.

1.  **Erstellen eines Profils für Geräte** Ein Registrierungsprofil für Geräte definiert die Einstellungen für Geräte. Wenn Sie dies noch nicht getan haben, erstellen Sie ein Registrierungsprofil für iOS-Geräte, die mit Apple Configurator registriert werden.

    #### So erstellen Sie ein Profil

    1.  Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie dann **Hinzufügen…**.

        ![Erstellen einer Profilseite für die Geräteregistrierung](../media/pol-sa-corp-enroll.png)

    2.  Geben Sie die Details für die Geräteprofile ein:

        -   **Name** : Name des Geräteanmeldungsprofils. Für Benutzer nicht sichtbar.

        -   **Beschreibung**: Beschreibung des Geräteanmeldungsprofils. Für Benutzer nicht sichtbar.

        -   **Benutzerzuweisung** : Gibt an, wie Geräte registriert werden. Wählen Sie für die direkte Anmeldung **Keine Benutzeraffinität**aus.

        -   **Gerätegruppen-Vorabzuweisung**: Alle Geräte, die mit diesem Profil bereitgestellt werden, gehören anfänglich zu dieser Gruppe. Sie können die Geräte nach der Registrierung erneut zuweisen.

    3.  Wählen Sie **Profil speichern**, um das Profil hinzuzufügen.

5.  **Exportieren eines Profils als MOBILECONFIG-Datei für die Bereitstellung auf iOS-Geräten** Wählen Sie das Geräteprofil, das Sie erstellt haben. Wählen Sie **Exportieren…** in der Taskleiste. Wählen Sie **Profil herunterladen**, und speichern Sie die heruntergeladene MOBILECONFIG-Datei.

6.  **Übertragen der Datei** Kopieren Sie die heruntergeladene MOBILECONFIG-Datei auf einen Mac-Computer.
    > [!NOTE]
    > Die Anmeldungsprofil-URL ist ab dem Export zwei Wochen lang gültig. Nach zwei Wochen müssen Sie eine neue Anmeldungsprofil-URL zum Registrieren von iOS-Geräten mit dem Setup-Assistenten exportieren.
7.  **Vorbereiten des Geräts mit Apple Configurator** iOS-Geräte werden mit dem Mac-Computer verbunden und für die Verwaltung mobiler Geräte registriert.

    1.  Starten Sie auf einem Mac-Computer **Apple Configurator 2.0**.

    2.  Verbinden Sie das iOS-Gerät mit dem Mac-Computer über ein USB-Kabel. Schließen **Fotos**, **iTunes** und andere Apps, die für das Gerät geöffnet werden, wenn das Gerät erkannt wird.

    3.  Klicken Sie in Apple Configurator mit einem Einmalklick auf das verbundene iOS-Gerät, und wählen Sie dann die Schaltfläche **Hinzufügen**. Optionen, die dem Gerät hinzugefügt werden können, werden in der Dropdownliste angezeigt. Wählen Sie **Profile** .

    4.  Verwenden Sie die Dateiauswahl zum Auswählen der aus Intune exportierten MOBILECONFIG-Datei, und wählen Sie dann **Hinzufügen**. Das Profil wird zum Gerät hinzugefügt.  Wenn das Gerät **nicht überwacht** wird, muss der Installation auf dem Gerät zugestimmt werden.

8.  **Installieren des Profils** Sie können das Profil nun auf dem iOS-Gerät installieren. Auf dem Gerät muss der Setup-Assistent ausgeführt worden sein, und es muss einsatzbereit sein.  Wenn bei der Registrierung Apps bereitgestellt werden müssen, sollten Sie über eine Apple-ID verfügen, da Sie für App-Bereitstellungen mit einer Apple-ID beim App Store angemeldet sein müssen.

    ###### Fertigstellen der Profilannahme für nicht überwachte iOS-Geräte

    1.  Entsperren Sie das iOS-Gerät.

    2.  Tippen Sie im Dialogfeld **Profil installieren** für das **Verwaltungsprofil** auf **Installieren**.

    3.  Geben Sie die **Gerätekennung** oder die **Apple-ID** ein, falls erforderlich.

    4.  Akzeptieren Sie die **Warnung**, und tippen Sie auf **Installieren**.

    5.  Akzeptieren Sie die **Remotewarnung**, und tippen Sie auf **Vertrauen**.

    6.  Wenn mit der Meldung **Profil installiert** bestätigt wird, dass das Profil **installiert** wurde, wählen Sie **Fertig**.

9. **Überprüfen des Profils**
    Starten Sie auf dem iOS-Gerät **Einstellungen**, und wechseln Sie zu **Allgemein** &gt; **Device Management** &gt; **Management-Profil** &gt;. Vergewissern Sie sich, dass die Profilinstallation aufgeführt wird, und überprüfen Sie die iOS-Richtlinieneinschränkungen sowie die installierten Apps. Es kann bis zu 10 Minuten dauern, bis Richtlinieneinschränkungen und Apps auf dem Gerät angezeigt werden.

10. **Verteilen von Geräten** Das iOS-Gerät ist jetzt bei Intune registriert und wird verwaltet.


### Weitere Informationen:
[Vorbereitungen zum Registrieren von Geräten](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


