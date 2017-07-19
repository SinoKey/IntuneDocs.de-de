---
title: "Registrieren von iOS-Geräten – Apple Configurator – Setup-Assistent"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mit Apple Configurator und dem Setup-Assistenten registrieren.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Registrieren von iOS-Geräten mit Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), das auf einem Mac-Computer ausgeführt wird. Für die Registrierung mit Apple Configurator müssen Sie jedes iOS-Gerät über USB mit einem Mac-Computer verbinden, um die Unternehmensregistrierung einzurichten. Sie können Geräte mit Apple Configurator auf zwei Arten bei Intune registrieren:
- **Registrierung per Setup-Assistent**: Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück, bereitet es auf die Ausführung des Setup-Assistenten vor und installiert die Unternehmensrichtlinien für den neuen Benutzer des Geräts. Bei den meisten Szenarien ist es erforderlich, dass die auf das iOS-Gerät angewendete Richtlinie Benutzeraffinität einschließt, um das Intune-Unternehmensportal zu aktivieren.
- **Direkte Registrierung**: Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode eignet sich für Geräte **ohne Benutzeraffinität**.

>[!NOTE]
>Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) verwendet werden.

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](enrollment-method-choose-ios.md) beschriebenen.

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von iOS-Geräten erfüllt sein:

- [Ein Apple-MDM-Push-Zertifikat](apple-mdm-push-certificate-get.md)
- Physischer Zugriff auf iOS-Geräte
- Geräteseriennummern (siehe [Abrufen einer iOS-Seriennummer](https://support.apple.com//HT204308))
- USB-Verbindungskabel
- Mac-PC mit [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Hinzufügen von Apple Configurator-Seriennummern](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Registrierung mit dem Setup-Assistenten

### <a name="create-an-apple-configurator-profile-for-devices"></a>Erstellen eines Apple Configurator-Profils für Geräte

Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit Apple Configurator registriert werden.

1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
2. Wählen Sie unter **Apple Configurator-Registrierungseinstellungen verwalten** die Option **AC-Profile** aus.
3. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** die Option **Erstellen** aus.
4. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.
5. Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

   - **Mit Benutzeraffinität registrieren:** Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Die Benutzeraffinität sollte für verwaltete Geräte eingerichtet sein, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie die Installation von Apps nutzen zu können.
   - **Ohne Benutzeraffinität registrieren:** Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

6. Wählen Sie **Erstellen** aus, um das Profil zu speichern.

### <a name="add-apple-configurator-serial-numbers"></a>Hinzufügen von Apple Configurator-Seriennummern

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wenden Sie diese Schritte an, um in Intune Seriennummern für das [Registrieren unternehmenseigener iOS-Geräte mithilfe von Apple Configurator mit Setup-Assistent](apple-configurator-setup-assistant-enroll-ios.md) hinzuzufügen. Sie können Seriennummern einzeln hinzufügen oder eine mit Komma getrennte CSV-Datei mit Seriennummern hochladen. Nachdem Sie Seriennummern hinzugefügt haben, können Sie ihnen ein Profil zuweisen. Das Profil enthält die spezifischen Verwaltungseinstellungen, die Sie auf Geräte anwenden möchten.

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](enrollment-method-choose-ios.md) beschriebenen.

**So fügen Sie Apple Configurator-Seriennummern in Intune hinzu**

1. Erstellen Sie eine Liste mit zwei Spalten, die durch Trennzeichen getrennte werden (CSV), und ohne Header. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Der aktuelle Höchstwert für die Liste ist 500 Zeilen. In einem Text-Editor sieht die CSV-Liste etwa wie folgt aus:

    F7TLWCLBX196,Gerätedetails</br>
    DLXQPCWVGHMJ, Gerätedetails

2. Wählen Sie im Azure-Portal nacheinander die Optionen **Geräte registrieren** und **Apple-Registrierung** aus.
3. Wählen Sie unter **Apple Configurator-Registrierungseinstellungen verwalten** die Option **Apple Configurator-Seriennummern** aus.
4. Wählen Sie auf dem Blatt **Apple Configurator-Seriennummern** die Option **Hinzufügen** aus.
5. Wählen Sie auf dem Blatt **Seriennummern hinzufügen** ein Profil aus, das Sie auf die importierten Seriennummern anwenden möchten. Wenn Sie eine Datei mit den neuen Daten importieren, werden die bereits vorhandenen überschrieben. Wählen Sie „Hiermit überschreiben Sie Details für vorhandene Bezeichner“ aus, um die vorhandenen Bezeichner durch die neuen zu ersetzen.
6. Navigieren Sie zu der CSV-Datei mit den Seriennummern, und wählen Sie **Hinzufügen** aus.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Zuweisen eines Profils zu bestimmten Seriennummern

Mit Intune können Sie Profile von zwei verschiedenen Stellen im Azure-Portal zuweisen. Die Zuweisung kann gemäß Apple Configurator-Profil oder je Gerät erfolgen.

#### <a name="assign-by-devices"></a>Zuweisen je Gerät
1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
3. Wählen Sie auf dem Blatt **Apple Configurator-Geräte** die Seriennummern aus, denen Sie ein Profil zuweisen möchten, und wählen Sie dann **Profil zuweisen** aus.
4. Wählen Sie auf dem Blatt **Profil zuweisen** das Profil, das Sie zuweisen möchten, und dann **Zuweisen** aus.

#### <a name="assign-by-profiles"></a>Zuweisen gemäß Profil
1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung** und **Apple-Registrierung** aus.
2. Wählen Sie **AC-Profile** aus, und wählen Sie dann das Profil aus, dem Sie Seriennummern zuweisen möchten.
3. Wählen Sie auf dem Blatt mit dem Namen des Profils **Seriennummern** > **Zuweisen** aus.
4. Wählen Sie die Seriennummern aus, die Sie dem Profil zuweisen möchten, und wählen Sie dann die Schaltfläche **Zuweisen** aus.

### <a name="export-the-profile-to-ios-devices"></a>Exportieren des Profils auf iOS-Geräte
Nachdem Sie das Profil erstellt und Seriennummern zugewiesen haben, müssen Sie das Profil aus Intune exportieren – entweder als URL oder als Datei in einem der unten beschriebenen Formate. Importieren Sie es dann manuell in das Apple Configurator-Programm auf einem Mac. Anschließend wird es von Apple Configurator auf Geräten bereitgestellt.

1. Wählen Sie im Intune-Portal das Blatt **Apple Configurator-Registrierungsprofile** und dann das zu exportierende Profil aus.
2. Wählen Sie auf dem Blatt für das Profil **Profil exportieren** aus.
3. Kopieren Sie die Profil-URL in [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) bei angeschlossenem iOS-Gerät. Sie werden sie später in Apple Configurator hochladen, um das von iOS-Geräten verwendete Intune-Profil zu definieren.

  Sie laden im folgenden Verfahren diese Profil-URL mit Apple Configurator in den Apple-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.
4. Laden Sie diese Profil-URL mit Apple Configurator in den Apple-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.
 1.  Öffnen Sie auf einem Mac-Computer **Apple Configurator 2**. Wählen Sie in der Menüleiste **Apple Configurator 2**, und wählen Sie dann **Voreinstellungen**.
  > [!WARNING]
  > Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt. Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten. Nach dem Verbinden eines Geräts sollte der **Begrüßungsbildschirm** angezeigt werden.
  2. Wählen Sie im Bereich **Voreinstellungen** die Option **Server** und dann das Pluszeichen (+) aus, um den MDM-Server-Assistenten zu starten. Klicken Sie auf **Weiter**.
  3. Geben Sie den **Hostnamen oder die URL** und die **Registrierungs-URL** für den MDM-Server unter „Registrierung von iOS-Geräten bei Microsoft Intune über den Setup-Assistenten“. Geben Sie für die Registrierungs-URL die aus Intune exportierte Registrierungsprofil-URL ein. Klicken Sie auf **Weiter**.  

    Sie können die Warnung, dass die Server-URL nicht überprüft wird, problemlos ignorieren. Um den Vorgang fortzusetzen, wählen Sie **Weiter**, bis der Assistent abgeschlossen ist.
  4.  Verbinden Sie die mobilen iOS-Geräte über einen USB-Adapter mit dem Mac-Computer.
  > [!WARNING]
  > Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt. Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten. Wenn Sie den Setup-Assistenten starten, sollte der **Begrüßungsbildschirm** zu sehen sein.
  5.  Wählen Sie **Vorbereiten**. Wählen Sie im Bereich **iOS-Gerät vorbereiten** die Option **Manuell** aus, und wählen Sie dann **Weiter**.
  6. Wählen Sie im Bereich **Beim MDM-Server registrieren** den erstellten Servernamen und dann **Weiter** aus.
  7. Wählen Sie im Bereich **Geräte überwachen** den Grad der Überwachung aus, und wählen Sie dann **Weiter**.
  8. Wählen Sie im Bereich **Organisation erstellen** die **Organisation** aus, oder erstellen Sie eine neue Organisation, und wählen Sie dann **Weiter** aus.
  9. Wählen Sie im Bereich **iOS-Setup-Assistenten konfigurieren** die Schritte aus, die dem Benutzer angezeigt werden sollen, und wählen Sie dann **Vorbereiten** aus. Authentifizieren Sie sich, wenn Sie dazu aufgefordert werden, um die Vertrauenseinstellungen zu aktualisieren.  
  10. Trennen Sie das USB-Kabel, wenn die Vorbereitung des iOS-Geräts abgeschlossen ist.  
6.  **Verteilen von Geräten**.
    Die Geräte sind nun für die Unternehmensregistrierung bereit. Schalten Sie die Geräte aus, und verteilen Sie sie an Benutzer. Wenn die Benutzer die Geräte einschalten, wird der Setup-Assistent gestartet.

## <a name="direct-enrollment"></a>Direkte Registrierung
Wenn Sie iOS-Geräte direkt mit Apple Configurator registrieren, können Sie ein Gerät registrieren, ohne die Seriennummer des Geräts abrufen zu müssen. Sie können dem Gerät zu Identifikationszwecken auch einen Namen zuweisen, bevor Intune den Gerätenamen während der Registrierung erfasst. Die Unternehmensportal-App wird für direkt registrierte Geräte nicht unterstützt. Diese Anleitung setzt voraus, dass Sie Apple Configurator 2.0 auf einem Mac-Computer verwenden.

1. Wählen Sie im Intune-Portal nacheinander die Optionen **Geräteregistrierung**, **Apple-Registrierung** und **AC-Profile** aus.
2. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** die Option **Erstellen** aus.
3. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.
4. Wählen Sie für **Benutzeraffinität** die Option **Ohne Benutzeraffinität registrieren** aus, um sicherzustellen, dass das Gerät keinem Benutzer zugeordnet ist. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.
5. Wählen Sie **Erstellen** aus, um das Profil zu speichern.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exportieren des Profil als MOBILECONFIG-Datei auf iOS-Geräte

1. Laden Sie auf dem Blatt **Profil exportieren** das Registrierungsprofil in [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) herunter, um es als Verwaltungsprofil direkt per Push auf ein verbundenes iOS-Gerät zu verschieben. Eine Zurücksetzung des Geräts auf Werkseinstellungen ist bei dieser Vorgehensweise nicht erforderlich.
2. Bereiten Sie das Gerät mit Apple Configurator mithilfe der folgenden Schritte vor.
  1. Öffnen Sie auf einem Mac-Computer Apple Configurator 2.0.
  2. Verbinden Sie das iOS-Gerät mit dem Mac-Computer über ein USB-Kabel. Schließen Sie Fotos, iTunes und andere Apps, die für das Gerät geöffnet werden, wenn das Gerät erkannt wird.
  3. Wählen Sie in Apple Configurator das verbundene iOS-Gerät und anschließend die Schaltfläche **Hinzufügen** aus. Optionen, die dem Gerät hinzugefügt werden können, werden in der Dropdownliste angezeigt. Wählen Sie **Profile** aus.
  4. Verwenden Sie die Dateiauswahl zum Auswählen der aus Intune exportierten MOBILECONFIG-Datei, und wählen Sie anschließend **Hinzufügen** aus. Das Profil wird zum Gerät hinzugefügt. Wenn das Gerät nicht überwacht wird, muss der Installation auf dem Gerät zugestimmt werden.
3. Installieren Sie das Profil nun anhand der folgenden Schritte auf dem iOS-Gerät. Auf dem Gerät muss der Setup-Assistent ausgeführt worden sein, und es muss einsatzbereit sein. Wenn bei der Registrierung Apps bereitgestellt werden müssen, sollten Sie über eine Apple-ID verfügen, da Sie für App-Bereitstellungen mit einer Apple-ID beim App Store angemeldet sein müssen.
   1. Entsperren Sie das iOS-Gerät.
   2. Wählen Sie im Dialogfeld **Profil installieren** für das **Verwaltungsprofil** die Option **Installieren** aus.
   3. Geben Sie die Gerätekennung oder die Apple-ID ein, falls erforderlich.
   4. Akzeptieren Sie die **Warnung**, und wählen Sie **Installieren** aus.
   5. Akzeptieren Sie die **Remotewarnung**, und wählen Sie **Vertrauen** aus.
   6. Wenn mit der Meldung **Profil installiert** bestätigt wird, dass das Profil installiert wurde, wählen Sie **Fertig** aus.

    4. Öffnen Sie auf dem iOS-Gerät **Einstellungen**, und wechseln Sie zu **Allgemein** > **Geräteverwaltung** > **Verwaltungsprofil**. Vergewissern Sie sich, dass die Profilinstallation aufgelistet ist, und überprüfen Sie die iOS-Richtlinieneinschränkungen und die installierten Apps. Es kann bis zu 10 Minuten dauern, bis Richtlinieneinschränkungen und Apps auf dem Gerät angezeigt werden.

    5. Verteilen von Geräten. Das iOS-Gerät ist jetzt bei Intune registriert und wird verwaltet.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installieren und Verwenden das Unternehmensportals auf Geräten

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Nachdem Benutzer ihre Geräte erhalten haben, müssen sie zusätzliche, unten beschriebene Schritte ausführen, um den Setup-Assistenten abzuschließen und die Unternehmensportal-App zu installieren.
