---
title: Einrichten der iOS- und Mac-Verwaltung | Microsoft Intune
description: "Aktivieren Sie die mobile Geräteverwaltung (Mobile Device Management, MDM) für iOS-Geräte einschließlich iPads und iPhones sowie Mac OS X-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: e61e764f4761ab83500ff6f0febe253d427729d9


---

# Einrichten der iOS- und Mac-Geräteverwaltung
[Hier](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md) finden Sie Unterstützung zum Einrichten Ihres iOS- oder Mac-Geräts.

Mobile Intune-Geräteverwaltung von iPads, iPhones und Mac OS X-Geräten und Erteilung des Zugriffs auf Unternehmens-E-Mail und Apps. Zum Verwalten von iOS- und Mac-Geräten benötigen Sie ein APNS-Zertifikat (Apple Push Notification Service). Sobald das Zertifikat in Intune hinzugefügt ist, können Benutzer die Unternehmensportal-App zur Registrierung ihrer Geräte installieren, oder der Administrator kann die [Verwaltung von firmeneigenen iOS-Geräten](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) einrichten.

1.  **Einrichten von Intune**<br>
    Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2.  **Abrufen einer Zertifikatsignierungsanforderung**<br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), navigieren Sie zu **Verwaltung** &gt; ** Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNS-Zertifikat hochladen**, und klicken Sie auf **APNS-Zertifikatanforderung herunterladen**. Speichern Sie die Zertifikatsignierungsanforderung (CSR-Datei) lokal. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.

    ![Dialogfeld „APNs-Zertifikat hochladen“](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Abrufen eines Apple Push Notification Service-Zertifikats**<br>
    Wechseln Sie zum [Apple Push Certificates-Portal](http://go.microsoft.com/fwlink/?LinkId=269844), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an, um das APNs-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Apple Push Certificates-Portal auf **Hochladen** geklickt haben, erhalten Sie eine JSON-Datei, die für APNs nicht verwendet werden kann. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für **Zertifikate für Drittanbieterserver** zurück, und klicken Sie auf **Herunterladen**.

    Laden Sie das APNs-Zertifikat (.pem) herunter, und speichern Sie die Datei lokal. Diese Apple-ID muss später verwendet werden, um das APNs-Zertifikat zu erneuern.

4.  **Hinzufügen des APNs-Zertifikats zu Intune**<br>
    Navigieren Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNS-Zertifikat hochladen**, und klicken Sie auf **APNS-Zertifikat hochladen**. **Wechseln Sie** zur Zertifikatdatei (.pem), klicken Sie auf **Öffnen** , und geben Sie Ihre **Apple-ID**ein. Mit dem APNs-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

5.  **Bereitstellen von Informationen für Benutzer zum Zugriff auf Unternehmensressourcen über das Unternehmensportal**<br>
    Ihre Benutzer müssen wissen, wie sie ihre Geräte registrieren können und was sie erwartet, wenn die Geräte in die Verwaltung eingebunden sind.
    - [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Endbenutzer-Leitfaden für iOS- und Mac-Geräte](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Wenn Ihr Unternehmen oder Ihre Organisation iOS-Geräte für Benutzer erwirbt, können diese Geräte ebenfalls zur Verwaltung als [unternehmenseigene iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) registriert werden.

### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


