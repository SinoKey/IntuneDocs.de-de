---
# required metadata

title: Einrichten der iOS- und Mac-Verwaltung | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einrichten der iOS- und Mac-Geräteverwaltung
Mit Microsoft Intune können Sie die BYOD-Registrierung („Bring Your Own Device“) für iOS- und Mac OS X-Geräte aktivieren, um iPhone-, iPad- und Mac-Benutzern Zugriff auf Unternehmens-E-Mail und -Apps zu gewähren. Nach der Registrierung können Benutzer die Intune-Unternehmensportal-App installieren, und über die Intune-Verwaltungskonsole können Richtlinien auf ihre Geräte angewendet werden.

Bevor Sie iOS-Geräte mit Intune verwalten können, müssen die Geräte mit Intune kommunizieren können. Apple erfordert eine Vertrauensstellung mit Intune, die durch Importieren eines APNs-Zertifikats (Apple Push Notification Service) eingerichtet wird.

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

5.  **Erläutern des Zugriffs auf Unternehmensressourcen über das Unternehmensportal**<br>
    Ihre Benutzer müssen wissen, wie sie ihre Geräte registrieren können und was sie erwartet, wenn die Geräte in die Verwaltung eingebunden sind. [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Wenn Ihr Unternehmen oder Ihre Organisation iOS-Geräte für Benutzer erwirbt, können diese Geräte ebenfalls zur Verwaltung als [unternehmenseigene iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) registriert werden.

### Siehe auch
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO4-->


