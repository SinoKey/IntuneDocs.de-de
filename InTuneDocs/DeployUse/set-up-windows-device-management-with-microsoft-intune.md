---
# required metadata

title: Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einrichten der Windows-Geräteverwaltung
Mit Intune können Sie die BYOD-Registrierung („Bring Your Own Device“) für Windows-PC-Geräte aktivieren, um Benutzern Zugriff auf Unternehmens-E-Mail und -Apps zu gewähren. In Kombination mit Azure Active Directory ist dies auch eine Möglichkeit, neue Windows 10-Geräte schnell und ohne Benutzereingriff in die Verwaltung einzubinden und Zugriff auf Unternehmensressourcen zu gewähren, ohne ein Reimaging des Computers durchführen zu müssen. Nach der Registrierung können Benutzer sich anmelden, und über die Intune-Verwaltungskonsole können Richtlinien, Apps und Einstellungen auf ihre Geräte angewendet werden. Über den Intune-Client können Sie auch die [Windows Phone-Verwaltung mit Microsoft Intune einrichten](set-up-windows-phone-management-with-microsoft-intune.md) oder [Computer mit der Intune-Clientsoftware verwalten](manage-windows-pcs-with-microsoft-intune.md).

Durch das Erstellen eines DNS-CNAME-Eintrags können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

### Einrichten der Windows-Geräteverwaltung

  1.  Erstellen Sie einen **CNAME**-DNS-Ressourceneintrag für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Wenn mehr als eine überprüfte Domäne vorhanden ist, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen folgende Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  Klicken Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows**..
  ![Dialogfeld „Windows-Geräteverwaltung“](../media/enroll-intune-winenr.png)
  3.  Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Überprüften Domänennamen eingeben** ein, und klicken Sie dann auf **Automatische Erkennung testen**..

### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


