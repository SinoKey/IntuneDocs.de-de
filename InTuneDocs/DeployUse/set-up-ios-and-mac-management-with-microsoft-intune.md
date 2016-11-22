---
title: Einrichten der iOS- und Mac-Verwaltung | Microsoft Intune
description: "Aktivieren Sie die mobile Geräteverwaltung (Mobile Device Management, MDM) für iOS-Geräte einschließlich iPads und iPhones sowie Mac OS X-Geräte mit Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d51f34dea3463bec83ea39cdfb79c7bedf9e3926
ms.openlocfilehash: 930419b20b675aa48c2b8bf1c49a1b576bbab414


---

# <a name="set-up-ios-and-mac-device-management"></a>Einrichten der iOS- und Mac-Geräteverwaltung
Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads, iPhones und Mac OS X-Geräte und ermöglicht Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps. Zum Verwalten von iOS- und Mac-Geräten benötigen Sie ein APNS-Zertifikat (Apple Push Notification Service). Sobald das Zertifikat in Intune hinzugefügt ist, können Benutzer die Unternehmensportal-App zur Registrierung ihrer Geräte installieren, oder der Administrator kann die [Verwaltung von firmeneigenen iOS-Geräten](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) einrichten.

1.  **Einrichten von Intune**<br>
    Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#set-mobile-device-management-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2.  **Abrufen einer Zertifikatsignierungsanforderung**<br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), navigieren Sie zu **Verwaltung** &gt; ** Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikatanforderung herunterladen** aus. Speichern Sie die Zertifikatsignierungsanforderung (CSR-Datei) lokal. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.

    ![Dialogfeld „APNs-Zertifikat hochladen“](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Abrufen eines Apple Push Notification Service-Zertifikats**<br>
    Wechseln Sie zum [Apple Push Certificates-Portal](http://go.microsoft.com/fwlink/?LinkId=269844), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an, um das APNs-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Apple Push Certificates-Portal **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei, die für APNs nicht verwendet werden kann. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für **Zertifikate für Drittanbieterserver** zurück, und wählen Sie anschließend **Herunterladen** aus.

    Laden Sie das APNs-Zertifikat (.pem) herunter, und speichern Sie die Datei lokal. Diese Apple-ID muss später verwendet werden, um das APNs-Zertifikat zu erneuern.

4.  **Hinzufügen des APNs-Zertifikats zu Intune**<br>
    Navigieren Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikat hochladen** aus. Wechseln Sie zur Zertifikatdatei (.pem), wählen Sie **Öffnen** aus, und geben Sie anschließend Ihre **Apple-ID**ein. Mit dem APNs-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

5.  **Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können.**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres iOS-Geräts bei Intune](../enduser/enroll-your-device-in-intune-ios.md) oder unter [Registrieren Ihres Mac OS X-Geräts bei Intune](../enduser/enroll-your-device-in-intune-mac-os-x.md). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

    Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:
    - [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Endbenutzer-Leitfaden für iOS- und Mac-Geräte](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Wenn Ihr Unternehmen oder Ihre Organisation iOS-Geräte für Benutzer erwirbt, können diese Geräte ebenfalls zur Verwaltung als [unternehmenseigene iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) registriert werden.

### <a name="see-also"></a>Weitere Informationen
[Voraussetzungen für die Registrierung bei Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO2-->


