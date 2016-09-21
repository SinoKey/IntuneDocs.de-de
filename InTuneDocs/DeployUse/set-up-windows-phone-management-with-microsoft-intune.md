---
title: "Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows 10 Mobile- oder Windows Phone-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 76aaa33832dc1b765e248f85f739a4955ca90e2d


---


# Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung mit Microsoft Intune

Als Intune-Administrator können Sie die Registrierung und die Verwaltung für Windows 10 Mobile- und Windows Phone-Geräte auf zwei Arten aktivieren:

- **[Automatische Registrierung mit Azure AD](#azure-active-directory-enrollment)** – Windows 10- und Windows 10 Mobile-Benutzer registrieren ihre Geräte, indem Sie dem Gerät ein Geschäfts- oder Schulkonto hinzufügen.
- **[Unternehmensportal-Registrierung](#company-portal-app-enrollment)** – Windows Phone 8.1 und neuere Geräte werden durch das Herunterladen und Installieren der Unternehmensportal-App registriert und anschließend durch die Eingabe der Anmeldeinformationen des Geschäfts- oder Schulkontos in der App.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Registrierung der Unternehmensportal-App
Sie können Benutzern erlauben, ihre Geräte durch Installieren und Registrieren mit der Intune-Unternehmensportal-App zu registrieren. Durch das Erstellen eines DNS-CNAME-Eintrags können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen. Wenn Sie Windows Phone 8.0-Geräte verwalten oder das Unternehmensportal auf Windows Phone-Geräten bereitstellen müssen, müssen Sie die Unternehmensportal-App zusätzlich herunterladen und signieren. Siehe [Einrichten der Windows Phone 8.0-Verwaltung](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Einrichten von Intune**<br>Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2.  **Erstellen Sie einen oder mehrere CNAME-Einträge** (optional)<br>Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmens-Website beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, von dem EnterpriseEnrollment.contoso.com an manage.microsoft.com umgeleitet wird. Existieren mehrere überprüfte Domänen, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|
  Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

  `EnterpriseEnrollment-s.manage.microsoft.com` – Unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens

  `EnterpriseRegistration.windows.net` – Unterstützt Windows 8.1- und Windows 10 Mobile- Geräte, die über das Geschäfts- oder Schulkonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

3.  **CNAME überprüfen**<br>Klicken Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone**. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und klicken Sie dann auf **Automatische Erkennung testen**.

    ![Dialogfeld „Verwaltung mobiler Geräte für Windows einrichten“](../media/windows-phone-enrollment.png)

4.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps für Geräte verteilen, die nicht im Windows Store verfügbar sind. [Erfahren Sie mehr](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

5.  **Informieren von Benutzern**<br>Ihre Benutzer müssen wissen, wie sie ihre Geräte registrieren können und was sie erwartet, wenn die Geräte in die Verwaltung eingebunden sind.
    - [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md)

Es sind keine weiteren Schritte erforderlich, es sei denn, Sie stellen das Unternehmensportal selbst auf Geräten bereit.  Die Schritte 2 und 3 in der Verwaltungskonsole können ignoriert werden.



<!--HONumber=Aug16_HO5-->


