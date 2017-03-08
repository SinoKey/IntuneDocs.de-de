---
title: Einrichten der iOS- und Mac-Verwaltung | Microsoft-Dokumentation
description: "Aktivieren Sie die mobile Geräteverwaltung (Mobile Device Management, MDM) für iOS-Geräte einschließlich iPads und iPhones sowie Mac OS X-Geräte mit Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: afca2af0b07b939adc66c8804f04a1125e12001b
ms.openlocfilehash: 9c71a83f9514187753360fa9c2085584d1b76711
ms.lasthandoff: 02/18/2017


---

# <a name="set-up-ios-and-mac-device-management"></a>Einrichten der iOS- und Mac-Geräteverwaltung

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads, iPhones und Mac OS-Geräte und ermöglicht Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps. Zum Verwalten von iOS- und Mac-Geräten benötigen Sie ein APNS-Zertifikat (Apple Push Notification Service). Sobald das Zertifikat in Intune hinzugefügt ist, können Benutzer die Unternehmensportal-App zur Registrierung ihrer Geräte installieren, oder der Administrator kann die [Verwaltung von firmeneigenen iOS-Geräten](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) einrichten.

1.  **Einrichten von Intune**<br>
    Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2.  **Abrufen einer Zertifikatsignierungsanforderung**<br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), navigieren Sie zu **Verwaltung** &gt; ** Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikatanforderung herunterladen** aus. Speichern Sie die Zertifikatsignierungsanforderung (CSR-Datei) lokal. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.

    ![Dialogfeld „APNs-Zertifikat hochladen“](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Abrufen eines Apple Push Notification Service-Zertifikats**<br>
    Wechseln Sie zum [Apple Push Certificates-Portal](http://go.microsoft.com/fwlink/?LinkId=269844), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an, um das APNs-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Apple Push Certificates-Portal **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei, die für APNs nicht verwendet werden kann. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für **Zertifikate für Drittanbieterserver** zurück, und wählen Sie anschließend **Herunterladen** aus.

    Laden Sie das APNs-Zertifikat (.pem) herunter, und speichern Sie die Datei lokal.

    > [!NOTE]
    > Sie müssen dieses APNs-Zertifikat jährlich verlängern (nicht ersetzen). Verwenden Sie dieselbe Apple-ID, um sich im Apple Push Certificate-Portal anzumelden und das Zertifikat zu verlängern. Folgen Sie dann denselben Anweisungen in diesem Thema, um das Zertifikat herunterzuladen und es dann in Intune hochzuladen.

4.  **Hinzufügen des APNs-Zertifikats zu Intune**<br>
    Navigieren Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikat hochladen** aus. Wechseln Sie zur Zertifikatdatei (.pem), wählen Sie **Öffnen** aus, und geben Sie anschließend Ihre **Apple-ID**ein. Mit dem APNs-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

5.  **Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres iOS-Geräts bei Intune](../enduser/enroll-your-device-in-intune-ios.md) oder unter [Registrieren Ihres Mac OS-Geräts bei Intune](../enduser/enroll-your-device-in-intune-macos.md). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

    Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:
    - [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
    - [Endbenutzer-Leitfaden für iOS- und Mac-Geräte](../enduser/using-your-ios-or-macOS-device-with-intune.md)

Wenn Ihr Unternehmen oder Ihre Organisation iOS-Geräte für Benutzer erwirbt, können diese Geräte ebenfalls zur Verwaltung als [unternehmenseigene iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) registriert werden.

### <a name="see-also"></a>Weitere Informationen
[Voraussetzungen für die Registrierung bei Microsoft Intune](prerequisites-for-enrollment.md)

