---
# required metadata

title: Vorbereiten der Registrierung von Geräten in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vorbereiten der Registrierung von Geräten in Microsoft Intune
Damit Mitarbeiter mobile Geräte (einschließlich Android, iOS Windows Phone und Windows PCs) bei Intune registrieren können, müssen Sie die Geräteregistrierung aktivieren. Um die Registrierung zu ermöglichen, müssen Sie eine Autorität zur Verwaltung mobiler Geräte festlegen, das Intune-Unternehmensportal konfigurieren, Lizenzen zuweisen und die Registrierung für die Geräteplattform aktivieren.

## <a name="BKMK_Set_MDM_Authority"></a>Festlegen der Autorität zur Verwaltung mobiler Geräte
Die Autorität für die Verwaltung mobiler Geräte definiert den Verwaltungsdienst mit der Berechtigung zum Verwalten einer Gruppe von Geräten. Die Optionen für die MDM-Autorität (Mobile Device Management, Verwaltung mobiler Geräte) umfassen Intune selbst und Configuration Manager mit Intune. Wenn Sie Configuration Manager als Verwaltungsautorität festlegen, kann kein anderer Dienst für die Verwaltung mobiler Geräte verwendet werden.

>[!IMPORTANT]
> Sie sollten sorgfältig überlegen, ob Sie mobile Geräte nur mit Intune (Onlinedienst) oder mit System Center Configuration Manager mit Intune (lokale Softwarelösung in Verbindung mit einem Onlinedienst) verwalten möchten. Nachdem Sie die Autorität für die Verwaltung mobiler Geräte festgelegt haben, kann sie nicht mehr geändert werden.



1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte**.

2.  Klicken Sie in der Liste **Aufgaben** auf **Autorität für die Verwaltung mobiler Geräte festlegen**. Das Dialogfeld **MDM-Autorität festlegen** wird geöffnet.

    ![Dialogfeld „MDM-Autorität festlegen“](../media/intune-mdm-authority.png)

3.  Intune erfordert eine Bestätigung, dass es als MDM-Autorität verwendet werden soll. Aktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Ja** , um Microsoft Intune zum Verwalten mobiler Geräte zu verwenden.

## Konfigurieren des Intune-Unternehmensportals und Zuweisen von Lizenzen
Das Intune-Unternehmensportal hilft Benutzern beim Zugriff auf Unternehmensressourcen wie Apps, beim Suchen von Helpdeskinformationen und beim Registrieren von Geräten bzw. beim Aufheben ihrer Registrierung. Vor dem Registrieren von Geräten sollten Sie [das Unternehmensportal konfigurieren](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Ferner müssen Sie [Benutzerlizenzen zuweisen](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4), um den Zugriff auf Intune zu erlauben.

## Einrichten der Geräteverwaltung
Nach dem Einrichten der MDM-Autorität müssen Sie die Geräteverwaltung für die Betriebssysteme einrichten, die Ihre Organisation unterstützen möchte. Die zum Einrichten der Geräteverwaltung erforderlichen Schritte unterscheiden sich für die verschiedenen Betriebssysteme. Beispielsweise brauchen Sie für Android OS keinerlei Aktivitäten in der Intune-Verwaltungskonsole auszuführen. Andererseits setzen Windows und iOS eine Vertrauensbeziehung zwischen den Geräten und Intune voraus, um die Verwaltung zu ermöglichen.

> [!div class="op_single_selector"]
- [Einrichten der Android-Verwaltung mit Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Einrichten der Windows-Geräteverwaltung mit Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Sie haben auch folgende Möglichkeiten:
 - Verwenden des [Kontos für den Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md), wenn viele Geräte registriert werden sollen
 - [Angeben von Geräten im Besitz des Unternehmens mithilfe von IMEI-Nummern](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md), um Geräte zu registrieren und Zielrichtlinien festzulegen


<!--HONumber=May16_HO1-->


