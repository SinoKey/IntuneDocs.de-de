---
title: "Registrieren von iOS-Geräten mit dem Setup-Assistenten | Microsoft Intune"
description: "Registrieren von unternehmenseigenen iOS-Geräten mithilfe des Apple Configurator-Tools, um die Geräte auf die Werkseinstellungen zurückzusetzen und für die Ausführung des Setup-Assistenten vorzubereiten."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: ea6a4732e747dccf9c42732c06bd1b8cdf20e91f


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent
Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird. Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück und bereitet es auf die Ausführung des Setup-Assistenten vor, um die Unternehmensrichtlinien für den neuen Benutzer des Geräts zu installieren.

## <a name="setup-assistant-enrollment-for-ios-devices-with-microsoft-intune"></a>Registrierung von iOS-Geräten bei Microsoft Intune über den Setup-Assistenten
Mit Apple Configurator können Sie ein iOS-Gerät auf die Werkseinstellungen zurücksetzen und auf die Einrichtung für den neuen Benutzer des Geräts vorbereiten. Bei dieser Methode muss das iOS-Gerät über USB mit einem Mac-Computer verbunden werden, um die Registrierung beim Unternehmen einzurichten. Vorausgesetzt wird die Verwendung von Apple Configurator 2.0. Bei den meisten Szenarien ist es erforderlich, dass die auf das iOS-Gerät angewendete Richtlinie **Benutzeraffinität** einschließt, um das Intune-Unternehmensportal zu aktivieren.

**Voraussetzungen**
* [Aktiviert für die iOS-Registrierung](set-up-ios-and-mac-management-with-microsoft-intune.md) durch Installieren eines APNs-Zertifikats
* Physischer Zugriff auf iOS-Geräte: Geräte müssen auf die Werkseinstellungen zurückgesetzt sein und dürfen keinen Kennwortschutz aufweisen
* Geräteseriennummern: siehe [Abrufen einer iOS-Seriennummer](https://support.apple.com/en-us/HT204308)
* USB-Verbindungskabel
* Mac-Computer mit [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Erstellen von mobilen Gerätegruppen** (optional).
    Wenn Ihr Unternehmen mobile Gerätegruppen zur Verwaltung von Geräten erfordert, erstellen Sie diese Gruppen. Weitere Informationen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Erstellen eines Profils für Geräte**.
    Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit Apple Configurator registriert werden.

    1.  Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie anschließend **Hinzufügen** aus.
    ![Erstellen eines Geräteregistrierungsprofils](../media/pol-sa-corp-enroll.png)

    2.  Geben Sie die Details für die Geräteprofile ein:

        -   **Name:** Der Name des Geräteregistrierungsprofils (für Benutzer nicht sichtbar).

        -   **Beschreibung:** Eine Beschreibung des Geräteregistrierungsprofils (für Benutzer nicht sichtbar).

        -   **Registrierungsdetails**: Gibt an, wie Geräte registriert werden.

            -   **Benutzeraffinität anfordern**: Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. **Benutzeraffinität** muss für DEP-verwaltete Geräte eingerichtet werden, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie z.B. die Installation von Apps nutzen zu können.

            -   **Keine Benutzeraffinität**: Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

        -   **Gerätegruppen-Vorabzuweisung**: Alle Geräte, die mit diesem Profil bereitgestellt werden, gehören anfänglich zu dieser Gruppe. Sie können die Geräte nach der Registrierung erneut zuweisen.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

        -  **Geräteregistrierungsprogramm**: Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) kann bei der Registrierung mit dem Setup-Assistenten nicht verwendet werden. Stellen Sie sicher, dass die Umschaltfläche auf **aus** festgelegt ist.

    3.  Wählen Sie **Profil speichern**, um das Profil hinzuzufügen.

3.  **Hinzufügen von iOS-Geräten für die Registrierung mit dem Setup-Assistenten**.
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Alle unternehmenseigenen Geräte** &gt; **Alle Geräte**, und wählen Sie dann **Geräte hinzufügen** aus. Sie können Geräte auf zwei Arten hinzufügen:

    ![Dialogfeld „Geräte hinzufügen“](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Hochladen einer CSV-Datei mit Seriennummern**: Erstellen Sie eine durch Trennzeichen getrennte Liste (CSV-Datei) mit zwei Spalten ohne Überschrift, die auf 5.000 Geräte oder 5 MB pro CSV-Datei beschränkt ist.

        |||
        |-|-|
        |&lt;Seriennummer 1&gt;|&lt;Details zu Gerät 1&gt;|
        |&lt;Seriennummer 2&gt;|&lt;Details zu Gerät 2&gt;|
        Diese CSV-Datei sieht bei Anzeige in einem Text-Editor folgendermaßen aus:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Manuelles Hinzufügen von Gerätedetails**&mdash;Geben Sie die Seriennummer und Gerätedetails von bis zu 15 Geräten ein.

    > [!NOTE]
    > Wenn Sie später unternehmenseigene Geräte aus der Intune-Verwaltung entfernen müssen, kann es notwendig sein, die Seriennummer der Geräte in Intune aus der Gerätegruppe **Nach iOS-Seriennummer** unter **Vorabregistrierte Unternehmensgeräte** zu entfernen, um die Geräteregistrierung zu deaktivieren. Wenn Intune eine Notfallwiederherstellung durchführt, während oder nachdem Sie Seriennummern entfernt haben, müssen Sie sicherstellen, dass in dieser Gruppe nur die Seriennummern aktiver Geräte vorhanden sind.

    Klicken Sie auf **Weiter**.

4.  **Auswählen der zu registrierenden Geräte**.
    Bestätigen Sie die zu registrierenden Geräte. Bereits registrierte oder anderweitig registrierte Seriennummern werden nicht importiert. Klicken Sie auf **Weiter**, um fortzufahren.

5.  **Zuweisen eines Profils**.
    Geben Sie das Profil an, das hinzugefügten Geräten aus der Liste der verfügbaren Profile zugewiesen werden soll, überprüfen Sie die **Registrierungsprofildetails**, und wählen Sie dann **Fertig stellen** aus. Manuell hinzugefügte Geräte können einem beliebigen Registrierungsprofil zugewiesen werden.

6.  **Exportieren eines Profils zum Bereitstellen auf iOS-Geräten**.
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie das Geräteprofil aus, das auf mobilen Geräten bereitgestellt werden soll. Wählen Sie in der Taskleiste **Exportieren** aus. Kopieren und speichern Sie die **Profil-URL**. Sie werden sie später in Apple Configurator hochladen, um das von iOS-Geräten verwendete Intune-Profil zu definieren.
    Zur Unterstützung von Apple Configurator 2 muss die URL des 2.0-Profils bearbeitet werden. Ersetzen Sie dafür diesen Code:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    durch diesen Code:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Sie laden im folgenden Verfahren diese Profil-URL mit Apple Configurator in den Apple DEP-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.



7.  **Vorbereiten des Geräts mit Apple Configurator**.
    iOS-Geräte werden mit dem Mac-Computer verbunden und für die Verwaltung mobiler Geräte registriert.

    1.  Öffnen Sie auf einem Mac-Computer **Apple Configurator 2**. Wählen Sie in der Menüleiste **Apple Configurator 2**, und wählen Sie dann **Voreinstellungen**.

         > [!WARNING]
         > Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt. Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten. Nach dem Verbinden eines Geräts sollte der **Begrüßungsbildschirm** angezeigt werden.

    2. Wählen Sie im Bereich „Voreinstellungen“ die Option **Server** aus, und wählen Sie das Pluszeichen, um den MDM-Server-Assistenten zu starten. Klicken Sie auf **Weiter**.

    3. Geben Sie den **Namen** und die **Registrierungs-URL** für den MDM-Server ein, den Sie unter „Registrierung von iOS-Geräten bei Microsoft Intune über den Setup-Assistenten“ in Schritt 6 kopiert und bearbeitet haben. Geben Sie für die Registrierungs-URL die aus Intune exportierte Registrierungsprofil-URL ein. Klicken Sie auf **Weiter**.  

       Sie können die Warnung, dass die Server-URL nicht überprüft wird, problemlos ignorieren. Um den Vorgang fortzusetzen, wählen Sie **Weiter**, bis der Assistent abgeschlossen ist.

    4.  Verbinden Sie die mobilen iOS-Geräte über einen USB-Adapter mit dem Mac-Computer.

        > [!WARNING]
        > Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt. Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten. Wenn Sie den Setup-Assistenten starten, sollte der **Begrüßungsbildschirm** zu sehen sein.

    5.  Wählen Sie **Vorbereiten**. Wählen Sie im Bereich „iOS-Gerät vorbereiten“ die Option **Manuell** aus, und wählen Sie dann **Weiter**.

    6. Wählen Sie im Bereich „Beim MDM-Server registrieren“ den erstellten Servernamen aus, und wählen Sie dann **Weiter**.

    7. Wählen Sie im Bereich „Geräte überwachen“ den Grad der Überwachung aus, und wählen Sie dann **Weiter**.

    8. Wählen Sie im Bereich „Organisation erstellen“ die **Organisation** aus, oder erstellen Sie eine neue Organisation, und wählen Sie dann **Weiter**.

    9. Wählen Sie im Bereich „iOS-Setup-Assistenten konfigurieren“ die Schritte aus, die dem Benutzer angezeigt werden sollen, und wählen Sie dann **Vorbereiten**. Authentifizieren Sie sich, wenn Sie dazu aufgefordert werden, um die Vertrauenseinstellungen zu aktualisieren.  

    10. Trennen Sie das USB-Kabel, wenn die Vorbereitung des iOS-Geräts abgeschlossen ist.  

8.  **Verteilen von Geräten**.
    Die Geräte sind nun für die Unternehmensregistrierung bereit. Schalten Sie die Geräte aus, und verteilen Sie sie an Benutzer. Wenn die Benutzer die Geräte einschalten, wird der Setup-Assistent gestartet.



### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO2-->


