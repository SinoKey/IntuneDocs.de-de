---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-PCs inklusive Windows 10-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f336cf52cbecd93cb7b2850560327e6024302e0
ms.openlocfilehash: 710e34f8f97377bf57a398f74773788df3794654


---

# Einrichten der Windows-Geräteverwaltung
Mit Intune können Sie die BYOD-Registrierung („Bring Your Own Device“) für Windows-PC-Geräte aktivieren, um Benutzern Zugriff auf Unternehmens-E-Mail und -Apps zu gewähren. In Kombination mit Azure Active Directory ist dies auch eine Möglichkeit, neue Windows 10-Geräte schnell und ohne Benutzereingriff in die Verwaltung einzubinden und Zugriff auf Unternehmensressourcen zu gewähren, ohne ein Reimaging des Computers durchführen zu müssen. Nach der Registrierung können Benutzer sich anmelden, und über die Intune-Verwaltungskonsole können Richtlinien, Apps und Einstellungen auf ihre Geräte angewendet werden. Über den Intune-Client können Sie auch die [Windows Phone-Verwaltung mit Microsoft Intune einrichten](set-up-windows-phone-management-with-microsoft-intune.md) oder [Computer mit der Intune-Clientsoftware verwalten](manage-windows-pcs-with-microsoft-intune.md).

Durch das Erstellen eines DNS-CNAME-Eintrags können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

### Einrichten der Windows-Geräteverwaltung

  1.  Erstellen Sie einen **CNAME**-DNS-Ressourceneintrag für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Der CNAME-DNS-Eintrag ist für die Registrierung von Windows-Geräten zwar optional, es sollte, sofern erforderlich, jedoch mindestens ein Eintrag erstellt werden, um den Prozess der Windows-Geräteregistrierung zu vereinfachen. Wenn kein CNAME-Eintrag gefunden wird, wird der Benutzer aufgefordert, den MDM-Servernamen manuell einzugeben.

  Existieren mehrere überprüfte Domänen, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

  **EnterpriseEnrollment-s.manage.microsoft.com** – Unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

  **EnterpriseRegistration.windows.net** – Unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das jeweilige Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  2.  Klicken Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows**.
  ![Dialogfeld „Windows-Geräteverwaltung“](../media/enroll-intune-winenr.png)
  3.  Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und klicken Sie dann auf **Automatische Erkennung testen**.

### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


