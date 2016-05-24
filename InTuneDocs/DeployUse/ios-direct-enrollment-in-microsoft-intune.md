---
# required metadata

title: Direkte Registrierung von iOS-Geräten bei Microsoft Intune | Microsoft Intune
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
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Direkte Registrierung von iOS-Geräten mit Apple Configurator
Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird. Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode ist für Geräte mit der Einstellung **Keine Benutzeraffinität** vorgesehen und erfordert eine USB-Verbindung des iOS-Geräts mit einem Mac-Computer, um die Registrierung beim Unternehmen einzurichten. Die Unternehmensportal-App wird für direkte registrierte Geräte nicht unterstützt. Diese Anleitung setzt voraus, dass Sie Apple Configurator 2.0 auf einem Mac-Computer verwenden.

1.  **Erstellen eines Profils für Geräte**
    Ein Registrierungsprofil für Geräte definiert die Einstellungen für Geräte. Wenn Sie dies noch nicht getan haben, erstellen Sie ein Registrierungsprofil für iOS-Geräte, die mit Apple Configurator registriert werden.

    #### So erstellen Sie ein Profil

    1.  Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und klicken Sie dann auf **Hinzufügen**..

        ![Erstellen einer Profilseite für die Geräteregistrierung](../media/pol-sa-corp-enroll.png)

    2.  Geben Sie die Details für die Geräteprofile ein:

        -   **Name** : Name des Geräteanmeldungsprofils. Für Benutzer nicht sichtbar.

        -   **Beschreibung**: Beschreibung des Geräteanmeldungsprofils. Für Benutzer nicht sichtbar.

        -   **Benutzerzuweisung** : Gibt an, wie Geräte registriert werden. Wählen Sie für die direkte Registrierung **Keine Benutzeraffinität**aus..

        -   **Gerätegruppen-Vorabzuweisung**: Alle Geräte, die mit diesem Profil bereitgestellt werden, gehören anfänglich zu dieser Gruppe. Sie können die Geräte nach der Registrierung erneut zuweisen.

    3.  Klicken Sie auf **Profil speichern** , um das Profil hinzuzufügen.

2.  **Hinzufügen von mit Apple Configurator zu registrierenden iOS-Geräten**
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorab registrierte Unternehmensgeräte** &gt; **Nach iOS-Seriennummer**, und klicken Sie dann auf **Geräte hinzufügen**..

    ![iOS-Setup-Assistent](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Sie können Geräte auf zwei Arten hinzufügen:

    -   **Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Überschrift, die auf 5000 Geräte oder 5 MB pro CSV-Datei beschränkt ist.

        |||
        |-|-|
        |&lt;Seriennumer1&gt;|&lt;Details zu Gerät1&gt;|
        |&lt;Seriennummer2&gt;|&lt;Details zu Gerät2&gt;|
        Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Gerätedetails manuell hinzufügen**: Geben Sie die Seriennummer und Gerätedetails von bis zu fünf Geräten ein, und klicken Sie dann auf **Weiter**..

    > [!NOTE]
    > Wenn Sie später firmeneigene Geräte aus der Intune-Verwaltung entfernen möchten, müssen Sie die Seriennummer des Geräts in Intune aus der Gruppe **Firmeneigene Geräte** entfernen, um die Geräteregistrierung zu deaktivieren.  Wenn Intune eine Notfallwiederherstellung durchführt, während oder nachdem Seriennummern entfernt wurden, müssen Sie sicherstellen, dass in dieser Gruppe nur die Seriennummern aktiver Geräte vorhanden sind.

3.  **Auswählen der zu registrierenden Geräte**
    Bestätigen Sie die zu registrierenden Geräte. Bereits registrierte oder anderweitig registrierte Seriennummern werden nicht importiert. Klicken Sie zum Fortfahren auf **Weiter** .

4.  **Zuweisen eines Profils**
    Geben Sie das Profil an, das hinzugefügten Geräten aus der Liste der verfügbaren Profile zugewiesen werden soll, überprüfen Sie die **Registrierungsprofildetails**, und klicken Sie dann auf **Fertig stellen**. Manuell hinzugefügte Geräte können einem beliebigen Anmeldungsprofil zugewiesen werden.

5.  **Auswählen eines Profils zum Bereitstellen auf iOS-Geräten**
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie das Geräteprofil aus, das auf mobilen Geräten bereitgestellt werden soll. Dieses Profil sollte das gleiche Profil sein, das Sie im vorherigen Schritt für die Bereitstellung zugewiesen haben. Klicken Sie auf **Exportieren…** in der Taskleiste. Klicken Sie auf **Profil herunterladen**, und speichern Sie die heruntergeladene MOBILECONFIG-Datei.

6.  **Übertragen der Datei**
    Kopieren Sie die heruntergeladene MOBILECONFIG-Datei auf einem Mac-Computer.
    > [!NOTE]
    > Die Anmeldungsprofil-URL ist ab dem Export zwei Wochen lang gültig. Nach zwei Wochen müssen Sie eine neue Anmeldungsprofil-URL zum Registrieren von iOS-Geräten mit dem Setup-Assistenten exportieren.
7.  **Vorbereiten des Geräts mit Apple Configurator**
    iOS-Geräte werden mit dem Mac-Computer verbunden und für die Verwaltung mobiler Geräte registriert.

    1.  Starten Sie auf einem Mac-Computer **Apple Configurator 2.0**..

    2.  Verbinden Sie das iOS-Gerät mit dem Mac-Computer über ein USB-Kabel. Schließen **Fotos**, **iTunes** und andere Apps, die für das Gerät geöffnet werden, wenn das Gerät erkannt wird.

    3.  Klicken Sie in Apple Configurator mit einem Einmalklick auf das verbundene iOS-Gerät, und klicken Sie dann auf die Schaltfläche **Hinzufügen**. Optionen, die dem Gerät hinzugefügt werden können, werden in der Dropdownliste angezeigt. Klicken Sie auf **Profile**. .

    4.  Verwenden Sie die Dateiauswahl zum Auswählen der aus Intune exportierten MOBILECONFIG-Datei, und klicken Sie dann auf **Hinzufügen**. Das Profil wird zum Gerät hinzugefügt.  Wenn das Gerät **nicht überwacht** wird, muss der Installation auf dem Gerät zugestimmt werden.

8.  **Installieren des Profils**
    Sie können das Profil nun auf dem iOS-Gerät installieren. Auf dem Gerät muss der Setup-Assistent ausgeführt worden sein, und es muss einsatzbereit sein.  Wenn bei der Registrierung Apps bereitgestellt werden müssen, sollten Sie über eine Apple-ID verfügen, da Sie für App-Bereitstellungen mit einer Apple-ID beim App Store angemeldet sein müssen.

    ###### Fertigstellen der Profilannahme für nicht überwachte iOS-Geräte

    1.  Entsperren Sie das iOS-Gerät.

    2.  Tippen Sie im Dialogfeld **Profil installieren** für das **Verwaltungsprofil** auf **Installieren**..

    3.  Geben Sie die **Gerätekennung** oder die **Apple-ID** ein, falls erforderlich.

    4.  Akzeptieren Sie die **Warnung**, und tippen Sie auf **Installieren**..

    5.  Akzeptieren Sie die **Remotewarnung**, und tippen Sie auf **Vertrauen**..

    6.  Wenn mit der Meldung **Profil installiert** bestätigt wird, dass das Profil **installiert** wurde, klicken Sie auf **Fertig**..

9. **Überprüfen des Profils**
    Starten Sie auf dem iOS-Gerät **Einstellungen**, und wechseln Sie zu **Allgemein** &gt; **Device Management** &gt; **Management-Profil** &gt;, vergewissern Sie sich, dass die Profilinstallation aufgeführt ist. Überprüfen Sie die iOS-Richtlinieneinschränkungen und installierten Apps. Es kann bis zu 10 Minuten dauern, bis Richtlinieneinschränkungen und Apps auf dem Gerät angezeigt werden.

10. **Verteilen von Geräten**
    Das iOS-Gerät ist jetzt bei Intune registriert und wird verwaltet.


### Weitere Informationen:
[Vorbereitungen zum Registrieren von Geräten](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


