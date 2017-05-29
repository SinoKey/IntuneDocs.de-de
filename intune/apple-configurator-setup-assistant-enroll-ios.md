---
title: "Registrieren von iOS-Geräten – Apple Configurator – Setup-Assistent"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mit Apple Configurator und dem Setup-Assistenten registrieren."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6b0bc51515a2b72c7574a7ca7e29c094f3bdbdb
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), das auf einem Mac-Computer ausgeführt wird. Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück, bereitet es auf die Ausführung des Setup-Assistenten vor, und installiert die Unternehmensrichtlinien für den neuen Benutzer des Geräts.

>[!NOTE]
>Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) verwendet werden.

Mit Apple Configurator können Sie ein iOS-Gerät auf die Werkseinstellungen zurücksetzen und auf die Einrichtung für den neuen Benutzer des Geräts vorbereiten. Bei dieser Methode muss das iOS-Gerät über USB mit einem Mac-Computer verbunden werden, um die Registrierung beim Unternehmen einzurichten. Vorausgesetzt wird die Verwendung von Apple Configurator 2.0. Bei den meisten Szenarien ist es erforderlich, dass die auf das iOS-Gerät angewendete Richtlinie Benutzeraffinität einschließt, um das Intune-Unternehmensportal zu aktivieren.

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](enrollment-method-choose-ios.md) beschriebenen.

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von iOS-Geräten erfüllt sein:

- [Abrufen eines Apple-MDM-Push-Zertifikats](apple-mdm-push-certificate-get.md)
- Sicherstellen des physischen Zugriffs auf die iOS-Geräte
- Bereithalten der Geräteseriennummern (siehe [Abrufen einer iOS-Seriennummer](https://support.apple.com//HT204308))
- Haben Sie ein USB-Verbindungskabel zur Hand
- Bereithalten eines Mac-Rechners mit installiertem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Hinzufügen von Apple Configurator-Seriennummern](apple-configurator-serial-numbers-add.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Erstellen eines Apple Configurator-Profils für Geräte

Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit Apple Configurator registriert werden.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

3. Wählen Sie unter **Apple Configurator-Registrierungseinstellungen verwalten** die Option **AC-Profile** aus.

4. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** die Option **Erstellen** aus.

5. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.

6. Wählen Sie für **Benutzeraffinität** aus, ob Geräte mit diesem Profil mit oder ohne Benutzeraffinität registriert werden.

   - **Mit Benutzeraffinität registrieren:** Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen. Die Benutzeraffinität sollte für verwaltete Geräte eingerichtet sein, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie die Installation von Apps nutzen zu können.

   - **Ohne Benutzeraffinität registrieren:** Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

7. Wählen Sie **Erstellen** aus, um das Profil zu speichern.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Zuweisen von Seriennummern zu einem Apple Configurator-Profil

Nachdem Sie Apple Configurator-Profile erstellt haben, können Sie den Profilen Geräteseriennummern zuweisen. Um Seriennummern zuweisen zu können, müssen Sie diese zunächst anhand der Schritte in [Hinzufügen von Apple Configurator-Seriennummern](apple-configurator-serial-numbers-add.md) in Intune hinzufügen.

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Zuweisen von Seriennummern zu Apple Configurator-Profilen

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** das Profil aus, dem Sie Seriennummern zuweisen möchten.

3. Wählen Sie auf dem Blatt mit dem Namen des Profils **Seriennummern** > **Zuweisen** aus.

4. Wählen Sie die Seriennummern aus, die Sie dem Profil zuweisen möchten, und wählen Sie dann die Schaltfläche **Zuweisen** aus.

## <a name="export-the-profile-to-ios-devices"></a>Exportieren des Profils auf iOS-Geräte

Nachdem Sie das Profil erstellt und Seriennummern zugewiesen haben, müssen Sie das Profil aus Intune exportieren – entweder als URL oder als Datei in einem der unten beschriebenen Formate. Importieren Sie es dann manuell in das Apple Configurator-Programm auf einem Mac. Anschließend wird es von Apple Configurator auf Geräten bereitgestellt.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Exportieren eines Profils mithilfe der Setup-Assistent-Registrierung

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** das zu exportierende Profil aus.

3. Wählen Sie auf dem Blatt für das Profil **Profil exportieren** aus.

4. Kopieren Sie die Profil-URL in [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) bei angeschlossenem iOS-Gerät. Sie werden sie später in Apple Configurator hochladen, um das von iOS-Geräten verwendete Intune-Profil zu definieren.

  Sie laden im folgenden Verfahren diese Profil-URL mit Apple Configurator in den Apple-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.

5. Laden Sie diese Profil-URL mit Apple Configurator in den Apple-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.
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

    Weitere Informationen finden Sie unter [So informieren sie Ihre Endbenutzer über Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Sie können die Endbenutzer auch auf [Verwenden Ihres iOS- oder Mac OS-Geräts mit Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) verweisen.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installieren und Verwenden das Unternehmensportals auf Geräten

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Nachdem Benutzer ihre Geräte erhalten haben, müssen sie zusätzliche, unten beschriebene Schritte ausführen, um den Setup-Assistenten abzuschließen und die Unternehmensportal-App zu installieren.

