---
title: "Registrieren von iOS-Geräten mithilfe von Apple Configurator und direkter Registrierung"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie unternehmenseigene iOS-Geräte mit Apple Configurator und der direkten Registrierung registrieren."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b464a07e701797d39b7f9f50d1854a9a2682ac8e
ms.openlocfilehash: 3208e964f2676ebcc1e54e29f039c4965c20238f
ms.lasthandoff: 03/01/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Registrieren von iOS-Geräten mithilfe von Apple Configurator und direkter Registrierung 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), das auf einem Mac-Computer ausgeführt wird. Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode ist für Geräte mit der Einstellung **Keine Benutzeraffinität** vorgesehen und erfordert eine USB-Verbindung des iOS-Geräts mit einem Mac-Computer, um die Registrierung beim Unternehmen einzurichten.

>[!NOTE]
>Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](enroll-devices-using-device-enrollment-manager.md) verwendet werden.

Wenn Sie iOS-Geräte direkt registrieren, können Sie ein Gerät registrieren, ohne die Seriennummer des Geräts abrufen zu müssen. Sie können dem Gerät zu Identifikationszwecken auch einen Namen zuweisen, bevor Intune den Gerätenamen während der Registrierung erfasst. Die Unternehmensportal-App wird für direkt registrierte Geräte nicht unterstützt. Diese Anleitung setzt voraus, dass Sie Apple Configurator 2.0 auf einem Mac-Computer verwenden.

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](choose-ios-enrollment-method.md) beschriebenen.


## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von iOS-Geräten erfüllt sein:

- [Konfigurieren von Domänen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Festlegen der MDM-Autorität](set-mdm-authority.md)
- [Erstellen von Gruppen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurieren des Unternehmensportals](/intune-azure/manage-apps/company-portal-app)
- Zuweisen von Benutzerlizenzen im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Abrufen eines Apple-MDM-Push-Zertifikats](get-an-apple-mdm-push-certificate.md)
- Sicherstellen des physischen Zugriffs auf die iOS-Geräte
- Bereithalten der Geräteseriennummern (siehe [Abrufen einer iOS-Seriennummer](https://support.apple.com//HT204308))
- Haben Sie ein USB-Verbindungskabel zur Hand
- Bereithalten eines Mac-Rechners mit installiertem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Erstellen eines Apple Configurator-Profils für Geräte

Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten. Die folgenden Schritte zeigen, wie Sie ein Registrierungsprofil für iOS-Geräte erstellen, die mit Apple Configurator registriert werden.

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

3. Wählen Sie unter **Apple Configurator-Registrierungseinstellungen verwalten** die Option **AC-Profile** aus.

4. Wählen Sie auf dem Blatt **Apple Configurator-Registrierungsprofile** die Option **Erstellen** aus.

5. Geben Sie auf dem Blatt **Registrierungsprofil erstellen** einen Namen und eine Beschreibung für das Profil ein.

6. Wählen Sie für **Benutzeraffinität** die Option **Ohne Benutzeraffinität registrieren** aus, um sicherzustellen, dass das Gerät keinem Benutzer zugeordnet ist. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.

7. Wählen Sie **Erstellen** aus, um das Profil zu speichern.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exportieren des Profil als MOBILECONFIG-Datei auf iOS-Geräte

1. Laden Sie auf dem Blatt **Profil exportieren** das Registrierungsprofil in [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) herunter, um es als Verwaltungsprofil direkt per Push auf ein verbundenes iOS-Gerät zu verschieben. Eine Zurücksetzung des Geräts auf Werkseinstellungen ist bei dieser Vorgehensweise nicht erforderlich.

2. Bereiten Sie das Gerät mit Apple Configurator mithilfe der folgenden Schritte vor.

   a. Öffnen Sie auf einem Mac-Computer Apple Configurator 2.0.

   b. Verbinden Sie das iOS-Gerät mit dem Mac-Computer über ein USB-Kabel. Schließen Sie Fotos, iTunes und andere Apps, die für das Gerät geöffnet werden, wenn das Gerät erkannt wird.

   c. Wählen Sie in Apple Configurator das verbundene iOS-Gerät und anschließend die Schaltfläche **Hinzufügen** aus. Optionen, die dem Gerät hinzugefügt werden können, werden in der Dropdownliste angezeigt. Wählen Sie **Profile** aus.

   d. Verwenden Sie die Dateiauswahl zum Auswählen der aus Intune exportierten MOBILECONFIG-Datei, und wählen Sie anschließend **Hinzufügen** aus. Das Profil wird zum Gerät hinzugefügt. Wenn das Gerät nicht überwacht wird, muss der Installation auf dem Gerät zugestimmt werden.

3. Installieren Sie das Profil nun anhand der folgenden Schritte auf dem iOS-Gerät. Auf dem Gerät muss der Setup-Assistent ausgeführt worden sein, und es muss einsatzbereit sein. Wenn bei der Registrierung Apps bereitgestellt werden müssen, sollten Sie über eine Apple-ID verfügen, da Sie für App-Bereitstellungen mit einer Apple-ID beim App Store angemeldet sein müssen.

   a. Entsperren Sie das iOS-Gerät.

   b. Wählen Sie im Dialogfeld **Profil installieren** für das **Verwaltungsprofil** die Option **Installieren** aus.

   c. Geben Sie die Gerätekennung oder die Apple-ID ein, falls erforderlich.

   d. Akzeptieren Sie die **Warnung**, und wählen Sie **Installieren** aus.

   e. Akzeptieren Sie die **Remotewarnung**, und wählen Sie **Vertrauen** aus.

   f. Wenn mit der Meldung **Profil installiert** bestätigt wird, dass das Profil installiert wurde, wählen Sie **Fertig** aus.

4. Öffnen Sie auf dem iOS-Gerät **Einstellungen**, und wechseln Sie zu **Allgemein** > **Geräteverwaltung** > **Verwaltungsprofil**. Vergewissern Sie sich, dass die Profilinstallation aufgelistet ist, und überprüfen Sie die iOS-Richtlinieneinschränkungen und die installierten Apps. Es kann bis zu 10 Minuten dauern, bis Richtlinieneinschränkungen und Apps auf dem Gerät angezeigt werden.

5. Verteilen von Geräten. Das iOS-Gerät ist jetzt bei Intune registriert und wird verwaltet.

